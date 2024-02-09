# Higher FPS imx307 sensor driver on Goke/Hisilicon SoCs.

### 1920x1080 39 fps

### 1280x720 55fps


# To compile
Compile OpenIPC for Hisilicon in ```/home/home/src/OpenIPCv210/openipc-firmware```. 
Change code and copy over stock drivers.
 

```
cp imx307_2l_sensor_ctl.c /home/home/src/OpenIPCv210/openipc-firmware/output/build/hisilicon-opensdk-master/libraries/sensor/gk7205v200/sony_imx307_2L/
cp imx307_2l_cmos.c /home/home/src/OpenIPCv210/openipc-firmware/output/build/hisilicon-opensdk-master/libraries/sensor/gk7205v200/sony_imx307_2L/
```
This will rebuild it: 
```make -C /home/home/src/OpenIPCv210/openipc-firmware/output/ hisilicon-opensdk-rebuild```

copy driver to device: 
```scp /home/home/src/OpenIPCv210/openipc-firmware/output/build/hisilicon-opensdk-master/libraries/sensor/gk7205v200/sony_imx307_2L/libsns_imx307_2l.so root@192.168.1.88:/usr/lib/sensors/libsns_imx307_2l.so```


# To run
copy libsns_imx307_2l.so to /usr/lib/sensors/
in /etc/majestic.yaml set:
```
video0:
  #size: 1920x1080
  size: 1280x720
  fps: 30
...
isp:
  sensorConfig: /etc/sensors/imx307_fps.ini
```
copy imx307_fps.ini in /etc/sensors/ and follow instructions inside to change sensor image.
Do not change Isp_FrameRate=30 in imx307_fps.ini neither fps: 30 in majestic.

