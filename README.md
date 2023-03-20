# Simple power Management for laptops

## What does it do?

- Changes the default cpu governor to `conservative`, helps save battery (you should test it).
- When the laptop is plugged in the cpu governor is chaged back to `schedutil`.
- When the laptop is unplugged `conservative` is set as the cpu governor and the power profile is set to `power-saver`

## Requisites

Requires cpupower, on fedora it can be installed running:

```
dnf install kernel-tools
```

Before installing check that your laptop supports the previously mentioned cpu governors with:

```
cpupower frequency-info
```

## Testing

In order to test if conservative cpu governor actually helps you save battery
you can use tools such as [battop](https://github.com/svartalf/rust-battop "Battop on Github") to see the real time discharge rate of your laptop.

To see the current one:

```
cat /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor
```

To change it to conservative: 

```
sudo cpupower frequency-set -g conservative
```

Keep in mind that it will change to the default after rebooting or suspending.

## Install

```
git clone https://github.com/cch000/power_management.git
cd power_management
chmod +x install
sudo ./install
```

## Uninstall

```
chmod +x uninstall
sudo ./uninstall
```