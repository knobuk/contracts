# knobuk/contracts

Protobuf source of truth for all KNOBUK gRPC services and events.

## Layout

```
proto/knobuk/     # .proto files
gen/go/           # generated Go stubs (commit after make proto-gen)
buf.yaml
buf.gen.yaml
```

## Generate Go stubs

From the workspace `dev/` repo:

```bash
cd ../dev && make proto-gen
```

Or locally with buf installed:

```bash
buf generate
```

## Versioning

Tag releases (`v0.1.0`, `v0.2.0`). Services pin a tag in production.

Go module: `github.com/knobuk/contracts/gen/go` (generated import path).

## Local path

Sibling services reference this repo via:

```
../contracts/proto          # Java, Node, Python, .NET codegen
../contracts/gen/go         # Go replace directive
```
