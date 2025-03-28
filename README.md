# coral-usb-init
Docker container that initializes the Google Coral USB TPU

The device is first identified as 1a6e:089a Global Unichip Corp device. After initialization its VID and PID changes and its identified as a 18d1:9302 Google Inc device after which it can be used with Frigate or other software.

Usage:

```docker build -t "coral-fix" .```

```docker run --rm --device /dev/bus/usb:/dev/bus/usb coral-fix```

The first run will return an error but the device will be initialized. You will need to run the container again if the device has been restarted.

Based on this blog post https://www.diyengineers.com/2024/05/18/setup-coral-tpu-usb-accelerator-on-raspberry-pi-5/
