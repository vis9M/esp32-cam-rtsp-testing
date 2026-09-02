# ESP32-CAM RTSP Performance Testing

Performance evaluation of multiple ESP32-CAM devices
in an RTSP streaming system.

## Hardware

- ESP32-CAM
- OV2640 camera
- ESP32-CAM-MB programmer/development board

## Progress

### Stage 1 - Basic camera setup
- [ ] Install development environment
- [ ] Connect ESP32-CAM
- [ ] Upload test firmware
- [ ] Connect ESP32-CAM to Wi-Fi
- [ ] Get IP address
- [ ] View camera stream in browser

### Stage 2 - RTSP
- [ ] Connect one camera to RTSP system
- [ ] View stream using RTSP client

### Stage 3 - Multiple cameras
- [ ] Two cameras
- [ ] Three cameras
- [ ] Four cameras

### Stage 4 - Performance testing
- [ ] FPS
- [ ] Latency
- [ ] Bandwidth
- [ ] Stability

## Problems

Connecting one ESP32-CAM to the laptop, programming it, connecting to Wi-Fi and seeing live video in browser

### ESP3232-CAM upload fails with "No serial data received"

**Problem**

When uploading firmware through Arduino IDE, compilation completed successfully, but the upload failed with:

> Failed to connect to ESP32: No serial data received.

The correct COM port was selected and the ESP32-CAM was connected through USB

**Solution** 

The ESP32 needed to be placed into flashing/download mode manually following these steps.

1. Hold the **FLASH** button
2. Press and release the **RST** button.
3. Keep **FLASH** pressed briefly.
4. Release **FLASH**.
5. Upload the sketch from Arduino IDE.

After entering flashing mode correctly, the firmware uploaded successfully.

**Verification** 

The Serial Monitor was opened at **115200** baud** and the **RST** button was pressed.

The ESP32 successfully printed:

`ESP32 is working!`
