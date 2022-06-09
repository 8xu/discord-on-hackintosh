# Is [Discord](https://discord.com) crashing on your AMD Hackintosh?

Well, it's probably because [MKL](https://en.wikipedia.org/wiki/Math_Kernel_Library), in MacOS however, when a program tries to use some of the "Intel functions" of the MKL, if the program doesn't properly catch the exception then it just outright crashes. Now you know why so many programs have issues on AMD Hackintoshes: the MKL is used all over the place! This is the basis for issues using a plethora of apps out there including Adobe and Matlab on a Hackintosh.

## How do you fix the crashes?
  Just copy and paste these in a terminal
  
  > ```cd /Applications/Discord.app/Contents/MacOS && echo "MKL_DEBUG_CPU_TYPE=5 ./Discord" > discord_```

  After that you need to open `/Applications/Discord.app/Contents/Info.plist` with a text editor, find *CFBundleExecutable* and modify it's value to `discord_`
 
  After all of this, hopefully Discord stops crashing! 🥲
You can also try [this](https://github.com/Pavo-IM/amd_hackintosh_discord_fix)
