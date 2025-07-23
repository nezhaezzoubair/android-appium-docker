# android-appium-docker
This Docker image is designed to run automated mobile tests on Android emulators using **Appium**, **Robot Framework**, and **UIAutomator2**. It is built on top of Google's official Android emulator image.


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

If KVM is correctly enabled, the command will return:
