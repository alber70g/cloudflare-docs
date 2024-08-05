---
title: Advanced TCP Protection
pcx_content_type: concept
weight: 1
meta:
  title: Cloudflare Advanced TCP Protection
---

# Cloudflare Advanced TCP Protection

Cloudflare Advanced TCP Protection, powered by [`flowtrackd`](https://blog.cloudflare.com/announcing-flowtrackd/), is a stateful TCP inspection engine used to detect and mitigate sophisticated out-of-state TCP attacks such as randomized and spoofed ACK floods or SYN and SYN-ACK floods.

Advanced TCP Protection can simultaneously protect against different kinds of attacks:
* Pinpointed attacks targeting a specific destination IP/port combination.
* Broad attacks targeting multiple IP addresses of an IP prefix at the same time.

Advanced TCP Protection can track TCP connections even when they move between Cloudflare data centers.

## SYN Flood Protection

This system protects against attacks such as fully randomized SYN and SYN-ACK floods. You should configure at least one SYN flood rule before enabling Advanced TCP Protection.

In mitigation mode, SYN flood rules will challenge new connection initiation requests (SYN, SYN-ACK) if they exceed the configured packet-per-second thresholds. The threshold should be higher than the normal rate of legitimate SYN and SYN-ACK packets that your network receives. Packets below the threshold will not be challenged. Using the [rate sensitivity](/ddos-protection/advanced-ddos-systems/rule-settings/#rate-sensitivity) and [burst sensitivity](/ddos-protection/advanced-ddos-systems/rule-settings/#burst-sensitivity) settings you can increase or decrease the tolerance of SYN and SYN-ACK packets.

For more information on the configuration settings of SYN flood rules, refer to [Rule settings](/ddos-protection/advanced-ddos-systems/rule-settings/).

## Out-of-state TCP Protection

This system protects against out-of-state TCP DDoS attacks such as fully randomized ACK floods and RST floods. You should configure one out-of-state TCP rule before enabling Advanced TCP Protection.

In mitigation mode, out-of-state TCP rules will drop out-of-state packets that do not belong to existing (and tracked) TCP connections if their rates exceed the configured thresholds. The threshold should be higher than the normal rate of non SYN or SYN-ACK TCP packets that your network receives. Packets below the threshold will not be evaluated. Using the [rate sensitivity](/ddos-protection/advanced-ddos-systems/rule-settings/#rate-sensitivity) and [burst sensitivity](/ddos-protection/advanced-ddos-systems/rule-settings/#burst-sensitivity) settings you can increase or decrease the tolerance of out-of-state TCP packets.

For more information on the configuration settings of out-of-state TCP rules, refer to [Rule settings](/ddos-protection/advanced-ddos-systems/rule-settings/).

## Setup

1. Log in to the [Cloudflare dashboard](https://dash.cloudflare.com/login) and select your account. 
2. Go to **L3/4 DDoS** > **Advanced Protection** > **Advanced TCP Protection**.
3. 
4.
5.