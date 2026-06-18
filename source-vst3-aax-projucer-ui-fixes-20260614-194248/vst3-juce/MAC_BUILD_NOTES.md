# DB-5035 Qing Compressor Mac Build Notes

This project includes both CMake and Projucer setup.

## Projucer workflow

1. Install Xcode.
2. Install JUCE/Projucer. Use JUCE 8.x if possible.
3. Open `DB-5035 Qing Compressor.jucer` in Projucer.
4. If Projucer reports missing modules, set the module path to your local JUCE `modules` folder.
5. Save the project to generate `Builds/MacOSX`.
6. Open the generated Xcode project.
7. Build the `DB-5035 Qing Compressor - VST3` target in Release.

## AAX note

The project file also enables AAX. Building/loading AAX may require the AAX SDK and Avid/PACE signing workflow. Unsigned AAX builds may not load in regular Pro Tools.

## CMake workflow

If you prefer CMake:

```sh
cmake -S . -B build-mac -G Xcode -DCMAKE_OSX_ARCHITECTURES="arm64;x86_64"
cmake --build build-mac --config Release
```

The CMake project is the version used for the current Windows VST3/AAX builds.
