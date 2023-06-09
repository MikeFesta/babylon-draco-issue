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

```
uncompressed cube loaded from base64 with SceneLoader.AppendAsync
```

### GLTFFileLoader Works

The second test works and can load the draco compressed cube base64 string with the GLTFFileLoader.

```
compressed cube loaded from base64 with GLTFFileLoader
```

### SceneLoader.AppendAsync fails for a draco compressed base64 string

The third test fails, which is the issue that we would like to resolve.

```
Testing failed, which is expected until the issue is identified.
Unable to load from data:;base64,Z2xURgIAAAA8BQAAGAQAAEpTT057ImFzc2V0Ijp7ImdlbmVyYXRvciI6Iktocm9ub3MgZ2xURiBCbGVuZGVyIEkvTyB2My40LjUwIiwidmVyc2lvbiI6IjIuMCJ9LCJleHRlbnNpb25zVXNlZCI6WyJLSFJfZHJhY29fbWVzaF9jb21wcmVzc2lvbiJdLCJleHRlbnNpb25zUmVxdWlyZWQiOlsiS0hSX2RyYWNvX21lc2hfY29tcHJlc3Npb24iXSwic2NlbmUiOjAsInNjZW5lcyI6W3sibmFtZSI6IlNjZW5lIiwibm9kZXMiOlswXX1dLCJub2RlcyI6W3sibWVzaCI6MCwibmFtZSI6IkN1YmUifV0sIm1hdGVyaWFscyI6W3siZG91YmxlU2lkZWQiOnRydWUsIm5hbWUiOiJNYXRlcmlhbCIsInBick1ldGFsbGljUm91Z2huZXNzIjp7ImJhc2VDb2xvckZhY3RvciI6WzAuODAwMDAwMDExOTIwOTI5LDAuODAwMDAwMDExOTIwOTI5LDAuODAwMDAwMDExOTIwOTI5LDFdLCJtZXRhbGxpY0ZhY3RvciI6MCwicm91Z2huZXNzRmFjdG9yIjowLjQwMDAwMDAwNTk2MDQ2NDV9fV0sIm1lc2hlcyI6W3sibmFtZSI6IkN1YmUiLCJwcmltaXRpdmVzIjpbeyJhdHRyaWJ1dGVzIjp7IlBPU0lUSU9OIjowLCJURVhDT09SRF8wIjoxLCJOT1JNQUwiOjJ9LCJleHRlbnNpb25zIjp7IktIUl9kcmFjb19tZXNoX2NvbXByZXNzaW9uIjp7ImJ1ZmZlclZpZXciOjAsImF0dHJpYnV0ZXMiOnsiUE9TSVRJT04iOjAsIlRFWENPT1JEXzAiOjEsIk5PUk1BTCI6Mn19fSwiaW5kaWNlcyI6MywibWF0ZXJpYWwiOjAsIm1vZGUiOjR9XX1dLCJhY2Nlc3NvcnMiOlt7ImNvbXBvbmVudFR5cGUiOjUxMjYsImNvdW50IjoyNCwibWF4IjpbMSwxLDFdLCJtaW4iOlstMSwtMSwtMV0sInR5cGUiOiJWRUMzIn0seyJjb21wb25lbnRUeXBlIjo1MTI2LCJjb3VudCI6MjQsInR5cGUiOiJWRUMyIn0seyJjb21wb25lbnRUeXBlIjo1MTI2LCJjb3VudCI6MjQsInR5cGUiOiJWRUMzIn0seyJjb21wb25lbnRUeXBlIjo1MTIzLCJjb3VudCI6MzYsInR5cGUiOiJTQ0FMQVIifV0sImJ1ZmZlclZpZXdzIjpbeyJidWZmZXIiOjAsImJ5dGVMZW5ndGgiOjI2MywiYnl0ZU9mZnNldCI6MH1dLCJidWZmZXJzIjpbeyJieXRlTGVuZ3RoIjoyNjR9XX0gCAEAAEJJTgBEUkFDTwICAQEAAAAYDAIMAAAF3/d93wf/AmZA/wJmQP8CZkAD/wAAAAAAAQAAAQAJAwAAAgEDCQIAAQIBAQkDAAIDAQEBAQIDASiRC3EMDmRHEWAv/xK+X0lVB8KvAAAAAP8/AAAAAIC/AACAvwAAgL8AAABADgEBAQANAwEQI1UVrRoHd4lAByCfiQAYgADYf/8HAP/vPwD+3/8BwP8DAAD+3/8BAAD4PwD+3/8BwP8JIAD+3/8BAAAAoP//338AAAAAAAD/DwAAAAAAPgAAAAAAAIA/DAADAQALAwEwGwEIAQgGAAjLlW+AAAAI/AcAAAgA4P9/AID/wP//AP8DAAD/AQAACgA=: Unable to get absolute URL. Override BABYLON.Tools.GetAbsoluteUrl to a custom implementation for the current context.
```
