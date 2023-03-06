# Simple power Management for a laptop

## What does it do?

- Changes the default cpu governor to `conservative`, helps save battery (at least for me).
- When the laptop is plugged in the cpu governor is chaged back to the default, `schedutil`.
- When the laptop is unplugged `conservative` is set as the cpu governor and the power profile is set to `power-saver`

## Installation

```

$ cd power_management
$ chmod +x install
$ sudo ./install

```