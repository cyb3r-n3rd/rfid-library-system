# RFID Library Management System

An RFID-based library management system I built for my college library — tap a card to issue
or return a book, with the catalogue tracked on a connected PC. It was recognised as one of
the best projects of the college.

![demo placeholder](images/demo.png)

## Bill of materials

| Part | Why | Approx. price | Where |
| --- | --- | --- | --- |
| Arduino Uno / Nano | microcontroller | ₹400–700 | any electronics shop |
| MFRC522 RFID reader + cards/tags (13.56 MHz) | read/write the cards | ₹150–250 | [generic MFRC522 kit](https://www.amazon.in/s?k=mfrc522) |
| 16x2 I²C LCD | on-device status | ₹200 | any shop |
| Buzzer + 2 LEDs (green/red) | issue / return feedback | ₹60 | any shop |
| Jumper wires + breadboard | wiring | ₹150 | any shop |

## Wiring (MFRC522 → Arduino Uno)

| MFRC522 | Arduino |
| --- | --- |
| SDA/SS | D10 |
| SCK | D13 |
| MOSI | D11 |
| MISO | D12 |
| RST | D9 |
| 3.3V | 3.3V |
| GND | GND |

![wiring placeholder](images/wiring.png)

## How it works

1. Each book and each member has a unique RFID tag.
2. The Arduino reads the tag UID via SPI and sends it to the desktop app over serial.
3. The desktop side matches the UID against the catalogue, records the issue/return with a
   timestamp, and the Arduino gives a green LED + short beep for success or red for an error.

## Repo layout

```
arduino/      # the Arduino sketch (.ino)
desktop/      # the serial-side catalogue app
docs/         # schematic and notes
images/       # photos and diagrams
```

> Code and schematics are being tidied up and will be committed here. Open an issue if you
> want a specific part first.

Built by **Shivam Verma (cyb3r_n3rd)** —
[portfolio](https://cyb3r-n3rd.github.io/portfolio/) ·
[LinkedIn](https://www.linkedin.com/in/shivamvermacyber)
