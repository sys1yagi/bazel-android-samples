# bazel-android-samples

# Setup

## Change WORKSPACE file

WORKSPACE is local environment settings file for android build.
It should be empty on repository maybe.

Please rewrite to suit your environment.

```
android_sdk_repository(
  name="androidsdk",
  path="/usr/local/opt/android-sdk",
  api_level = 23,
  build_tools_version="23.0.1"
)
```

## Setup project

See README.md of each projects.

- [project-generated-by-android-studio](project-generated-by-android-studio)
- [project-generated-by-android-studio-blank-activity](project-generated-by-android-studio-blank-activity)

## Build

ex. project-generated-by-android-studio

Run command in the same location as the WORKSPACE.

```
bazel build //project-generated-by-android-studio:android
```

## Install

ex. project-generated-by-android-studio

```
bazel mobile-install //project-generated-by-android-studio:android
```
