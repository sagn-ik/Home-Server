# Home Assistant OS Setup on Raspberry Pi

## Requirements
- Raspberry Pi [using 3B for this build]
- MicroSD card (8gig or larger)
- Power supply for Raspberry Pi
- Ethernet cable (recommended for stability)
- Computer to flash the OS

## Step 1: Download Home Assistant OS
1. Visit the official Home Assistant website: [https://www.home-assistant.io/installation/](https://www.home-assistant.io/installation/)
2. Download the appropriate Raspberry Pi image (e.g., `Raspberry Pi 4 64-bit` for RPi4).

## Step 2: Flash Home Assistant OS to the SD Card
1. Download and install [balenaEtcher](https://www.balena.io/etcher/).
2. Insert your microSD card into the computer.
3. Open balenaEtcher and select:
   - The HAOS image you downloaded.
   - The microSD card as the target.
   - Click **Flash** and wait for completion.
4. Safely eject the SD card.

## Step 3: Boot Home Assistant OS
1. Insert the microSD card into the Raspberry Pi.
2. Connect the Raspberry Pi to power.
3. (Optional) Connect an Ethernet cable for a stable network connection.
4. Wait a few minutes while HAOS initializes.

## Step 4: Access Home Assistant
1. On your computer, open a web browser.
2. Enter: `http://homeassistant.local:8123/`
   - If this doesn’t work, find the Raspberry Pi’s IP address and enter `http://<YOUR_PI_IP>:8123/`
3. Follow the on-screen setup instructions.

## Step 5: Configure Home Assistant
- Create a user account.
- Set up your location and timezone.
- Add integrations for smart home devices.

## Optional: Enable SSH Access
1. Create an empty file named `ssh` (without extension) on the **boot** partition of the microSD card.
2. Reboot the Raspberry Pi.
3. Connect via SSH using:
   ```sh
   ssh root@homeassistant.local
   ```

## Troubleshooting
- If Home Assistant doesn’t start, ensure the SD card was flashed correctly.
- Use an Ethernet connection if Wi-Fi setup is problematic.
- Check the Home Assistant forums for additional help.

## Additional Resources
- [Home Assistant Documentation](https://www.home-assistant.io/docs/)
- [Community Forums](https://community.home-assistant.io/)
