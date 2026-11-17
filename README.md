These are the IR codes for the HDMI switch marketed as: UGREEN 4K@60 Hz HDMI 2.0 Switch, 5-in-1-out, 5 Ports, Remote.  It is listed [here](https://nz.ugreen.com/products/90512).  The switch comes with a remote, which (like all IR remotes) sends codes to the HDMI switch.  This repo tells you what those codes are, so that you can use it with a learning remote or other IR transmitter of your choice.

The codes were captured using an Arduino Uno and a basic IR receiver LED, using the standard IR library [IRremote](https://docs.arduino.cc/libraries/irremote/).  The switch appears to use the standard NEC library, and I have just set out the captured commands below.  Some libraries want an 'inverted' command to send, which I have also set out below for convenience.

In addition to the commands, you will require the 'address' of the device.  This is also set out below.

## NEC IR Command Reference

| Button | Command (Hex) | Inverse Command (Hex) | Combined NEC Command |
|:---|:---:|:---:|:---:|
| Input 1 | `0x05` | `0xFA` | `0xFA05` |
| Input 2 | `0x09` | `0xF6` | `0xF609` |
| Input 3 | `0x07` | `0xF8` | `0xF807` |
| Input 4 | `0x1B` | `0xE4` | `0xE41B` |
| Input 5 | `0x08` | `0xF7` | `0xF708` |
| Next | `0x1F` | `0xE0` | `0xE01F` |

### Address Reference

| Field | Hex Value |
|:---|:---:|
| Address | `0x80` |
| Inverse Address | `0x7F` |
| Combined NEC Address | `0x7F80` |

*Inverse values are calculated using 8-bit bitwise inversion (XOR with `0xFF`).*
