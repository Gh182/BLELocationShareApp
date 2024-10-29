# Why?
Boox made the Tab Ultra C Pro without GNSS module, so here it is an app to send location from another device through BLE and use it as mock location.
## Functionalities
The app can be used as both sender and receiver. Remember to allow all the permissions to make it work properly (thy're not always appearing on opening or after installing... W.I.P.)

The app uses these permissions:
- Notifications
- Nearby devices (allow)
- Location (allow all the time)
### Sender
The app can broadcast the actual position (latitude, longitude, altitude and accuracy) of the sender device or an arbitrary one.
### Receiver
The app scans periodically BLE messages in search for a new location message and use it as Mock Location.

It is needed to set the app as Mock Location Provider in Android developer Settings or through ADB:
- to set as Mocking Location: ```adb shell appops set com.gh182.blelocationshareapp android:mock_location allow```
- to undo it: ```adb shell appops set com.gh182.blelocationshareapp android:mock_location deny```
- to ckeck for Mocking Permission: ```adb shell appops get com.gh182.blelocationshareapp android:mock_location```
