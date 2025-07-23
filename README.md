# android-appium-docker
This Docker image is tailored for running automated Android mobile tests using Appium, Robot Framework.
It is especially suitable for use in CI/CD pipelines (e.g., GitLab CI).


## Prerequisites

Make sure the following are installed and configured on your host machine:

- Docker
- Android Debug Bridge (adb)
- A Linux machine (physical or VM with Hyper-V or VirtualBox) with **KVM** enabled

### How to check if KVM is available and enabled:

```bash
sudo apt update
sudo apt install cpu-checker
kvm-ok
```

If KVM is correctly enabled, the command will return:
```bash
INFO: /dev/kvm exists
KVM acceleration can be used
```

## Run the container
```bash
sudo docker run -d \
  -e ADBKEY="$(cat ~/.android/adbkey)" \
  --device /dev/kvm \
  -p 8554:8554/tcp \
  -p 5555:5555/tcp \
  --name android-emulator \
  nezhaa/android-appium-image:latest
```
⏳ Wait a few minutes for the Android emulator to boot up.

## Connect to the emulator via ADB
```bash
adb connect localhost:5555
```
You should see:
```bash
connected to localhost:5555
```

## Display the emulator (optional)

You can visualize the emulator's screen using scrcpy.

Install scrcpy:
```bash
sudo apt install scrcpy
```
Launch the display:
```bash
scrcpy --serial localhost:5555
```













