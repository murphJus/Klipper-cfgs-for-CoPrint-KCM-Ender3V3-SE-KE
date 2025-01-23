# Klipper-cfgs-for-CoPrint-KCM-Ender3V3-SE-KE

## Z-Offset and Bed Mesh
Bedmesh is the same normal process but z-offset must be manually inputted in chroma_head.cfg.
```
[probe]
pin: cp_Head:PA3

x_offset: 33
y_offset: -1.5

#Input your z-offset here
z_offset: 3.2
```

## PID Tune 
PID tuning for the CoPrint Chromahead is inputted manually 

Start by inputting this into the console 
```
PID_CALIBRATE HEATER=extruder TARGET=220 
```

After it finishes click the save and restart firmware button and record your values.
Input your values into the chroma_head.cfg extruder
```
[extruder]
max_extrude_only_distance: 300.0
max_extrude_cross_section:10
full_steps_per_rotation: 200
step_pin: cp_Head:PA9
dir_pin: !cp_Head:PA8
enable_pin: !cp_Head:PA10
#stepx
microsteps: 16
rotation_distance:  4.55287810496
nozzle_diameter: 0.400
filament_diameter: 1.750
heater_pin: cp_Head:PA2
sensor_type: NTC 100K MGB18-104F39050L32
sensor_pin: cp_Head:PA1
control: pid

#Enter values here
pid_Kp:15.407
pid_Ki:0.744
pid_Kd:79.727
```
