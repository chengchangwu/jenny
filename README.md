# Jenny's Wallet

## Build

Install Android SDK uninstall under $HOME/Android.

Install JDK,

```
sudo apt-get update
sudo apt-get install openjdk-11-jdk
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64/jre
```

Set udev rules according to http://developer.android.com/tools/device.html .

```
sudo usermod -aG plugdev $LOGNAME
sudo apt-get install android-sdk-platform-tools-common
```

Set environment variables，

```
export ANDROID_SDK_ROOT=$HOME/Android/Sdk
export NDK_HOME=$HOME/Android/Sdk/ndk/22.1.7171670
export PATH=$ANDROID_SDK_ROOT/platform-tools:$PATH
```

Run,

```
cargo android run
```

- The `#[mobile_entry_point]` annotation generates all the boilerplate `extern` functions for mobile.
- Logging on Android is done using `android_logger`.

To run this on desktop, just do `cargo run` like normal! For mobile, use `cargo android run` and `cargo apple run` respectively (or use `cargo android open` and `cargo apple open` to open in Android Studio and Xcode respectively).

