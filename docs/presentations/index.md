## PUWELL's Bizarre Adventure

[Slides](https://docs.google.com/presentation/d/1ma5rQ1qzzaBv3KeVGDb0__8gsTNZbjwfX39XY3dLjX4/edit?usp=sharing)

Talk was given at CovHackSoc in early 2020, based on work I did over the summer in 2019.

Covers some basic hardware hacking, where I bought a cheap IP camera off Amazon and how I got code executation on it.

Talk covers:

* Discovering the debug pads.
* Hooking up a UART adapter to talk to the bootloader.
* Tricked the u-boot based bootloader into dumping itself.
* Some some firmware analysis to discover how to trick it to load a debug script and get a shell.
* Mounting a new rootfs and using `pivot_root` to get my own environment on it.

Interesting as I couldn't use the usual trick of swapping the value of `init` in the kernel arguments, hence the use of the debug script trick.
