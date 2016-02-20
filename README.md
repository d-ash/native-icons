# Native Icons Extraction Library

This library provides a method to extract icons, which are assosiated with a given file extension. The library is multi-platform, it works on Windows and OSX. A Linux version is not implemented yet, due to inconsistency among various distributions, GUI libraries and window managers.

The following function accepts `extension` and `outputDir` as parameters. These are **UTF8** encoded strings.

```C
int rymnik_SaveIconsForFileExt( const char* const extension, const char* const outputDir );
```

* It calls native OS API methods to get images for the `extension`, and saves three sizes of them to the `outputDir`.
* Image dimensions are platform-specific.
* Saved files will have one of these postfixes [ `_sma`, `_mid`, `_big` ] in their names.
* On OSX images are stored in a PNG format, on Windows it's ICO.
* In case of an error the return value will be 0, otherwise 1.

**IMPORTANT**  
Call `rymnik_Init()` before calling `rymnik_SaveIconsForFileExt(...)`.  
See usage examples in `*_test.*` files.
