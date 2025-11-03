# Ch3

A small Swift package that exposes the [H3](https://github.com/uber/h3) to Swift.This library works directly with the C functions.

## Difference from upstream

This library has Ch3 updated to `4.3.0` whereas the upstream stayed `3.x`.

## Installation (Swift Package Manager)

### Using Xcode

- Select your project in Xcode, then go to the “Package Dependencies” tab.
- Click the `+` button, paste `https://github.com/DJBen/Ch3.git` into the search field, and press Return.
- Choose the latest release (or a specific version) and add the package to the relevant targets.

### Using Package.swift

Add the dependency to your `Package.swift`:

```swift
dependencies: [
    .package(url: "https://github.com/DJBen/Ch3.git", from: "4.3.0")
],
targets: [
    .target(
        name: "YourApp",
        dependencies: [
            .product(name: "Ch3", package: "Ch3"),
        ]
    )
]
```

## Example

```swift
# Create coordinate and get the H3 index
var coord = GeoCoord(lat: degsToRads(40.661), lon: degsToRads(-73.944))
let index = geoToH3(&coord, 10)

# Get the string representation of the index
let cString = strdup("")
h3ToString(self, cString, 17)
print("\(String(cString: cString!))")
```
