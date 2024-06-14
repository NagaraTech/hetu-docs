### proto

VLC and P2P use Protobuf format to exchange messages, and the same format is used between the Gateway and P2P. Here is the Protobuf format definition:

znet.proto

```protobuf
message ZMessage {
  bytes id = 1;
  uint32 version = 2;
  ZType type = 3;
  bytes public_key = 4;
  bytes data = 5;
  bytes signature = 6;
  bytes from = 7;
  bytes to = 8;
}

enum ZType {
  Z_TYPE_RNG = 0;
  Z_TYPE_EVENT = 1;
  Z_TYPE_CLOCK = 2;
  Z_TYPE_GATEWAY = 3;
  Z_TYPE_ZCHAT = 4;
}

message OutboundMsg {
  bytes id = 1;
  bytes from = 2;
  bytes to = 3;
  bytes data = 4;
  ZType type = 5;
}

message InboundMsg {
  bytes id = 1;
  bytes from = 2;
  bytes data = 3;
  ZType type = 4;
}

message NodeData {
  bytes public_key = 1;
  uint32 websocket_port = 2;
  uint32 json_rpc_port = 3;
  string domain = 4;
}
```

vlc.proto

```protobuf
syntax = "proto3";

package bussiness;

import "vlc.proto";

// business data
// ZMessage.type = Z_TYPE_CHAT
message ZChat {
	bytes message_data = 1;
	vlc.ClockInfo clock = 2;
}

// ZMessage.type = Z_TYPE_HPOINTS
message HPoints {
	bytes op_address = 1;
	bytes event_id = 2;
	uint64 points = 3;  // new points
}

// ZMessage.type = Z_TYPE_GATEWAY
// Gateway just only needs read api
message ZGateway {
    string request_id = 1;
    GatewayType type = 2;
    QueryMethod method = 3;
    bytes data = 4;
}

enum GatewayType {
  GATEWAY_TYPE_CLOCK_NODE = 0;
  GATEWAY_TYPE_MERGE_LOG = 1;   // ref merge log
  GATEWAY_TYPE_NODE_INFO = 2;  // heartbeat or node info
  GATEWAY_TYPE_Z_MESSAGE = 3;  // p2p message
}

enum QueryMethod {
    QUERY_BY_MSGID = 0;
    QUERY_BY_TABLE_KEYID = 1;
    QUERY_STATUS = 2;
}

// ZGateway.type = GATEWAY_TYPE_CLOCK_NODE
// please see ClockInfos in vlc.proto 

// ZGateway.type = GATEWAY_TYPE_NODE_INFO
message NodeInfo {
    repeated string node_ids = 1;
}

message QueryResponse {
    string request_id = 1;
    bool success = 2;
    string reason = 3;
    bytes data = 4;
}

// ZGateway.method = QUERY_BY_MSGID
message QueryByMsgID {
    string msg_id = 1;
}

// ZGateway.method = QUERY_BY_TABLE_KEYID
message QueryByTableKeyID {
    uint64 last_pos = 1;
}

// ZGateway.method = QUERY_STATUS
message QueryStatus {
    uint64 clock_total = 1;
    uint64 mergelog_total = 2;
    uint64 zmessage_total = 3;
}
```

### api

znet json-rpc

POST http://54.151.255.61:13333/rpc13333

```json
{
    "method": "getWsAddr",
    "address": "a308d9f92777ab8c4f5daa89592faeede951d7f5006fff600b0c082b24e964af"
}
{
    "method": "getNodeStates"
}

{
    "method": "getExtIp"
}
{
    "method": "getNeighbors"
}
{
    "id": "139812928310222",
    "method": "queryByKeyId",
    "gatewayType": 3,
    "index": 0
}
```

Definition of `gatewayType` in the `queryByKeyId` method.

```protobuf
GATEWAY_TYPE_CLOCK_NODE = 0;  // clock
GATEWAY_TYPE_MERGE_LOG = 1;   // ref merge log
GATEWAY_TYPE_NODE_INFO = 2;  // heartbeat or node info
GATEWAY_TYPE_Z_MESSAGE = 3;  // p2p message
```
