# Ch3

A small Swift package that exposes the [H3](https://github.com/uber/h3) to Swift.This library works directly with the C functions.

## Difference from upstream

This library has Ch3 updated to `4.3.0` whereas the upstream stayed `3.x`.

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

