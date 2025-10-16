### HackTheBox- Android Fundamentals - Android Debug Bridge
1. **install apk file**
  ![](images/install-apk.png)

2. **unzip the file**
   ```bash
    unzip myapp_adb.zip
   ```
   ![](images/unzip-apk-zip.png)

3. **display device that connected** 
   ![](images/conn-devices.png)

4. **push apk file in device**
   ```bash
    adb push ./myapp.apk /sdcard/Download/
   ```
5. **check it's exists in device**
   ```bash
      adb shell -l /sdcard/Download/
   ```
   ![](images/comfirm-its-push.png)

6. **install apk**
   ```bash
       adb install myapp.apk
   ```
   ![](images/success-install.png)

7. **gain shell to search for flag path by**
   ```bash
     find ~ -type f -name "flag.txt"
   ```
   ![](images/flag-1.png)

```And find flag-2```
![](images/second-path-flag2.png)
![](images/flag-2.png)

and extract flag3
![](images/flag-3.png)

----

**Mission Done**
![](images/Done-adb.png)