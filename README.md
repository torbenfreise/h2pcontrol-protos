# h2pcontrol-protos

Protobuf definitions for the h2pcontrol lab device registry. Each proto represents a service running on a lab device.

## Structure

```
protos/h2pcontrol/<device>/v1/<service>.proto
```

Packages follow the directory path: `h2pcontrol.<device>.v1`

## Usage

Schemas are published to the [Buf Schema Registry](https://buf.build/drumglow/protos) on every merge to `main`.

Generate client code using [Buf remote plugins](https://buf.build/plugins) or add this module as a dependency in your `buf.yaml`:

```yaml
deps:
  - buf.build/drumglow/protos
```

## Adding a new device

1. Create `protos/h2pcontrol/<device>/v1/<service>.proto`
2. Set the package to `h2pcontrol.<device>.v1`
3. Open a PR — CI will lint and check for breaking changes automatically

## Versioning

Non-breaking changes (new fields, new RPCs) go into the existing `v1/` directory. Breaking changes require a new `v2/` directory alongside `v1/`.