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
    deps = ["//app/src/main:main_app"],
)

kt_android_library(
    name = "main_app",
    srcs = glob(["java/com/example/hellobazel/*.kt"]),
    custom_package = "com.example.hellobazel",
    manifest = "AndroidManifest.xml",
    resource_files = glob(["res/**"]),
    visibility = ["//app/src:__subpackages__"],
    deps = [
        artifact("androidx.appcompat:appcompat:1.6.1"),
        artifact("androidx.core:core-ktx:1.12.0"),
        artifact("com.google.android.material:material:1.10.0"),
        artifact("androidx.constraintlayout:constraintlayout:2.1.4"),
        artifact("androidx.lifecycle:lifecycle-runtime:2.6.1"),
    ],
)
