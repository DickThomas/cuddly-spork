### The Problem
I was trying to install the Sims 4 on Linux using wine, but it kept failing due to vcredist_x64.exe vcredist_x86.exe (vc2010 vc2013 vc2017) failing to install or be skipped after installing them with winetricks.


### The Solution
The solution was simple, A program that "returns 0" to signal to the OS/ WINE / Origin installer that the program has exited successfully.

#### Step one.
write a program that exits with 0 to trick Origin/Wine that it was run successfully.

(see repo)

#### Step two.
Building the program was just as simple. After installing the mingw32 software (you'll have to google for your distro, I pretty much-installed everything mingw related"
build the exe with a quick 

    x86_64-w64-mingw32-g++  -static -static-libgcc -static-libstdc++ -o vcredist_x86.exe vcpp.cpp 
    
#### Step Three.

replace the vcredist_x86.exe and vcredist_x64.exe where ever your find them inside your WINEPREFIX renaming the old ones.

#### Step Four.
Re-run the installer for the sims4 on Origin.

#### Step Five.

Sit back and Enjoy 😂😂😂😂
