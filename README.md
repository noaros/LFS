# LFS

A recurring itch I've had for a long time is to take the Linux From Scratch project for a spin, to gain insight and remind myself of how all the pieces fit together, especially at those early levels. I'll be applying to to my dual boot Arch/Win install with rEFInd bootloader so will probably have to deviate a bit from tutorial.

First step was was to free up about 30GB of space on my shared NTFS partition. I will be building the system from Arch, which I also used to format as ext4.

I appreciate that the LFS project exists as a guide, but there is room for improvement with clarity. The author seems too cautious for hobbyist work, and strangely makes a big deal out of timing benchmarks. "Host" means different things at different times, and the whole cross compilation explanation was so confusing I found myself reviewing the typical terms elsewhere. The technical explanation for the various meta compiling stages is particularly confusing. Cross compilation isn't even needed for my purposes, and probably many others, so while I realize the author is doing it as a teaching point, I find myself wishing he had made a simpler version without it, at least for a first pass. Also the author refactors out some of the repetition in install steps for each package, but that leaves the reader without a clear step by step guide for each.

I think I found a mistake in the material, as the instructions set up a "sources" directory as "root", yet later direct you to unpack files as "lfs" user, which doesn't have access, and so won't work. There is a step in chapter 4 to make 'lfs' the owner of all directories under its mount point, but the sources directory is omitted.

I had trouble using the shell script in chapter 5 to make the 'limits' file, and thought I had found another mistake. I was able to manually create the 'limits.h' file and put in the right spot based on clues in the nearby paragraph. Later I learned something went wrong with my gcc build, and that was why the script failed.
