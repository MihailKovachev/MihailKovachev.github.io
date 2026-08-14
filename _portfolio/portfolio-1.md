---
title: "ZloUSB"
excerpt: "HID keyboard emulator<br/><img src='/images/ZloUSB/ZloUSB_top_and_bottom.png'>"
collection: portfolio
---

[ZloUSB](https://github.com/MihailKovachev/ZloUSB) is an HID keyboard emulator for keystroke injection and script automation inspired by the [USB Rubber Ducky](https://shop.hak5.org/products/usb-rubber-ducky) and the [MalDuino](https://maltronics.com/collections/malduinos/products/malduino-3). I created this as a project to teach myself PCB schematic design and layout with Altium.

## Key Features & Specifications

|Category|Details|
|:--: |:--|
|**Microcontroller**|Raspberry Pi RP2040|
|**Flash Memory**|16 MB (128 Mbit) Winbond W25Q128JVSIQ SPI Flash|
|**Connectivity**|Dual USB-A and USB-C (USB 2.0 Full-Speed @ 12 Mbit/s)|
|**User Controls**|3 tactile buttons: \\(\overline{\text{USBB}}\\) (firmware upload), \\(\text{RST}\\) (manual reset), and \\(\text{INJ/}\overline{\text{UPL}}\\) (Injection / Script Upload)|
|**Diagnostics**|2 status/debugging LEDs |
|**PCB Form Factor**|4-layer ultra-compact USB stick layout, 40.0 mm x 20.0 mm|

## Hardware Design & Engineering Constraints

The primary constraints for this build were miniaturization and low-cost fabrication and assembly:

- To leverage the cost-effective single-sided automated assembly of JLCPCB, the component selection was tightly filtered around JLCPCB's Basic / Preferred Components library to avoid extra fees.
- Since budget constraints restricted SMT assembly to a single side, components required on the bottom layer were upscaled to larger footprints to enable manual post-assembly soldering.
- The USB-A and USB-C connectors had to share the power line and the USB 2.0 D+/D- differential pair, whilst achieving identical trace lengths and \\(90\,\Omega\\) differential impedance. 

## Schematics

### USB Interface & Power

![USB Schematic](/images/ZloUSB/ZloUSB_USB_Sch.png)

### RP2040 Core

![Core Schematic](/images/ZloUSB/ZloUSB_Core_Sch.png)

## 3D Renders

|Top View| Bottom View |
|:---:|:---:|
|![Top 3D View](/images/ZloUSB/ZloUSB_top_3d_view.png)|![Bottom 3D View](/images/ZloUSB/ZloUSB_bottom_3d_view.png)|

## PCB Layout

|Layer|Description|Image|
|:--:|:---|:--:|
|L1 (Top)|Signal - USB, RP2040, LEDs, buttons|![Top Layer](/images/ZloUSB/ZloUSB_top_layer.png)|
|L2 (GND)|Ground|![Ground Layer](/images/ZloUSB/ZloUSB_Ground_Layer.png)|
|L3 (PWR)|Power - 3V3, 5V VBUS|![Power Layer](/images/ZloUSB/ZloUSB_Power_Layer.png)|
|L4 (Bottom)|Signal - flash memory, voltage regulator|![Bottom Layer Mirrored](/images/ZloUSB/ZloUSB_bottom_layer_mirrored.png)<br/><br/>![Bottom Layer](/images/ZloUSB/ZloUSB_bottom_layer.png)|

![Top and Bottom Layer](/images/ZloUSB/ZloUSB_top_and_bottom.png)
