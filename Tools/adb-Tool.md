### adb(Android Debug Bridge)
- is a command-line tool that allows you to communicate with an Android device (emulator or physical device)

- used for 
  1. debugging
  2. development
  3. testing purposes
  4. Accessing Activities

### How the ADB connection process works
1. The ADB client checks whether the `adb server` is running on the host machine. If not, it starts the server process, which listens on TCP port 5037.
2. The ADB server locates the connected emulators by scanning the odd-numbered ports from 5555 to 5585 and sets up connections with the ones running an ADB daemon (`adbd`).


### install adb in linux and windows
- linux 
   ```bash
     apt install abd
  ```
- windows
  ```powershell
      C:\> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
      C:\> iex (New-Object System.Net.WebClient).DownloadString('https://get.scoop.sh')
      C:\> scoop bucket add extras
      C:\> scoop install adb
  ```

---

### important command
1. **see connected devices**
```bash
     adb devices  
```

2. **Select specific device**
```bash
   adb -s <serial> command 
```

3. **connect by wifi if the device on the same network**
```bash
   adb -s ip:port <command>
```

4. **root the device**
```bash
   adb root
```

5. **open shell**
```bash
   adb shell
```

1. **push filr to device**
```bash
    adb push <local> <remote>
```

1. **pull file from device**
```bash
   adb pull /sdcard/Download/<file-name> ~/directory/
```

1. **install apk**
```bash
   adb install myapp.apk
```

1. **reboot device**
```bash
  adb reboot
```

1.  run specific command by emulator
```bash
   adb -s <emulator-name> shell
```

1.  detect package name
```bash
   adb -s <serial> shell pm list package | grep mobile_pentest_lab
```

1.   open application
```bash
  adb -s <serial> shell am start -n com.example.mobile_pentest_lab/.MainActivity

```



----

### emulator
1. show avaliable emulator
```bash
 emulator -list-avds
```

2. run specific avd
```bash
   emulator -avd <>
```