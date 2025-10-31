## Glass Instructions
Instructions on how to set up glass effects in the Aero7-11 theme pack.

### Requirements

- Aero7-11 Theme installed and applied. [Instructions here](../README.md#installation)

#### DWMBlurGlass Method:
This method does *not* work with the uDWM patch on 23H2, use the Windhawk mod instead.

- Install DWMBlurGlass.
- Make sure to go to the symbols tab and download symbols.
- Apply it as normal.

#### OpenGlass Method:
This method is broken on Windows 11 24H2 and later due to changes in DWM. If you are on 24H2 or later, please use the DWMBlurGlass method above.

- Optionally Run the AeroDWM.reg file to import its contents into the registry.
- If you are on Windows version 26100.4484 or later, follow the instructions in dwmcore-patch.txt.
- Install OpenGlass and start it up.

#### DWMCore Patch Method:
To use this method you need to downgrade your `dwmcore.dll` file to a version prior to 26100.4484. This is *not* recommended, and you should use the DWMBlurGlass method above instead.

**Applying**:

- Check if your Windows version is 26100.4484 or later.
	1. If you are on a version below that, this patch is not required and should not be used.
- Open command prompt as TrustedInstaller.
	1. NSudo is included for this purpose.
- Switch to `%SYSTEMROOT%\System32`.
- ***RENAME*** `dwmcore.dll` to `dwmcore.old.dll`.
	1. ***DO NOT DELETE IT!*** You will want a backup if something goes wrong!
- Copy `dwmcore.dll` from the folder to System32.
- Run `taskkill /f /im dwm.exe` to restart DWM.

**If something goes wrong**: Something went wrong, there is a black screen, DWM is restarting on loop, etc!

- You will need to go into recovery mode. To do this:
	1. Press and hold the physical power button to shut it down.
	2. Press the button to turn it on.
	3. As soon as the boot logo appears, hold the button to power off again.
	4. Repeat 2-3 times. It will then try to go to automatic repair.
- Choose `advanced options -> troubleshoot -> advanced options -> command prompt`
- Run notepad
- Select File -> Open -> This PC
- Change `Text Documents (*.txt)` to `All Files (*.*)`
- Browse to the `%SYSTEMROOT%\System32` folder
- Rename `dwmcore.dll` to `dwmcore.bad.dll`.
- Rename `dwmcore.old.dll` to `dwmcore.dll`.
- Run `wpeutil reboot`

---

Note: For OpenGlass users an experimental reg file is available. It is not unstable, it is just that the Aero look still seems a little off. Anyone who can help make it better, anything will help!