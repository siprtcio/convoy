![convoy image](./convoy-logo.svg)
=========
[![golangci-lint](https://github.com/frain-dev/convoy/actions/workflows/linter.yml/badge.svg)](https://github.com/frain-dev/convoy/actions/workflows/linter.yml)
[![Build and run all tests](https://github.com/frain-dev/convoy/actions/workflows/go.yml/badge.svg)](https://github.com/frain-dev/convoy/actions/workflows/go.yml)
- Website: https://getconvoy.io
- Forum: [Github Discussions](https://github.com/frain-dev/convoy/discussions)
- Documentation: [getconvoy.io/docs](https://getconvoy.io/docs)
- Deploy: [Install Convoy](https://getconvoy.io/docs/deploy/install-convoy)
- Slack: [Join the Community](https://join.slack.com/t/convoy-community/shared_invite/zt-xiuuoj0m-yPp~ylfYMCV9s038QL0IUQ)


[Convoy](https://getconvoy.io) is the Fastest Webhooks Gateway developers use to securely ingest, persist, debug, deliver and manage millions of events reliably with rich features such as retries, rate limiting, static ips, circuit breaking, rolling secrets and more. It was built for Engineers that value efficiency in their workflow, to get started download the [openapi spec](https://github.com/frain-dev/convoy/blob/main/docs/v3/openapi3.yaml) into Postman or Insomnia. Convoy is [FREE for developers](https://getconvoy.io/blog/Convoy-Webhooks-is-free-for-developers) forever.

Convoy provides several key features:

- **Webhooks Gateway:** As a webhooks gateway, Convoy lives at the edge of your network to stream webhooks from your micoservices, and send them out to your users as well as receive webhooks from your providers and route them to the required services. With this your internal systems are never exposed to the public internet.

- **Scalability:** Convoy acts as a dedicated message queue for webhooks, and was designed to be horizontally scalable. It includes several components like the `api server`, `workers`, `scheduler`, and `socket server` which can be scaled independently to fit the need.

- **Security:** Convoy ships with several security features for webhooks, such as payload signing to ensure message integrity, bearer token authentication for authenticated webhook endpoints, and static ips for network environments with strict firewall rules.

- **Fan Out:** Convoy is able to route an events to multiple endpoints based on the event type or payload structure. It relies on a subset of [MongoDB's Extended JSON v2](https://www.mongodb.com/docs/manual/reference/mongodb-extended-json/) to match event payload structure and route events to their respective destination(s).

- **Rate Limiting:** While Convoy is able to ingest events at a massive rate, it throttles the delivery of these events to the endpoints at a configurable rate per endpoint. 

- **Retries & Batch Retries:** Convoy supports two retry algorithms; constant time and exponential backoff with jitter. Where automatic retries are not sufficient, convoy provides batch retries for endpoints are consecutively failed to process retried events.

- **Customer-Facing Dashboards:** Convoy allows you to generate customer facing webhooks dashboard to embed into your applications using an iframe. On this dashboard, users can debug webhooks, retry events, add endpoints, and configure each endpoint's subscription.

- **Endpoint Failure Notifications:** When endpoints consecutively fails to process events, convoy disables the endpoint and sends out a notification. Two types of notifications are supported: Email and Slack Notifications.

## Installation, Getting Started
There are several ways to get started using Convoy.

### Option 1: Using our Install Script on Linux
```bash
 /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/frain-dev/convoy/main/deploy/vm-deploy.sh)"
```

### Option 2: Convoy Cloud
Get started with our free Cloud version -- Sign up for [Convoy Cloud](https://dashboard.getconvoy.io/signup) account 

### Option 3: Deploy Locally
To do this make sure you have [Docker 20+](https://docs.docker.com/desktop/) installed.

```bash
# Get the code
$ git clone https://github.com/frain-dev/convoy.git

# Go to the Convoy folder
$ cd convoy

# Start Services
docker compose -f configs/local/docker-compose.yml up
```

## Contributing
Thank you for your interest in contributing! Please refer to [CONTRIBUTING.md](https://github.com/frain-dev/convoy/blob/main/CONTRIBUTING.md) for guidance. For contributions to the Convoy dashboard, please refer to the [web/ui](https://github.com/frain-dev/convoy/tree/main/web/ui) directory.

## License
[Mozilla Public License v2.0](https://github.com/frain-dev/convoy/blob/main/LICENSE)
