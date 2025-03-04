---
title: Plugin: Synaptics CxAudio — Conexant Audio
---

## Introduction

This plugin is used to update a small subset of Conexant (now owned by Synaptics)
audio devices.

## Firmware Format

The daemon will decompress the cabinet archive and extract a firmware blob in
a modified SREC file format.

This plugin supports the following protocol ID:

* `com.synaptics.synaptics-cxaudio`

## GUID Generation

These devices use the standard USB DeviceInstanceId values, e.g.

* `USB\VID_17EF&PID_3083&REV_0001`
* `USB\VID_17EF&PID_3083`
* `USB\VID_17EF`

These devices also use custom GUID values, e.g.

* `SYNAPTICS_CXAUDIO\CX2198X`
* `SYNAPTICS_CXAUDIO\CX21985`

## Update Behavior

The firmware is deployed when the device is in normal runtime mode, and the
device will reset when the new firmware has been written.

## Vendor ID Security

The vendor ID is set from the USB vendor, in this instance set to `USB:0x17EF`

## Quirk Use

This plugin uses the following plugin-specific quirks:

### CxaudioChipIdBase

Base integer for ChipID.

Since: 1.3.2

### CxaudioSoftwareReset

If the chip supports self-reset.

Since: 1.3.2

### CxaudioPatch1ValidAddr

Address of patch location #1.

Since: 1.3.2

### CxaudioPatch2ValidAddr

Address of patch location #2.

Since: 1.3.2

## External Interface Access

This plugin requires read/write access to `/dev/bus/usb`.

## Version Considerations

This plugin has been available since fwupd version `1.3.2`.
