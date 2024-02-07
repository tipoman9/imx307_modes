# Higher FPS imx307 sensor driver on Goke/Hisilicon SoCs.

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

