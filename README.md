# PapilonSavunmaActiveLivenessiOS

This package is library for Active Liveness. This library detects the face and checks the head and eye movements to check the face is live or not.



## Installation

PapilonNFCReaderiOS is available through [CocoaPods](https://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod 'PapilonActiveLivenessiOS'
```

## Usage

This SDK has five steps to control liveness. These steps are;
1. Face Recognition
2. Blinking Detection
3. Looking Left Check
4. Looking Right Check
5. Smiling Detection

Simply create an object with class `LivenessDetection`, with initializer `currentStepInit`. This currentStep should be 1 at the start. As the current step changes the steps that are given above are completing. 

```swift
let livenessDetector = LivenessDetection(currentStepInit: 1)
```

Then you need to call detectFace function and feed it with the video captured `UIImage`
```swift 
livenessDetector.detectFace(UIImage)
```

The full active liveness check will finish when `livenessDetector.currentStep` is equals to six and that means it is successful.


We are working on to develop with more optional usage. For now, you can control all the steps that are given above.


## License

See the LICENSE file for more info.
