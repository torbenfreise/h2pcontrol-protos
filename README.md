# h2pcontrol-protos

Protobuf definitions for the h2pcontrol lab device registry. Each proto defines the api interface of respective device.

## Usage

Schemas are published to the [Buf Schema Registry](https://buf.build/beyer-labs/h2pcontrol) on every merge to `main`.

## Adding a new device

1. Create `protos/h2pcontrol/<device>/v1/<service>.proto`
2. Copy the following template, replacing 'device' with your device name: 
```protobuf
syntax = "proto3";

package h2pcontrol.device.v1;

option java_multiple_files = true;
option java_outer_classname = "DeviceProto";
option java_package = "com.beyerlabs.h2pcontrol.device.v1";
```
3. Open a new PR with your changes.The workflow will automatically run linting and formatting checks. 
4. Once the checks have passed, you can merge to main, and the schemas and SDKs will be available in the registry.


## Linting and Formatting

This project uses the [buf CLI](https://buf.build/docs/installation) to format and lint proto files.

### Format

Auto-format all `.proto` files in place:

```bash
buf format -w
```

### Lint

Run the linter to check for style violations:

```bash
buf lint
```
Lint rules can be configured in `buf.yaml`.
