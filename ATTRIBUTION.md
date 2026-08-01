# Attribution

Four schemas in this repository are derived from the h2pcontrol v1 system written by Tijmen H.
Hilgenkamp (https://github.com/dyknapp/H2pControl at commit
`2973592be79f907a29c8320ea05c796dd72e0092`, 2025-06-10) and from the instrument servers written by
Daniel Knapp (https://github.com/BeyerLabVU/h2pcontrol_servers at commit
`af85d67124f787e7fa75c7e36a59174b2c41f16f`, 2025-07-10):

| This repository | Upstream file                                                          |
| --- |------------------------------------------------------------------------|
| `protos/h2pcontrol/manager/v1/manager.proto` | `H2pControl/proto/h2pcontrol.proto`                                    |
| `protos/h2pcontrol/ad45355_dac/v1/ad45355_dac.proto` | `H2pControl/manager/proto/eval_ad45335_dac.proto`                      |
| `protos/h2pcontrol/lioptec/v1/lioptec.proto` | `h2pcontrol_servers/lioptec/proto/lioptec.proto`                       |
| `protos/h2pcontrol/picoscope/v1/picoscope.proto` | `h2pcontrol_servers/picoscope_5444DMSO/proto/picoscope_5444DMSO.proto` |

Everything else in this repository is the work of the commit author.

## Seeing the diff

```sh
git clone https://github.com/dyknapp/H2pControl /tmp/v1
git -C /tmp/v1 checkout 2973592
git clone https://github.com/BeyerLabVU/h2pcontrol_servers /tmp/v1-servers
git -C /tmp/v1-servers checkout af85d67

diff -u /tmp/v1/proto/h2pcontrol.proto                                    protos/h2pcontrol/manager/v1/manager.proto
diff -u /tmp/v1/manager/proto/eval_ad45335_dac.proto                      protos/h2pcontrol/ad45355_dac/v1/ad45355_dac.proto
diff -u /tmp/v1-servers/lioptec/proto/lioptec.proto                       protos/h2pcontrol/lioptec/v1/lioptec.proto
diff -u /tmp/v1-servers/picoscope_5444DMSO/proto/picoscope_5444DMSO.proto protos/h2pcontrol/picoscope/v1/picoscope.proto
```
