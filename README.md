# Klipper KP3S
![alt text](https://github.com/nehilo/klipper_KP3S/blob/main/klipper%20kp3s.png?raw=true)


# Firmware build

```bash
cd ~/klipper
```
```bash
make menuconfig
```

![alt text](https://github.com/nehilo/klipper_KP3S/blob/main/make.png?raw=true)

```bash
make 
```

```bash
./scripts/update_mks_robin.py out/klipper.bin out/Robin_nano.bin
```



## PID calibration
Replace `230` and `70` with your average temperatures
After all commands save auto edited settings with `SAVE_CONFIG`

PID Extruder
```
PID_CALIBRATE HEATER=extruder TARGET=230
```
PID Hotbed
```
PID_CALIBRATE HEATER=heater_bed TARGET=70
```

You question and main information you can checked https://cutt.ly/Cgow7vL
