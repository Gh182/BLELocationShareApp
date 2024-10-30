

[![Github All Releases](https://img.shields.io/github/downloads/Gh182/BLELocationShareApp/total.svg)]()


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

to set as Mocking Location:
```adb

adb shell appops set com.gh182.blelocationshareapp android:mock_location allow
```

to undo it:
```adb

adb shell appops set com.gh182.blelocationshareapp android:mock_location deny
```

to ckeck for Mocking Permission:
```adb

adb shell appops get com.gh182.blelocationshareapp android:mock_location
```

## Current bugs
1. Location Sender is a tough beast to kill:
    - The only way to stop Location Sender is by force closing the app (the stop button kills the service but it restarts)
    - Stopping and restarting Location Sender continues to send the previous location and the new one (resulting in a big mess)

2. Custom Power Settings is just a placeholder:
    - It will be implemented in the future with time frequency for sending/receiving and transmission power

3. So many other hidden gems you may find before me 
