# CHCircleGaugeView

A configurable chart that depicts the value of a measurement using a subtle animation.

[![Version](https://cocoapod-badges.herokuapp.com/v/CHCircleGaugeView/badge.png)](http://cocoadocs.org/docsets/CHCircleGaugeView)
[![Platform](https://cocoapod-badges.herokuapp.com/p/CHCircleGaugeView/badge.png)](http://cocoadocs.org/docsets/CHCircleGaugeView)

<img src="https://github.com/chaione/CHCircleGauge/raw/master/miscellaneous/screenshots/CHCircleGaugeView_ExampleAnimation01.gif">

## Installation

### CocoaPods

CHCircleGaugeView is available through [CocoaPods](http://cocoapods.org), to install it simply add the following line to your Podfile:

`pod "CHCircleGaugeView"`

### Manually

To install manually, just copy everything in the `CHCircleGaugeView` directory into your Xcode project.

_**Important:**_ If your project doesn't use ARC you must add the `-fobjc-arc` compiler flag to all CHCircleGaugeView implementation files in Target Settings > Build Phases > Compile Sources.

## Usage

Instantiate like any other view and customize it as needed:

```objective-c
- (void)viewDidAppear:(BOOL)animated {
    [super viewDidAppear:animated];
    
    CGRect frame = CGRectMake(0, 0, 200, 200);
    CHCircleGauge *circleGauge = [[CHCircleGauge alloc] initWithFrame:frame];
    [self.view addSubView:circleGauge];
    
    [circleGauge setValue:0.5 animated:YES];
}
```

### States

There is a `state` property of type `CHCircleGaugeState` that determines how to display a few things.

* `CHCircleGaugeStateNA`: "n/a" is displayed in the center of the circle and the gauge inside the track will not be present. The displayed string can be changed by setting the `notApplicableString` property on the gauge.
* `CHCircleGaugeStatePercentSign`: "%" is displayed in the center of the circle and the gauge inside the track will not be present. The displayed string can be changed by setting the `noDataString` property on the gauge.
* `CHCircleGaugeStateScore`: A whole number (with an optional units suffix) is displayed in the center of the circle and the gauge inside the track will represent the value.

Modifying or setting the `value` property will automatically cause the state to switch to `CHCircleGaugeStateScore`.

### Setting Values

To change the value of the gauge you can call `setValue:animated:` or set `value`.

### Configuration

The gauge can easily be configured by adjusting public properties:

* `trackTintColor`: The color shown for the portion of the gauge that is always filled.
* `gaugeTintColor`: The color shown on top of `trackTintColor` for the portion of the gauge that varies based on the `value` property.
* `textColor`: The color of the text.
* `font`: The font of the text.
* `trackWidth`: The width for the portion of the gauge that is always filled. Defaults to a value of 0.5.
* `gaugeWidth`: The width for the portion of the gauge that varies based on the `value` property. Defaults to a value of 2.
* `unitsString`: String that is a suffix on the `value`. This string is meant to be just a few characters long. Defaults to `nil`.
* `notApplicableString`: The text shown when the state of the gauge is `ChCircleGaugeStateNA`. Defaults to "n/a".
* `noDataString`: The text shown when the state of the gauge is `CHCircleGaugeStatePercentSign`. Defaults to "%".

## Contributing

Pull request are welcomed. To add functionality or to make changes:

1. Fork this repo.
2. Open `CHCircleGuageViewExample.xcworkspace` in the `CHCircleGuageViewExample` directory.
3. Make changes to the necessary files in the `CHCircleGaugeView` group.
4. Ensure new public methods are documented.
5. Submit a pull request.

## Authors

Created by [Matthew Morey](http://matthewmorey.com), [Rogelio Gudino](http://cananito.com/), and other [contributors](https://github.com/chaione/CHCircleGaugeView/graphs/contributors).

## License

CHCircleGaugeView is available under the MIT license. See the [LICENSE](https://github.com/chaione/CHCircleGaugeView/LICENSE) file for more information. If you're using CHCircleGaugeView in your project, attribution would be nice.