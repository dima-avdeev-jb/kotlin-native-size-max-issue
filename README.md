Issue with property name: `val SIZE_MAX = 1`  

To reproduce:
 - install KMM plugin into AndroidStudio.
 - Open and press run on iOS simulator.

Build logs:
```
/[project path]/shared/build/xcode-frameworks/Debug/iphonesimulator16.4/shared.framework/Headers/shared.h:148:37: error: expected identifier or '('
@property (class, readonly) int32_t SIZE_MAX __attribute__((swift_name("SIZE_MAX")));
```


Take a look at file [main.ios.kt](shared%2Fsrc%2FiosMain%2Fkotlin%2Forg%2Fexample%2Fmain.ios.kt)
Here we have `val SIZE_MAX = 1`. We can comment it and build will works fine.
