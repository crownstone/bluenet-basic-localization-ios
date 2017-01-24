# bluenet-basic-localization-ios
Basic version of the bluenet localization for iOS.

To use, you can use the framework in the release found here:
https://github.com/crownstone/bluenet-basic-localization-ios/releases

Download the framework, place it in the ./Carthage/Build/iOS folder and include it like a Carthage framework.

This module is made to be used with the BluenetLibIOS which is found here:
https://github.com/crownstone/bluenet-lib-ios

To implement your own classifier, you have to make sure your classifier adheres to the following protocols:

```swift
public protocol LocalizationClassifier {
    func classify(_ inputVector: [iBeaconPacketProtocol], referenceId : String?) -> String?
}

// dataformat of the ibeacon packet that is inserted into the classify method
public protocol iBeaconPacketProtocol {
    var uuid : String { get }
    var major: NSNumber { get }
    var minor: NSNumber { get }
    var rssi : NSNumber { get }
    var distance : NSNumber { get }
    var idString: String { get }
    var referenceId: String { get }
}
```
