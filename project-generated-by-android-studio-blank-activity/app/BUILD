android_binary(
  name = "android",
  custom_package = "com.sys1yagi.project_generated_by_android_studio_blank_activity",
  srcs = glob(["src/main/java/com/sys1yagi/project_generated_by_android_studio_blank_activity/*.java"]),
  manifest = "src/main/AndroidManifest.xml",
  resource_files = glob(["src/main/res/**"]),
  deps = ["support_design", "//external:android/appcompat_v4", "//external:android/appcompat_v7"],
)

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
