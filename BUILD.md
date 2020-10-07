# How to build iCHM

1. git clone --recurse-submodules https://github.com/djlin/ichm.git

* If you prefer to manually download the supporting frameworks, do the following.
1.1. iCHM requires some frameworks, all available on GitHub, get them here: [PSMTabBarControl](https://github.com/dorianj/PSMTabBarControl), [chmlib](https://github.com/lvivski/chm_lib), and [Sparkle](https://github.com/sparkle-project/Sparkle]. Use the green "Clone or download" control to download the full source archive of each framework.
1.2. Create a Frameworks folder in the iCHM source folder.
1.3. Extract all the frameworks zips to some temporary location. You can delete the sources once the frameworks are built.
1.4. Open a terminal and cd to the [PSMTabBarControl/chmlib/Sparkle] folder.
1.5 ./build.sh (for Sparkle, do "make release")"
1.6. Copy the contents of build/Release to the iCHM/Frameworks folder.

2. Run all conversions done automatically by XCode
3. Go to the linker and remove the -lcrypto link module.
4. Change the target platform to 10.12 and ensure 64bit is seclected.
* Several places. "Build Settings" -> "Architectures" -> change to "Standard architectures
* Several places. "Build Settings" -> "Apple Clang - Language - Objective-C" -> set "Weak References ni Manual Retaini Release" to "No"
5. Change the version number to reflect the 64bit nature of the build. This is necessary but can remind you if you forget where it came from.
6. Use "Automatically manage signing" and provide your Team info. 
* I leave provisioning Profile "None" and make "Signinig Certificate" -> "Sign to Run Locally"
7. Build a release and copy it to your Applications folder.

## References
1. [CHM Viewer for MacOS](http://heardofaudio.com/musings/blog/files/7ba3a4c9c2e9bd496ed23817bf3249ea-28.php)
