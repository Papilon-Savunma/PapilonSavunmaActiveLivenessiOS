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

Simply create an object with class `LivenessDetection`, with initializer `detectionOptionsInit`. There are four options;
- `HeadRot`: Only left-right head rotation movement check
- `Blink_HeadRot`: Eye blink and left-right head rotation movement check
- `HeadRot_Smile`: Left-right head rotation movement and smiling check
- `FullPack`: Eye blink, left-right head rotation movement and smiling check

For instance;

```swift
let livenessDetector = LivenessDetection(detectionOptionsInıt: .FullPack)
```

Then you need to call detectFace function and feed it with the video captured `UIImage`
```swift 
livenessDetector.detectFace(UIImage)
```

The full active liveness check will finish when `livenessDetector.livenessSuccess` is `true` and that means it is successful. For instance; 

```swift 
if livenessDetector.livenessSuccess == true {
  print("Active liveness check completed successfully")
}
```

Also, you can check wheter these steps are checked or not with the boolen values; 
- `isFaceDetected`
- `isBlinkDetected`
- `isRotateLeftDetected`
- `isRotateRightDetected`
- `isSmileDetected`

*All these values are default false.*


## Notes
- In the frames, if any face is recognized, currentStep property will be 1 which means process will be restarted.
- In the frames, if there are more than one face, currentStep property will be 1 which means process will be restarted.
- We are working on to develop with more optional usage. For now, you can control all the steps that are given above.


## License

See the LICENSE file for more info.
