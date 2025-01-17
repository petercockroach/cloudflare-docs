---
pcx_content_type: concept
source: https://support.cloudflare.com/hc/en-us/articles/200169466-Using-Cloudflare-with-WebSockets
title: WebSockets
---

# WebSockets

Cloudflare supports proxied WebSocket connections without additional configuration.

## Availability

{{<feature-table id="network.websockets">}}

## Background

WebSockets are open connections sustained between the client and the origin server. Inside a WebSockets connection, the client and the origin can pass data back and forth without having to reestablish sessions. This makes exchanging data within a WebSockets connection fast. WebSockets are often used for real-time applications such as live chat and gaming.

## Compatibility notes

| Product | Compatible | Notes |
| --- | --- | --- |
| [SSL](/ssl/) | Yes |
| [WAF](/waf/) | Yes* | The initial HTTP 101 request is subject to WAF managed rules, custom rules, rate limiting rules, and other WAF features like any other WebSockets connection. However, once a connection has been established, the WAF does not perform any further inspections. |
| [Workers](/workers/examples/websockets/) | Yes | You can also use [Durable Objects](/durable-objects/) as an endpoint for WebSocket sessions, giving you full control over messages sent to and from clients. |

## What happens if my site exceeds the number of concurrent WebSockets connections that Cloudflare expects?

Immediately, nothing. Cloudflare will allow occasional spikes in usage beyond our guidelines and we will not apply unnecessary limits.

Repeated spikes or high continued usage will prompt a dialogue. Cloudflare will reach out to learn more about your application. We will not impose limit errors for any application without contacting the customer unless we suspect that abuse or an attack is involved.

Customers whose usage claims a disproportionate percentage of resources for their current plan level may be asked to upgrade to the plan level that matches their needs.

## Technical note

When Cloudflare releases new code to its global network, we may restart servers, which terminates WebSockets connections.
