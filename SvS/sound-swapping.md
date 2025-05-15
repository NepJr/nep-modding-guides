# Sisters vs Sisters sound swapping guide

## Tools needed
- Something to extract CPK files. [Noesis](https://www.richwhitehouse.com/filemirror/noesisv4474.zip) worked fine for me
- [VGAudio Application](https://github.com/Thealexbarney/VGAudio) to convert your WAV file to HCA
- [CPK Patcher](https://github.com/mosamadeeb/CpkPatcher) to patch the SOUND.CPK file

## Steps to replace existing sounds
Go to where your SvS installation is. Easiest way is to right click the game on steam, go to properties, local files, then browse. Once you're there, go into ``neptunia-sisters-vs-sisters_Data\StreamingAssets\CPK``. Once there, right click your SOUND.CPK file, and make a copy and store it somewhere else. In the event something goes wrong you can use that backup to restore it easily. Alternatively, you can re-verify files on steam.

Next, Use Noesis to extract the CPK files, and find a place to store them. Now, enter where the files got extracted, then go into ``Assets\Project\AppData\Game\Sound\Bgm``. This is where the BGM files exist. 

Now, find a song you want to replace [here](https://github.com/NepJr/nep-modding-guides/blob/main/SvS/data/music-list.md). This tutorial will only cover the main menu theme however, as it's the easiest to quickly test

Now, get a song to replace the main menu theme. You need to save it as a WAV file.

Next, open command prompt / terminal and go to the folder where VGAudio is extracted. It's a command line tool, however, the command to convert the wav file to HCA is ```VGAudioCli.exe -i input_sound.wav -o 001-new.hca --bitrate 256000```.

Now that our Sound file is created, it's time to patch the SOUND.CPK file

Make a new folder, I like to name mine SOUND.CPK_patched, then inside, you need to create the subdirectories that match the CPK file, so inside the patch folder, you'd have to create ``Assets\Project\AppData\Game\Sound\Bgm``. Inside the Bgm folder in the patch, place your HCA file, specifically named ``001.hca``.

Now, it's time to patch the CPK file. I placed the CPK Patcher EXE in the folder where the CPK folders are to make it easier to patch them. To patch the CPK file, open a terminal / command prompt window in the CPK folder, then run ```CpkPatcher.exe SOUND.CPK C:\path\to\SOUND.CPK_patched SOUND_NEW.CPK```. It will create a SOUND_NEW.CPK file in the folder with the other CPK files. Rename ``SOUND.CPK`` to something else then rename your ``SOUND_NEW.CPK`` accordingly. If you launch the game, you should hear your custom track on the main menu.

There are probably some other nifty things you can do with these sound files i.e. looping and what have you, but this just covers doing basic sound swaps
