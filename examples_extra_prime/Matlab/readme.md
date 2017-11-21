### Matlab example - [Emotiv SDK 3.5.1](https://github.com/Emotiv/community-sdk)

1. Install Visual Studio Community 2013 or 2015 version with C++ build tool (MSVC).
2. If your Matlab is 64bit version, remove "default arguments" on each C/C++ header.
For example:
Original code in header [IEegData.h](https://github.com/Emotiv/community-sdk/blob/master/include/IEegData.h#L217):
``` C
EDK_API int
    IEE_DataSetMarkerWithEpoch (unsigned int userId,
                                unsigned int markerColum,
                                float markerHardwareColum = 0,
                                double epoch = 0);
```

Edit it to be like this:
``` C
EDK_API int
    IEE_DataSetMarkerWithEpoch (unsigned int userId,
                                unsigned int markerColum,
                                float markerHardwareColum,
                                double epoch);
```
3. Setup default C++ language compilation with `mex -setup c++` in Matlab console.
4. Edit each example to make them load correct edk.dll and C++ headers location. They work if you cloned all the Emotiv Community repository as it is.
5. Examples are tested with Matlab R2017a 64bit + Visual Studio 2015 Community
