# Changelog

## 0.0.11

- Added MQTT Support

## 0.0.10.1

- Removed while loop and added an assertion if we do not get the data after the Usage data table loads

## 0.0.9.5

- Updated Docker file to no longer install software-properties-common and instead only install necessary packages for Playwright and Firefox

## 0.0.9.4

- Now using expect as recommended by Playwright API documentation instead of networkidle. This allows the while loop to exit once the raw plan data and usage data is received. Then the data is processed outside the while loop and pushed to the Home Assistant sensor

## 0.0.9.3

- Login logic and usage data gathering it now based on https://www.xfinity.com/learn/internet-service/auth page instead of https://customer.xfinity.com/#/devices#usage
- Added a lot more page checks to make sure page is properly loaded
- Session data is now based on the OAuth JWT token
- Added PyJWT library to Docker file to allow for JWT token processing
- Need to cleanup any old references to the previous logic

## 0.0.9.1

- Changed to keyboard enter instead of clicking on sign_in button

## 0.0.9

- Encypt the Xfinity password in the log file when in debug mode
- Added debug_support logging option to gather page source and screenshots when extra troubleshooting is needed.
- Version bump pip requirements:
    - playwright to 1.44.0
    - typing-extensions to 4.12.0
    - pyee to 11.1.0
    - greenlet to 3.0.3
    - tenacity to 8.3.0
    - requests to 2.32.3

## 0.0.8

- Added blueprint to help users maintain sensor data between Home Assistant Restarts

## 0.0.7

- Added timestamp to logging output
- Addon will write sensor data to backup file it will use to restore the sensor upon startup.
- Adding documentation regarding how the sensor works if the addon isn't running.

## 0.0.6

- Added retry logic to prevent infinite page reloading when usage data is missing. [#2](https://github.com/thor0215/hassio-xfinity-usage/issues/2)

## 0.0.5

- Playwright sometimes has an uncaught exception in the node.js layer and script will not crash, but stops processing. Added logic to restart Playwright every 12 hrs

## 0.0.4

- Reformatted log output
- Added comments in code to better explain what's happening
- Added English translation for configuration options

## 0.0.3

- Updated Xfinity logo

## 0.0.2

- Adjusted logic so that the sensor will only be updated when the session is active and the usage data is populated

## 0.0.1

- Initial release
