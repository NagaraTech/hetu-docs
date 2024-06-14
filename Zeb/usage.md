## Usage

### Integrating into the Existing Environment

p2p test env: http://54.151.255.61:13333/rpc13333
gateway test env: http://52.221.181.98:8080/gateway
Pegion chrome extension: https://github.com/NagaraTech/z-message-extension/actions/runs/9362056141

1. After downloading the Chrome extension
2. add an RPC
3. create or add an account
4. then add friends to start chatting.

### Setting Up a New EnvironmentUsage

> To create a new environment, it is recommended to start with at least 10 nodes.

Each node should include a `znet` and a `zchronod` with postgresql.

[Here](https://github.com/NagaraTech/p2p-docker/tree/main/scripts) is a reference script to set up a new environment with at least 10 nodes, each including a `znet` and a `zchronod`

Sure, here's a detailed guide on how to proceed with deploying the gateway, configuring the environment, and setting up the browser and Chrome extension for chatting.

Sure, here's a detailed guide on how to proceed with deploying the gateway, configuring the environment, and setting up the browser and Chrome extension for chatting.

Create an environment configuration file (e.g., `.env`) with the necessary settings.

Here is a script to deploy the gateway using the configuration from the `.env` file:

Set the Gateway URL in the browser configuration. Here is an example of how you might configure and deploy the browser application

Ensure that your browser application reads from this configuration file and uses the `gatewayUrl` when making requests.

Deploy the browser application following your standard deployment process. This might involve building and deploying a web application.
