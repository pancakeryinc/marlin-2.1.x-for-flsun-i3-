# marlin-2.1.x-for-flsun-i3-
Created to make linear advance work with standalone TMC2208 without UART. Based on barebones Marlin.

If you are using basic drivers than change:

```с
#define X_DRIVER_TYPE  TMC2208_STANDALONE
#define Y_DRIVER_TYPE  TMC2208_STANDALONE
#define Z_DRIVER_TYPE  TMC2208_STANDALONE
and
#define E0_DRIVER_TYPE TMC2208_STANDALONE
```

to

```с
#define X_DRIVER_TYPE  A4988
#define Y_DRIVER_TYPE  A4988
#define Z_DRIVER_TYPE  A4988
and
#define E0_DRIVER_TYPE A4988
```