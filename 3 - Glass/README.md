## Glass Instructions
Instructions on how to set up glass effects in the Aero7-11 theme pack.

### Requirements
- Aero7-11 Theme installed and applied. [Instructions here](../README.md#installation)


#### DWMBlurGlass Method:
This method does *not* work with the uDWM patch on 23H2, use the Windhawk mod instead.

1. Install DWMBlurGlass.
2. Make sure to go to the symbols tab and download symbols.
3. Apply it as normal.

#### OpenGlass Method:
This method is broken on Windows 11 24H2 and later due to changes in DWM. If you are on 24H2 or later, please use the DWMBlurGlass method above.

1. Optionally Run the AeroDWM.reg file to import its contents into the registry.
2. If you are on Windows version 26100.4484 or later, follow the instructions in dwmcore-patch.txt.
3. Install OpenGlass and start it up.

#### DWMCore Patch Method:
To use this method you need to downgrade your `dwmcore.dll` file to a version prior to 26100.4484. This is *not* recommended, and you should use the DWMBlurGlass method above instead.

**Applying**:

1. Check if your Windows version is 26100.4484 or later.
	1. If you are on a version below that, this patch is not required and should not be used.
2. Open command prompt as TrustedInstaller.
	1. NSudo is included for this purpose.
3. Switch to `%SYSTEMROOT%\System32`.
4. ***RENAME*** `dwmcore.dll` to `dwmcore.old.dll`.
	1. ***DO NOT DELETE IT!*** You will want a backup if something goes wrong!
5. Copy `dwmcore.dll` from the folder to System32.
6. Run `taskkill /f /im dwm.exe` to restart DWM.

---
**If something goes wrong**: Something went wrong, there is a black screen, DWM is restarting on loop, etc!

1. You will need to go into recovery mode. To do this:
	1. Press and hold the physical power button to shut it down.
	2. Press the button to turn it on.
	3. As soon as the boot logo appears, hold the button to power off again.
	4. Repeat 2-3 times.
	4. It will then try to go to automatic repair.
2. Choose advanced options -> troubleshoot -> advanced options -> command prompt
3. Run notepad
4. Select File -> Open -> This PC
5. Change `Text Documents (*.txt)` to `All Files (*.*)`
6. Browse to the System32 folder (inside the Windows folder)
7. Rename `dwmcore.dll` to `dwmcore.bad.dll`.
8. Rename `dwmcore.old.dll` to `dwmcore.dll`.
9. Run wpeutil reboot


---

Note: For OpenGlass users an experimental reg file is available. It is not unstable, it is just that the Aero look still seems a little off. Anyone who can help make it better, anything will help!