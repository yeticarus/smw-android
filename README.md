
# smw-android
A port of SMW to Android. <br>

Original Repository: https://github.com/snesrev/smw <br>
This is a cobbled together version from [Waterdish](https://github.com/Waterdish/zelda3-android). Full credit goes to them, I just ported the SMW code over.


<h1>Instructions:</h1>
Running the app once will create the directory **Android/data/net.freyta.smw/files**. <br>
You need to put the **smw_assets.dat** file in this directory.<br>
To generate this file from your rom from an Android device, follow the instructions below. <br> 
(Alternativelly, you can generate the file from the instructions of the original repository.)

<h2>How to Change Settings:</h2>
**Android/data/net.freyta.smw/files** contains **smw.ini**. Use a text editor to change options.<br>

<h4>Default Settings for gamepad: </h4>
L3 = Save State<br>
R3 = Load State <br>

<h4>Default Settings for touch screen:</h4>
Start + R = Save State<br>
Start + L = Load State<br>

*Note: Credit to [@yeticarus](https://github.com/yeticarus) for their touch screen code.* 


<h2>Instructions for creating smw_assets.dat on Android:</h2>
<h4>If PyDroid is already installed and configured with Pillow and pyyaml, you can skip this part. Else, do this:</h4>
1. Download PyDroid: https://play.google.com/store/apps/details?id=ru.iiec.pydroid3&hl=en_US. Choose to skip any options that ask for money, you can do all of the following steps without paying.<br>
2. Open the hamburger menu at the top left of the app and select Pip.<br>
3. Type in "Pillow" without the quotes and it will have you install the repository app from the app store.<br>
4. Once the repository app is installed, you can install "Pillow" and "pyyaml" <br>
<h4>Then,</h4>
5. Download the <b>source code</b> zip file for smw-android (not the apk release).<br>
6. Extract the zip file. <br>
7. Place your rom file in ./smw-android/app/jni/SMW_SRC/, and rename it to smw.sfc <br>
8. Open PyDroid, open the hamburger menu, and select Terminal.<br>
9. Navigate to where you placed the rom file. (If you are unfamiliar with terminal commands, "ls" lists the folders and files and "cd Foldername" changes the directory.  <br> 
10. Paste in this command <code>python3 assets/restool.py --extract-from-rom</code> <br>
11. It should pause for a while and when it finishes you should be able to see smw_assets.dat in the same folder as your rom. You can go ahead and copy that to the Android/data/net.freyta.smw/files location. <br>

<h4>Cleaning</h4>
If you wish, you can now delete your rom, the sourcecode.zip, the extracted source code, and even uninstall PyDroid (or just Pillow and pyyaml).</br>
Just keep the apk installed with the smw_assets.dat in the correct location.

<h2>Changelog</h2>
<h3>Version 1.1.0</h3>
Fixing known issue: pressing B while holding Y used to shortly release Y (You couldn't jump holding a shell).<br>
<h3>Version 1.0.2</h3>
Now the source code include the fix for secondary entrance issue at data extraction. (https://github.com/snesrev/smw/pull/43)
