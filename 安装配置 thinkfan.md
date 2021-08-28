## 1. 安装 thinkfan

`yay -S thinkfan`

## 2. 配置 thinkfan

``` shell
╭─quintin@manjaro ~ 
╰─$ cat /etc/thinkfan.conf 
# 设备通过 find /sys/devices -type f -name "temp*_input" 命令获取
hwmon /sys/devices/platform/coretemp.0/hwmon/hwmon6/temp3_input
hwmon /sys/devices/platform/coretemp.0/hwmon/hwmon6/temp4_input
hwmon /sys/devices/platform/coretemp.0/hwmon/hwmon6/temp1_input
hwmon /sys/devices/platform/coretemp.0/hwmon/hwmon6/temp5_input
hwmon /sys/devices/platform/coretemp.0/hwmon/hwmon6/temp2_input

tp_fan /proc/acpi/ibm/fan
(0,     0,      55)
(1,     48,     60)
(2,     50,     61)
(3,     52,     63)
(4,     56,     65)
(5,     59,     66)
(7,     63,     32767)

╭─quintin@manjaro ~ 
╰─$ cat /etc/modprobe.d/thinkfan.conf                  
options thinkpad_acpi fan_control=1
```

## 3. 加载 thinkfan 模块

``` shell
sudo modprobe -rv thinkpad_acpi
sudo modprobe -v thinkpad_acpi
```

## 4. 启动 thinkfan

`sudo systemctl start thinkfan`

## 5. 设置开机自启动

`sudo systemctl enable thinfan`
