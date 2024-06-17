## Implementations

Follow the latest poc implementations

- [zeb](https://github.com/hetu-project/zeb)
- [chronos](https://github.com/hetu-project/chronos)
- [zeb-aggregator](https://github.com/hetu-project/zeb-aggregator)
- [zeb-Pegion](https://github.com/hetu-project/zeb-pegion)
- [zeb-dolphin](https://github.com/hetu-project/zeb-dolphin)

### zeb

ZNet is a p2p relay network with verifiable VLC (virtual logic clock) causal order. This system is currently in poc stage.

### zchronod

The zchronod or chronos is a implement of vlc(verifiable logical clock).

It use the znet p2p relay as network module. And as a backend project node for supporting verifiable logical clock and causality ordering. This system is currently in poc stage.

### aggregator

The zeb-aggregator is for collecting P2P VLC date periodically and providing APIs for the browser and Chrome extension to query relative data.

### Pegion

Pegion is a p2p chat chrome extension base on Zeb network. The message sent by Pigeon carries VLC information during its transmission through the Zeb network. By utilizing the VLC information, the propagation path of the message can be effectively determined.

### Dolphin

Dolphin is a browser for the zeb network to display a graph of message graph through nodes.
