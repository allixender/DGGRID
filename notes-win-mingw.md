
```shell

# mingw64
set PATH=C:\dev\mingw-w64\x86_64-8.1.0-posix-seh-rt_v6-rev0\mingw64\bin;%PATH%

# RTools
C:\dev\Rtools\mingw_64\bin\gcc

```
set PATH=C:\dev\Rtools\mingw_64\bin;%PATH%


#include <math.h>

// if it doesn't work then we define these manually
#ifndef _USE_MATH_DEFINES

    #define _MATH_DEFINES_DEFINED

    #define M_PI       3.14159265358979323846000000000000000000L
    #define M_PI_2     1.57079632679489661923000000000000000000L
    #define M_SQRT2    1.41421356237309504880000000000000000000L

#endif
