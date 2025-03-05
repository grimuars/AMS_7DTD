# OCB Remote Description Mod - 7 Days to Die (V1.0) Addon

This mod is meant to be used by other mods in order to
provide remote information when looking at blocks. On a
dedicated server, a lot of information is not readily
available on the client side. This limits what can be
shown when looking at blocks.

This mod solves this by pinging the server when we look
at a block. Actually only blocks that have been configured
to use remote descriptions, in order to preserve bandwidth.
The server will then answer with the requested custom label.

We do this repeatedly when staring at one block in order to
get up to date information from the server. In case the
server doesn't answer, the last provided label is used,
until it either goes stale or an update is received.

This gives a fair balance between bandwidth usage and added
value, as we only ask for an update about once per second.

See [OcbPlantGrowInfo][1] for a demo implementation.

[![GitHub CI Compile Status][3]][2]

## Download and Install

End-Users are encouraged to download my mods from [NexusMods][5].  
Every download there helps me to buy stuff for mod development.

Otherwise please use one of the [official releases][4] here.  
Only clone or download the repo if you know what you do!

## Changelog

### Version 0.3.1

- Verified compatibility with V1.0 (b333)
- Improve responsiveness when looking at new block 
- Fix issue when re-joining a server without restart

### Version 0.3.0

- First compatibility with V1.0 (exp)

### Version 0.2.0

- Update compatibility for 7D2D A21.0(b313)

### Version 0.1.0

- Last A20.6/7 compatible version

[1]: https://github.com/OCB7D2D/OcbPlantGrowInfo
[2]: https://github.com/OCB7D2D/OcbRemoteDescription/actions/workflows/ci.yml
[3]: https://github.com/OCB7D2D/OcbRemoteDescription/actions/workflows/ci.yml/badge.svg
[4]: https://github.com/OCB7D2D/OcbRemoteDescription/releases
[5]: https://www.nexusmods.com/7daystodie/mods/2165