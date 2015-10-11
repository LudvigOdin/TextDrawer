# TextDrawer
[![Swift 2.0](https://img.shields.io/badge/Swift-2.0-orange.svg?style=flat)](https://developer.apple.com/swift/)
![Version Status](http://img.shields.io/cocoapods/v/TextDrawer.png) ![license MIT](http://img.shields.io/badge/license-MIT-orange.png) [![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)

*TextDrawer, is a UIView allows you to add text, with gesture, on UIView, or UIImage.*

## About

Annotating Images

TextDrawer is the easiest way to add text to `UIImage` with a touch interface. You can add text, with resizable, move, and rotate gesture with `UIGestureRecognizer`.
With TextDrawer, it's easily save notes on top of a `UIImage`.

![ScreenShot](http://share.gifyoutube.com/vJAB4g.gif)

## Requirements

* iOS 8
* Swift 1.2

## Installation

#### [CocoaPods](http://cocoapods.org)

````ruby
use_frameworks!
pod 'TextDrawer', '~> 1.0.6'
````

#### [Carthage](https://github.com/Carthage/Carthage)

````bash
github "remirobert/TextDrawer"
````

#### Manually

1. Clone this repo and add the `TextDrawer/TextDrawer.xcodeproj` to your project
2. Select your project app target "Build Phases" tab
3. Add the `TextDrawer.framework` to the "Link Binary With Libraries"  
4. Create a new build phase of type "Copy Files" and set the "Destination" to "Frameworks"
5. Add the `TextDrawer.framework` and check "Code Sign On Copy"

For an example, see the demo project included in this repo.
To run the example project, clone the repo, and run `pod install` from the Example directory.

## Getting Started

````swift
import TextDrawer
````

##### Design

This framework is composed on different parts.
The first one is the `TextEditView`. It allows you to edit the text. it is composed of a `UITextView`, and manage the keyboard notifications.
Next, `DrawTextView`, is a `UIView`, showing your text in the view.
And, `TextDrawer`, it contains the above views. It allows to configure some parameter (like font, size, color, etc ...). All the gestures are managed here.

## Usage
Add an instance of `TextDrawer` above an `UIImageView`, or an another `UIView` (with an optional clear background). Adjust the size and layout of `TextDrawer` however you'd like. `TextDrawer` uses, `Masonry` to manage auto-layout. You don't have anything to do, after that. `TextDrawer` will handle, the gesture for you. See this screen bellow.

<img width="989" alt="screen shot 2015-07-21 at 14 37 45" src="https://cloud.githubusercontent.com/assets/3276768/8800821/398a416a-2fb6-11e5-9029-52df374d45d7.png">

Render the `TextDrawer` to an `UIImage` outup:

```Swift
// draw the TextDrawer view on an UIImageView
let image = drawTextView.renderTextOnView(imageViewBackground)

// render the TextDrawer View to UIImage
let image = drawTextView.render()

// render the TextDrawer View directly on an UIImage
let image = drawTextView.renderTextOnImage(image)
```

Clear the `TextDrawer` view:

```Swift
self.textDrawer.clearText()
self.textDrawer.resetTransformation()
```

`TextDrawer` configuration:

```Swift
drawTextView.font = UIFont.systemFontOfSize(34)
drawTextView.textColor = UIColor.whiteColor()
drawTextView.textAlignement = NSTextAlignment.Center
drawTextView.textBackgroundColor = UIColor.redColor()
drawTextView.text = "test input"
drawTextView.textSize = 40
```

## Contributors

* [Rémi ROBERT](https://github.com/remirobert), creator. ( ﾟヮﾟ)

## License

`TextDrawer` is released under an [MIT License][mitLink]. See `LICENSE` for details.

>**Copyright &copy; 2015 Rémi ROBERT.**

*Please provide attribution, it is greatly appreciated.*

[mitLink]:http://opensource.org/licenses/MIT
