# marlin-2.1.x-for-flsun-i3-
Created to make linear advance work with standalone TMC2208 without UART. Based on barebones Marlin.

If you are using basic drivers than change:

```C++ core
#define X_DRIVER_TYPE TMC2208_STANDALONE
#define Y_DRIVER_TYPE TMC2208_STANDALONE
#define Z_DRIVER_TYPE TMC2208_STANDALONE
```
and
```C++ core
#define E0_DRIVER_TYPE TMC2208_STANDALONE
```
to
```C++ core
#define X_DRIVER_TYPE A4988
#define Y_DRIVER_TYPE A4988
#define Z_DRIVER_TYPE A4988
```
and
```C++ core
#define E0_DRIVER_TYPE A4988
```
Stuff above is mostly useless, and this is not:
```C++ core
#define INVERT_X_DIR true
#define INVERT_Y_DIR false
#define INVERT_Z_DIR false
```
and
```C++ core
#define INVERT_E0_DIR true
```
Must be changed to:
```C++ core
#define INVERT_X_DIR false
#define INVERT_Y_DIR true
#define INVERT_Z_DIR true
```
and
```C++ core
#define INVERT_E0_DIR false
```
and Bob's your uncle.
If you need to adapt this firmware to standart i3, change:
```C++ core
#define X_BED_SIZE 300
#define Y_BED_SIZE 300
```
and
```C++ core
#define Z_MAX_POS 400
```
to
```C++ core
#define X_BED_SIZE 200
#define Y_BED_SIZE 200
```
and
```C++ core
#define Z_MAX_POS 220
```

If you want to change my totally awesome printer name, than go and change:
```C++ core
#define CUSTOM_MACHINE_NAME "Pancaker i3+"
```
to any boring thing your heart desires.

PLEASE KEEP IN MIND THAT MY PRINTER'S PROBE OFFSET WILL DIFFER FROM YOURS. 
```C++ core
#define NOZZLE_TO_PROBE_OFFSET { -28, -1, 0 }
```
You'll probably will need to measure your probe offset to be sure that bed homing works correctly.

If your heart desires, you can buy me a cup of tea: paypal.me/pancakery

Wish you all great first layers!
