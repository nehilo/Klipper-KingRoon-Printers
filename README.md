# Klipper_KP3S
![alt text](https://github.com/nehilo/klipper_KP3S/blob/main/klipper%20kp3s.png?raw=true)

## General

This guide assumes that you have raspberry pi with fluidpi image installed and configured. Also you have ssh access to your device.

Documentation: https://docs.fluidd.xyz/installation/fluiddpi

## Build klipper firmware

On your raspberry pi:

```bash
cd ~/klipper/
make menuconfig
```

This is how menuconfig should **exactly** like for KP3S (please match all params including serial port):

![alt text](https://github.com/nehilo/klipper_KP3S/blob/main/photo_2021-01-26_18-44-12.jpg?raw=true)

Next build your image:

```bash
make

./scripts/update_mks_robin.py out/klipper.bin out/Robin_nano.bin
```

After that copy `Robin_nano.bin` file from pi to root of your printer sd card (using `scp` or whatever way your prefer). Boot printer, and it should start updating. It won't switch off after it reach 100%, so reboot it by yourself in a couple of minutes and you're all set.

## Calibration

This should be done once for a while. At least do it before you begin printing with klipper. Please use fluidd web interface console for that (not pi ssh or whatever).

Every command takes some time to finish. After all commands finished you may want to save calibration values with `SAVE_CONFIG`

PID Calibration console EXTRUDER
```
PID_CALIBRATE HEATER=extruder TARGET=200 # replace 200 with your average printing temperature
```
PID Calibration console BED
```
PID_CALIBRATE HEATER=heater_bed TARGET=50 # replace 50 with your average printing temperature
```


For questions and additional information: https://cutt.ly/Cgow7vL
