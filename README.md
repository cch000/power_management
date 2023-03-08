# Simple power Management for laptops

## What does it do?

- Changes the default cpu governor to `conservative`, helps save battery (at least for me).
- When the laptop is plugged in the cpu governor is chaged back to `schedutil`.
- When the laptop is unplugged `conservative` is set as the cpu governor and the power profile is set to `power-saver`

## Dependencies

Requires cpupower, on fedora it can be installed running:

```
dnf install kernel-tools
```


## Installation

Before installing check that your computer supports the previously mentioned cpu governors with:

```
cpupower frequency-info
```
If you can see them go ahead an install by running:

```
git clone https://github.com/cch000/power_management.git
cd power_management
chmod +x install
sudo ./install
```
