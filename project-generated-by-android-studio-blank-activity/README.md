# Setup 

## Generate BUILD file

AS generate `build` directory automatically. 
`build` directory and `BUILD` file collide in the case-insensitive environment.
So, avoid the collision by the following flow。

```sh
chmod +x setup_build_file.sh
./gradlew clean
./setup_build_file.sh
```

It generate a symbolic link of `BUILD_FILE`.

## Create symbolic link of android_sdk

bazel supports appcompat-v7 and v4 by default. But support-design and other library does not support (It will be supported later).

```
//ok
deps = ["//external:android/appcompat_v7"] 

//error
deps = ["//external:android/design"] 
```

So, defined the dependency of support-design in BUILD-file. 

```
java_import(
  name = "support_design_import",
  jars = ["android-sdk/extras/android/support/design/libs/android-support-design.jar"],
)

android_library(
  name = "support_design",
  custom_package = "android.support.design",
  manifest = "android-sdk/extras/android/support/design/AndroidManifest.xml",
  resource_files = glob(["android-sdk/extras/android/support/design/res/**"]),
  deps = [":support_design_import",  "//external:android/appcompat_v7"],
)
```

You should recreate symbolic link of "android-sdk" directory.

```sh
ln -s android-sdk /path/to/android-sdk
```
