# Simple power Management for laptops

## What does it do?

- Changes the default cpu governor to `conservative`, helps save battery (you should test it).
- When the laptop is plugged in the cpu governor is chaged to `performance`
and the scaling driver is changed to `amd-pstate epp`.
- When the laptop is unplugged `conservative` is set as the cpu governor, the power profile is set to `power-saver`
and the performance scaling driver is changed to `amd-pstate`.

## Requisites

- amd cpu (at least zen2)
- kernel >= 6.3 or a patched kernel with amd-pstate epp

## Testing

In order to test if conservative cpu governor actually helps you save battery
you can use tools such as [battop](https://github.com/svartalf/rust-battop "Battop on Github") to see the real time discharge rate of your laptop.

To see the current governor:

```bash
cat /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor
```

## Install

```bash
git clone https://github.com/cch000/power_management.git
cd power_management
chmod +x install
sudo ./install
```

**Reboot**

## Uninstall

```bash
chmod +x uninstall
sudo ./uninstall
```

**Don't forget to reboot.**
