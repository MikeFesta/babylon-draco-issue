# babylon-draco-issue

Sample code demonstrating an issue loading a glTF base64 string with draco compression. The context is NodeJS with the NullEngine, using SceneLoader.

## How to use

```
npm i
```

```
node index.js
```

### BabylonJS Playground Example

https://playground.babylonjs.com/#QYY96X
Shows that this issue is not present in the web browser context

### SceneLoader.AppendAsync works for a non-draco compressed base64 string

The first test works and can load the cube.

### GLTFFileLoader Works

The second test works and can load the draco compressed cube base64 string with the GLTFFileLoader.

### SceneLoader.AppendAsync fails for a draco compressed base64 string

The third test fails, which is the issue that we would like to resolve.
