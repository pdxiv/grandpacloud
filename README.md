# grandpa cloud

## Abstract

This document specifies a technically simplified model for accomplishing cloud functionality for an interested audience, and requests discussion and suggestions for improvements.

## Rationale

Running services with a modern cloud infrastructure can be complex. Can the the high-level goals of modern cloud infrastructure be realized in a technically simplified way using technologies that are mature and commonly available on most computing platforms "out-of-the-box"? 

Possible benefits:
* Higher uptime
* Better utilization of system resources
* Higher service speeds
* Lower service latencies
* Faster troubleshooting
* Less training required (only basic operating system and networking concepts)

## Definitions and Notation

The following sections define terms used in this document.

###  Requirements Notation

This document occasionally uses terms that appear in capital letters. When the terms "MUST", "SHOULD", "MUST NOT", "SHOULD NOT", and "MAY" appear capitalized, they are being used to indicate particular requirements of this specification.  A discussion of the meanings of these terms appears in [RFC-2119].

## Concepts requirements

### Security

* Security abstractions SHOULD NOT be added unless there is a distinct requirement.
* There SHOULD be few or no firewalls.
* When security is required:
  + TCP MUST use SSL.
  + UDP MUST use DTLS.

### Networking

* NAT MUST NOT be used, except for with web browsers.
* HTTP MUST NOT be used, except for with web browsers.
* UDP SHOULD be used whenever it doesn't add complexity over TCP.
* Containers MUST use the "host networking" driver.
* IPv6 SHOULD be used whenever possible.
* Applications SHOULD rely on service discovery to find networked resources when possible.
* Service discovery SHOULD be accomplished with DNS-SD (DNS Service Discovery).
* Networked services MUST use client-side load balancing, except for communication with web browsers.

### Integration

* Service complexity SHOULD be avoided. Consider using statically compiled binaries when possible. Avoid the complexity of many dependencies and/or containers.
