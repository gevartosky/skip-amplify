# SkipAmplify

This package provides support for [AWS Amplify](https://aws.amazon.com/amplify/)
for dual-platform [Skip](https://skip.dev) projects. It provides a unified
interface for the
[Amplify Swift SDK](https://github.com/aws-amplify/amplify-swift)
and
[Amplify Kotlin SDK](https://github.com/aws-amplify/amplify-android).

## Setup

To include this framework in your project, add the following
dependency to your `Package.swift` file:

```swift
let package = Package(
    name: "my-package",
    products: [
        .library(name: "MyProduct", targets: ["MyTarget"]),
    ],
    dependencies: [
        .package(url: "https://source.skip.dev/skip-amplify.git", "0.0.0"..<"2.0.0"),
    ],
    targets: [
        .target(name: "MyTarget", dependencies: [
            .product(name: "SkipAmplify", package: "skip-amplify")
        ])
    ]
)
```

## Building

This project is a free Swift Package Manager module that uses the
[Skip](https://skip.dev) plugin to transpile Swift into Kotlin.

Building the module requires that Skip be installed using
[Homebrew](https://brew.sh) with `brew install skiptools/skip/skip`.
This will also install the necessary build prerequisites:
Kotlin, Gradle, and the Android build tools.

## Testing

The module can be tested using the standard `swift test` command
or by running the test target for the macOS destination in Xcode,
which will run the Swift tests as well as the transpiled
Kotlin JUnit tests in the Robolectric Android simulation environment.

Parity testing can be performed with `skip test`,
which will output a table of the test results for both platforms.

## License

This software is licensed under the
[Mozilla Public License 2.0](https://www.mozilla.org/MPL/).

