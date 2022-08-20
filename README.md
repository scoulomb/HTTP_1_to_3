# HTTP/1 to HTTP/3


## Resource HTTP 1.1 and 2

Slides JM 

## HTTP 1.1 

Introduction to Keep Alive.
See https://github.com/scoulomb/private_script/blob/main/Links-story-notes/connection-keep-alive.md

<!-- was ccl -->

## HTTP 2.0

### Reminder on TCP layer 

It is not HTTPS it is more TCP/TLS/HTTP.

It is well visible 
- https://github.com/scoulomb/docker-under-the-hood/tree/main/NAT-deep-dive-appendix#source-port which also points to 
    - https://stackoverflow.com/questions/31446777/difference-between-packets-and-frames/31464376#31464376 (where packet enscapulsation is shown)
    - https://github.com/scoulomb/misc-notes/blob/master/NAS-setup/Wake-On-LAN.md#reminder-on-arp 
    - https://github.com/scoulomb/misc-notes/blob/master/NAS-setup/Wake-On-LAN.md#wol---how-does-it-work
    <!-- all ccl here and said not a ~~ topic ~-->

- This wikipedia article also completes: https://en.wikipedia.org/wiki/Internet_protocol_suite and show router. <!-- (could imagine nexted rectangle also) -->
- This enables to understand what is TCP (also used here: https://github.com/scoulomb/misc-notes/blob/master/NAS-setup/Wake-On-LAN.md#socket-and-python)

<!-- section "Reminder on TCP layer" ccl -->

### About stream

See https://github.com/scoulomb/private_script/blob/main/Links-story-notes/socketEstablishmentDirection.md
<!-- this ccl and update consider OK for now -->

Websocket and HTTP 2 breaks traditionnal query/reply (inboud/outbound) and push for bi-directionnal flow


From https://stackoverflow.com/questions/21057882/whats-the-main-difference-between-bidirectional-and-directional-sockets (actually question say socket but it means message flow as mentionned in answer)
> Websockets are an attempt to work around the pull model of HTTP, e.g. where the client does an HTTP query and the server does an HTTP response and that's the end of the talk. But often more than that is needed, e.g. server push or just classical bidirectional communication not limited to request+response. In a world without firewalls, one would use classical sockets for this task, but in today's world lots of communication is restricted and direct connections to arbitrary ports will not work anymore.

From https://stackoverflow.com/questions/28582935/does-http-2-make-websockets-obsolete
> The main use case for Websockets in a browser is to enable bidirectional streaming of data. So, I think the OP's question becomes whether HTTP/2 does a better job of enabling bidirectional streaming in the browser, and I think that yes, it does.

Here https://datatracker.ietf.org/doc/html/rfc7540#page-15
> A "stream" is an independent, bidirectional sequence of frames
exchanged between the client and server within an HTTP/2 connection.


From https://web.dev/performance-http2/
> Stream: A bidirectional flow of bytes within an established connection, which may carry one or more messag

See also
https://docs.aws.amazon.com/transcribe/latest/dg/streaming-setting-up.html