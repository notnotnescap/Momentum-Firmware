The Protocols settings allow you to configure various communication protocols and hardware interfaces on your Flipper Zero. These settings can be found by pressing `UP` on the Desktop and navigating to `MNTM > Protocols`.

## [SubGHz](SubGHz)

Configure SubGHz radio settings:

- [`Frequency Configuration`](SubGHz#Frequency-Configuration): Manage radio frequencies
  - [`Use Defaults`](SubGHz#Use-Defaults): Toggle between default and custom frequency configuration
  - [`Static Freqs`](SubGHz#Static-Freqs): Configure static frequencies for SubGHz operation
  - [`Hopper Freqs`](SubGHz#Hopper-Freqs): Configure frequency hopping settings
- [`Advanced Settings`](SubGHz#Advanced-Settings): Configure advanced SubGHz options
  - [`Bypass Region Lock`](SubGHz#Bypass-Region-Lock): Toggle region lock bypass for SubGHz transmission
  - [`Extend Freq Bands`](SubGHz#Extend-Freq-Bands): Enable extended frequency bands. _**Locked**: must bypass region lock first._
- [`File Naming Prefix`](SubGHz#File-Naming-Prefix): Configure how file naming prefixes are applied

## [GPIO](GPIO)

Configure GPIO pin assignments for external connections:

- [`CC1101 SPI`](GPIO#CC1101-SPI): Configure pin assignment for CC1101 SubGHz radio
- [`HRF24 SPI`](GPIO#HRF24-SPI): Configure pin assignment for HRF24 radio module
- [`ESP32/8266 UART`](GPIO#ESP32/8266-UART): Configure pins for ESP32 or ESP8266 WiFi modules
- [`NMEA GPS UART`](GPIO#NMEA-GPS-UART): Configure pins for GPS modules with NMEA output
