# XIAO MG24 Sense IMU Data Logger

This project is an Arduino sketch for the XIAO MG24 Sense board that logs motion data from the LSM6DS3 IMU sensor. It supports multiple activities such as walking, running, solat (prayer), and more.

## Features

- **IMU Sensor (LSM6DS3):** Reads accelerometer and gyroscope data at 100 Hz sample rate.
- **Real-Time Clock (PCF8563):** Provides accurate timestamps for data logging.
- **OLED Display:** Shows current activity, status messages, initialization progress bar, and countdown timer with large fonts.
- **SD Card Storage:** Organizes data files by date and activity type, saving sensor data in CSV format.
- **User Interaction:**
  - *Short Button Press:* Cycles through different activity modes.
  - *Long Button Press:* Starts or stops data collection with a 5-second countdown and audible beeps.
- **Progress Bar:** Displays a smooth, visually centered initialization progress bar during setup.
- **Countdown with Sound:** Before data collection starts, a countdown from 5 to 1 is shown with beeps, followed by a "GO" signal with a long beep that immediately triggers data logging.
- **Data Filtering:** Applies a simple low-pass filter to sensor data for noise reduction.
- **Error Handling:** Displays error messages on the OLED and plays error sounds if initialization or file operations fail.
- **Debug Mode:** Optional serial output for debugging sensor readings and system status.

## Workflow

1. **Setup Phase:**
   - Initializes OLED, IMU, RTC, and SD card.
   - Shows a smooth progress bar indicating initialization status.
   - Attaches button interrupt for user input.
   - Plays a startup sound.

2. **Idle Mode:**
   - Displays current activity and status.
   - Waits for user input.

3. **User Input:**
   - Short press cycles through activities.
   - Long press triggers a countdown with beeps, then starts data collection.

4. **Data Collection:**
   - Samples IMU data at 100 Hz.
   - Applies filtering to raw sensor data.
   - Logs timestamped data to SD card in CSV format.
   - Updates OLED with sample count and recording status.
   - LED indicator blinks during sampling.

5. **Stop Collection:**
   - Stops data logging on long button press.
   - Closes file and displays saved sample count.

## Hardware Connections

- **Button:** Connected to pin D1 with internal pull-up.
- **Buzzer:** Connected to pin D3.
- **SD Card:** SPI interface with chip select on pin D2.
- **LED:** Built-in LED used as sampling indicator.
- **IMU and RTC:** Connected via I2C.

## Usage

- Short press the button to cycle through activities.
- Long press the button to start data collection after a countdown.
- Long press again to stop data collection.

## Author

[Your Name]

## License

[Specify your license here]
