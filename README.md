# android-bazel-kotlin-template

this is a POC / template when converting a default generated android studio default project to bazel

- Kotlin 1.8.1
- Material Design 1.10

## Note
Using Bazel 7 pre-release to handle material design macro type resource, see https://github.com/bazelbuild/bazel/issues/17345

### Build using bazel
`bazel build //app/src/main:app`
