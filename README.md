# jlink-tagConnect-adapter

![License](https://img.shields.io/badge/license-GNU%20GPL%20v3.0-blue.svg)
![GitHub last commit](https://img.shields.io/github/last-commit/Fescron/jlink-tagConnect-adapter.svg)
![GitHub Release Date](https://img.shields.io/github/release-date/Fescron/jlink-tagConnect-adapter.svg)
![GitHub release](https://img.shields.io/github/release/Fescron/jlink-tagConnect-adapter.svg)

20 pin SWD/JTAG J-Link to 10 pin Tag-Connect adapter board

<br/>

<img src="documentation/3D-render-front.png" height="280" alt="Front"> <img src="documentation/3D-render-back.png" height="280" alt="Back">

<br/>

## 1 - Quick links

- [Schematic](documentation/jlink-tagConnect-adapter.pdf)
- [Tag-Connect datasheet](documentation/TC2050-IDC-Datasheet.pdf)

<br/>

## 2 - Usage

One can simply plug this adapter board in a [J-Link debugger](https://www.segger.com/products/debug-probes/j-link/models/j-link-base/) along with a [10 pin Tag-Connect adapter cable](http://www.tag-connect.com/TC2050-IDC) on the IDC connector. The cable will then have the approximate pinout (`RXD` instead of pin 7 `NC`) of the [standard 9-pin Cortex-M SWD/JTAG pinout](https://www.segger.com/products/debug-probes/j-link/accessories/adapters/9-pin-cortex-m-adapter/) from J-Link. The pinout of the Tag-Connect cable can be seen on the picure below.

<img src="documentation/Tag-Connect-pinout.png" height="200" alt="Tag-Connect pinout">

**Pushbutton** `SW1` can be used to mannually **reset** the target board. A **DC-DC converter** can be plugged in on header `J4` to supply the target board with the correct voltage using the 5V supply of the J-Link programmer. If the pinout of the converter doesn't match `VIN - VOUT - GND`, the last two pins can be changed around by swapping the solder joints on `JP1` and `JP2` on the bottom of the adapter. Then the pinout `VIN - GND - VOUT` will be selected.

**Jumpers** `J6` and `J7` can also be used to swap some pinouts around. `J6` connects `pin 4` on the Tag-Connect cable to `RXD` or *doesn't connect it*. `J7` connects `pin 5` on the Tag-Connect cable to *nothing* or to `nTRST` (JTAG).

<br/>

## 3 - BOM

|  Component  |  Value  |
| ---------- | --------- |
| J1 | 01x07 Male pinheader |
| J2 | 01x03 Male pinheader |
| J3 | 02x10 Female IDC connector ([DigiKey link](https://www.digikey.be/product-detail/en/sullins-connector-solutions/SFH11-PBPC-D10-RA-BK/S9205-ND/1990098))|
| J4 | 01x03 Female pinsocket |
| J5 | 02x05 Male IDC header |
| J6 | 01x03 Male pinheader (+ jumper) |
| J7 | 01x03 Male pinheader (+ jumper) |
| R1 | 1 kΩ 0805 Resistor |
| R2 | 100 Ω 0805 Resistor |
| C1 | 100 nF 0805 Capacitor |
| SW1 | 2 pin SPST tact switch |
