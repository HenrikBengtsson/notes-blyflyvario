# Bluefly Vario

The [Bluefly] is a vario that connects via Bluetooth. I've got the
[BlueFlyVario] with Bluetooth & GPS v22.  We ordered two on 2022-05-12
for 348 AUD (~240 USD) and received them 2022-05-29.


## Overview

* Weight: 48 g

* Dimensions: 58 x 36 x 16 mm

* Battery: ~8 hours (w/ Bluetooth & electromagnetic transducer
  running). 2-3 hours to fully charge.  Observation: A five-hour
  (sic!) flight took it from 100% down to 46% (3.828V; 3 beeps)

* Power button: click to turn ON, long press to turn OFF

* Power button when already ON: short press toggles audio ON, BUZZER,
  and OFF. This is easy to press during a flight.

* Battery status (during startup):

  1. First beep is a 1.0s beep at 4000 Hz
  2. Followed by 1-6 "battery" beeps (indicating 3.6-4.2 V)
  3. Followed by a short 0.2s beep at 4000 Hz

* LED lights:

  - BLUE (Bluetooth):
      + Flash every second => Bluetooth scanning
      + Double flash every second => connected
      + Solid => Bluetooth module is disabled (settings
        `SecondsBluetoothWait`).  Fix by restarting vario

  - ORANGE (GPS):
      + 1.0s flashing => GPS 3D fix
      + off => no GPS fix
      
  - GREEN:
      + During startup
      + When pressing button
      + When lift beep sounds (setting `GreenLED`)

  - RED:
      + Charging (turns off if full charged, but may stays on for
        trickle charging)

* Track logs:

  - Capacity: ~60 hours at one-second intervals
  - Always on: when GPS has 3D fix (ORANGE flash)


# Settings

You can _view_ the Bluefly settings via the [BlueFlyVario Android app]
(download [APK](https://blueflyvario.com/files/BlueFlyVario.apk),
[source
code](https://github.com/alistairdickie/BlueFlyVario_Android)).  The
app can be installed on Poke 3 (Android 10). Unfortunately, you
_cannot_ update the settings using this app.  If you try, the app
(v1.0) will crash when it tries to send the settings to Bluefly, and
if you restart the app you will find that your changes were never
applied.

To also _change_ settings, use the [BFV Desktop Java Application]
(download [ZIP](https://blueflyvario.com/files/BFVDesktop0.85.zip)),
which runs on any computer and operating system with Java
installed. The downside is that you need a computer, which you might
not bring on your flying trip.

The Poke 3 does not have a speaker. To make sure that the Bluefly
outputs vario sounds during your flight, make sure to change settings
to:

* `UseAudioWhenConnected`: `true` (default `false`)


[Bluefly]: https://www.blueflyvario.com/
[BlueFlyVario]: https://www.blueflyvario.com/
[BlueFlyVario Android App]: https://www.blueflyvario.com/software/
[BFV Desktop Java Application]: https://www.blueflyvario.com/software/
