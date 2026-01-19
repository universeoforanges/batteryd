# batteryd
batteryd is a simple, configurable power management daemon written in Lua 5.1 for Linux.

## Why batteryd?
Originally, batteryd was made for my personal use. Personally, I found it pretty annoying that I couldn't find any configurable power management daemons, so I just made my own, then eventually opened it to the public.

## Configuring batteryd
batteryd will check the following directories for a file named "config".
- `$HOME/.config/batteryd`
- `./`

### Default config
```
# if true, the daemon print all notifications to stdout instead of showing a notification. (default: false)
USE_STDOUT = false

# determines if the user is warned when the battery capacity falls below the percentage specified by LOW_BATTERY_THRESHOLD. (default: true)
WARN_ON_LOW_BATTERY = true

# determines if the user is warned when the battery capacity falls below the percentage specified by CRIT_BATTERY_THRESHOLD. (default: true)
WARN_ON_CRIT_BATTERY = true

# determines if the user is warned when the power state changes (e.g. battery is unplugged)
WARN_ON_STATE_CHANGE = true

# threshold to notify the user & run the specified command to run on low charge when the battery is low (default: 20%)
LOW_BATTERY_THRESHOLD = 20

# threshold to notify the user & run the specified command to run on critical charge when the battery is critically low (default: 10%)
CRIT_BATTERY_THRESHOLD = 10

# threshold that specifies when to limit system performance by disabling cores, etc. set to 0 if u dont want reserve power obv (default: 20%)
RESERVE_POWER_THRESHOLD = 20

# extra commands to run when the battery capacity falls below the percentage set by RESERVE_POWER_THRESHOLD. (default: none)
ON_RESERVE_POWER = ""

# threshold that specifies when to run the specified action (default is 5%)
ACTION_THRESHOLD = 5

# the command to run when the battery capacity falls below the percentage specified by ACTION_THRESHOLD. (default: "systemctl poweroff -i")
ACTION_CMD = "systemctl poweroff -i"

# the command to run when the system is now running on DC power. (default: none)
ON_DC_POWER = ""

# the command to run when the system is now running on AC power. (default: none)
ON_AC_POWER = ""

# the command to run when the system falls below the percent set by LOW_BATTERY_THRESHOLD. (default: none)
ON_LOW_BATTERY = ""

# the command to run when the system falls below the percent set by CRIT_BATTERY_THRESHOLD. (default: none)
ON_CRIT_BATTERY = ""

# the command to run when the critical battery warning is cleared (default: none)
ON_CRIT_WARNING_CLEARED = ""

# the command to run when the low battery warning is cleared (default: none)
ON_LOW_WARNING_CLEARED = ""

# the command to run when the system is no longer running on reserve power (default: none)
ON_RESERVE_CLEARED = ""
```
