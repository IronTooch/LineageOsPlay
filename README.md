# LineageOsPlay
A repo to keep all the things necessary to get a Raspberry Pi working with Lineage OS

Go to Settings > Other > About and take a note of the GSF ID or use Device ID
Open https://www.google.com/android/uncertified in any Web Browser
Log in with your Google Account
Enter the GSF ID
Solve the reCAPTCHA
Tap Register
Restart your Device
Wait a few Minutes
Open Google Play Store > Settings > About > Play Protect certificate still shows Device is not certified but it works


```shell
.\adb root
.\adb shell
GSERVICES_DB_PATH='/data/data/com.google.android.gsf/databases/gservices.db'
DEVID_OUTPUT_PATH='/storage/self/primary/Documents/device_id.txt'
ANDROID_ID_DBQUERY='select * from main where name = "android_id";'
sqlite3 $GSERVICES_DB_PATH "$ANDROID_ID_DBQUERY" | awk -F\| '{print $2};' > $DEVID_OUTPUT_PATH
```
