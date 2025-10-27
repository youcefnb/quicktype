---

### Summary

This PR adds new options to the CSharp renderer to control the usage of `DateOnly` and `TimeOnly` types when generating code for the System.Text.Json serialization framework.

### Changes

- **feat(csharp):** Introduced new boolean options `no-dateonly` and `no-timeonly` in CSharp language options.
- Updated `package.json` dependencies for `ajv` and `esbuild`.
- Refactored `SystemTextJsonCSharpRenderer` to use the new options, allowing conditional registration of `DateOnly` and `TimeOnly` converters.
- Added helper methods to determine usage of `DateOnly` and `TimeOnly` types based on newly provided options.

### Motivation

Addresses #2629 (https://github.com/glideapps/quicktype/issues/2629), allowing users to exclude `DateOnlyConverter` and `TimeOnlyConverter` from generated code for projects targeting .NET Standard, where these types are unavailable.

### Impact

- Users can now generate C# code compatible with .NET Standard by disabling `DateOnly` and `TimeOnly` usage.
- Improves support for libraries intended for broad .NET platform compatibility.

---