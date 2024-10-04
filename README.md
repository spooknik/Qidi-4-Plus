# Qidi 4 Plus Resources
Tweaks, mods, and info for the Qidi 4 Plus 3D printers

#### Better Host Fan Control
The fan that cools the eletronics chamber only runs when the stepper motors are active, however when the printer is idle the fan does not run. The CPU of the host can get a little bit warmer than what is preferred. You can add the following to your printer.cfg and comment out the original.

Replace (Comment out) This: 
```
[controller_fan board_fan]
pin:U_1:PC4
max_power:1.0
shutdown_speed:1.0
cycle_time:0.01
fan_speed: 1.0
stepper:stepper_x,stepper_y
```

With this:

```
[temperature_fan board_fan]
pin:U_1:PC4
max_power: 1.0
shutdown_speed: 1.0
cycle_time: 0.01
off_below: 0
sensor_type: temperature_host
control: pid
pid_deriv_time: 2.0
pid_Kp: 5
pid_Ki: 2
pid_Kd: 5
target_temp: 40
min_speed: 0.3
max_speed: 1.0
min_temp: 0
max_temp: 70
```

Credit: [stew675](https://discord.com/channels/1184400034641477722/1286669613681213440/1291763142967296001)

You can also consider upgrading the Fan to a 92 mm or 80mm fan.

#### SSH Access to the Klipper Host

You can SSH into the host with the following:  `ssh mks@[IP of Printer]`
Password is: `makerbase`

 

