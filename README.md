# components-example

WebAssembly Component Model example

This is a slow-burning work-in-progress :-)

Eventually I am hoping to have a working example of a web application that can
be deployed as a single Wasm module, but which is composed of multiple
components, each of which can be built and deployed independently.

For now it's a simple wasmCloud actor for http and key-value storage.

## Prerequisites

- `cargo` 1.74
- `wash` 0.25.0
- `wasmtime` 16.0.0 (if running with wasmtime)
- `redis-server`

## Building

```bash
wash build
```

## Running with wasmCloud

Make sure to follow the build steps above, and replace the file path in
[the wadm manifest](./wadm.yaml) with the absolute path to your local built
component.

```
wash up -d
wash app deploy ./wadm.yaml
curl http://localhost:8081
```
