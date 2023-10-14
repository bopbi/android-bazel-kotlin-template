load("@rules_kotlin//kotlin:android.bzl", "kt_android_library")
load("@rules_jvm_external//:defs.bzl", "artifact")

android_binary(
    name = "app",
    custom_package = "com.example.hellobazel",
    manifest = "AndroidManifest.xml",
    manifest_values = {
        "minSdkVersion": "24",
        "targetSdkVersion": "34",
    },
    deps = ["//app/src/main:main_lib"],
)

kt_android_library(
    name = "main_lib",
    srcs = glob(["java/com/example/hellobazel/*.kt"]),
    custom_package = "com.example.hellobazel",
    manifest = "AndroidManifest.xml",
    resource_files = glob(["res/**"]),
    visibility = ["//app/src:__subpackages__"],
    deps = [
        artifact("androidx.appcompat:appcompat"),
        artifact("androidx.core:core-ktx"),
        artifact("androidx.constraintlayout:constraintlayout"),
        artifact("androidx.lifecycle:lifecycle-runtime"),
        "main_external_lib",
    ],
)

## Separate Material Design as Demo
kt_android_library(
    name = "main_external_lib",
    srcs = glob(["java/com/example/hellobazel/*.kt"]),
    custom_package = "com.example.hellobazel",
    manifest = "AndroidManifest.xml",
    resource_files = glob(["res/**"]),
    visibility = ["//app/src:__subpackages__"],
    deps = [
        artifact("com.google.android.material:material"),
    ],
)
