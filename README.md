# marlin-2.1.x-for-flsun-i3-
Created to make linear advance work with standalone TMC2208 without UART. Based on barebones Marlin.

If you are using basic drivers than change:

```C++ core
#define X_DRIVER_TYPE  TMC2208_STANDALONE
#define Y_DRIVER_TYPE  TMC2208_STANDALONE
#define Z_DRIVER_TYPE  TMC2208_STANDALONE
```
and
```C++ core
#define E0_DRIVER_TYPE TMC2208_STANDALONE
```
to
```C++ core
#define X_DRIVER_TYPE  A4988
#define Y_DRIVER_TYPE  A4988
#define Z_DRIVER_TYPE  A4988
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

If you want to change my totally awesome printer name, than go to:
```C++ core
#define CUSTOM_MACHINE_NAME "Pancaker i3+"
```
and write any boring thing your heart desires.