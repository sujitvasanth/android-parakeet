# Android Parakeet GPU pipeline

ARM64 Android APK artifacts for local Parakeet speech recognition using the native `ggml` runtime and OpenCL GPU acceleration, with CPU fallback.

## Install

1. Download an APK from [`releases/`](releases/).
2. On the phone, allow installation from the file manager/browser if Android asks.
3. Open the APK and install it.
4. Launch **Parakeet Transcriber** and choose a compatible Parakeet `.gguf` model from device storage.

The project targets ARM64 Android devices. The OpenCL build is the supported GPU variant; Vulkan artifacts are excluded because that path failed on the target device.

## Included builds

- `Parakeet-OpenCL-GPU19.apk` — working OpenCL GPU build.

## Project layout

- `app/` — recovered Android manifest, resources, and Java activities.
- `native-libs/arm64-v8a/` — ARM64 OpenCL native libraries used by the APK.
- `releases/` — signed APK artifacts ready for sideloading.

## Build note

These are packaged artifacts from the previous Codex workspace rather than a clean Gradle project. Rebuilding the native layer requires the Android NDK, CMake, OpenCL headers, and the Parakeet/ggml source tree.

## Model

The app expects a compatible Parakeet GGUF model supplied separately. Model files are intentionally not committed to this repository because they are large.

## License

Check the licenses of the Parakeet, ggml, Vulkan, and OpenCL components before redistribution.
