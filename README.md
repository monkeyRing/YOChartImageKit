# YOChartImageKit

[![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)

Since watchOS does not have _UIView_ class, YOChartImageKit draws a _UIImage_ of a chart with given values.  
Values and colors can be customized.

![watchos](https://raw.githubusercontent.com/yasuoza/YOChartImageKit/assets/images/watchos/all.png)

![ios](https://raw.githubusercontent.com/yasuoza/YOChartImageKit/assets/images/ios/all.png)

## Configuration

Followng section describes the way to draw charts.  
If you want to try YOChartImageKit, open `YOChartImageKit.xcodeproj`. Eample applications are available for iOS and watchOS.

### Line chart

#### solid

![](https://raw.githubusercontent.com/yasuoza/YOChartImageKit/assets/images/watchos/0_solid_line.png)

```swift
let image = YOLineChartImage()
image.strokeWidth = 4.0              // width of line
image.strokeColor = randomColor()    // color of line
image.values = [0.0, 1.0, 2.0]       // chart values
image.smooth = false                 // disable smooth line
image.drawImage(frame, scale: scale) // draw a image
```

#### smooth

![](https://raw.githubusercontent.com/yasuoza/YOChartImageKit/assets/images/watchos/0_smooth_line.png)

```swift
let image = YOLineChartImage()
image.strokeWidth = 4.0              // width of line
image.fill = randomColor()           // color of area
image.values = [0.0, 1.0, 2.0]       // chart values
// image.smooth = true               // [default] draws a smooth line
image.drawImage(frame, scale: scale) // draw a image
```

### Bar chart

![](https://raw.githubusercontent.com/yasuoza/YOChartImageKit/assets/images/watchos/1_bar.png)

```swift
let image = YOBarChartImage() 
image.fillColor = randomColor()      // color of bars
// image.barPadding = 2.0            // [optional] padding of bars. 
image.values = [0.0, 1.0, 2.0]       // chart values
image.drawImage(frame, scale: scale) // draw a image
```

### Donut chart

![](https://raw.githubusercontent.com/yasuoza/YOChartImageKit/assets/images/watchos/2_donut.png)

```swift
let image = YODonutChartImage()
image.donutWidth = 16.0                           // width of donut
// image.labelText = "LABEL"                      // [optional] center label text
// image.labelColor = UIColor.whiteColor()        // [optional] center label color
image.values = [10.0, 20.0, 70.0]                 // chart values
image.colors = (0..<3).map { _ in randomColor() } // colors of pieces
image.drawImage(frame, scale: scale)              // draw a image
```

## Framework Requirements

- watchOS ~> 2.0

## Build Requirements

- Xcode >= 7.0

## Example Application

Example applications are available for both iOS and watchOS.  
Open `YOChartImageKit.xcodeproj` with Xcode and build demo app.
