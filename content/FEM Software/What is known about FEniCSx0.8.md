---
aliases:
  - FEniCSx
---
## Summary of FEniCSx 0.8

1. FEniCSx is a powerful tool that is most compatible with Linux operating systems.
2. It has extensive tutorials and a wide range of use cases, as shown in this [link](https://jsdokken.com/dolfinx-tutorial/).
3. The language used to operate FEniCSx 0.8 is Python.

## Steps for Installing and Using FEniCSx 0.8 on Windows

1. Open Windows PowerShell.
2. Install WSL:
	1. Run `wsl --install`.
3. Set WSL's version to 2:
	- WSL 2 has access to CUDA Nvidia drivers, allowing your subsystem to use your GPU (a graphics processing hardware component in most commercial computers).
	1. It will notify you about missing kernel drivers and provide a link for "more information."
	2. Click the link, download the .exe kernel drivers, and execute them on Windows.
	3. Now run `wsl --set-default-version 2`.
4. Install the Ubuntu distribution:
	1. Run `wsl --install -d Ubuntu`.
	- `-d` stands for "distribution."
5. Download VSCode onto your **Windows** machine:
	1. Search "VSCode" in your browser from your Windows machine (do not launch a browser from your WSL terminal).
	2. Download the version of VSCode for your Windows OS version.
	3. Launch the application and go to the extensions sidebar icon (which looks like four squares).
	4. Search for and download "WSL" and "Python."
6. In your terminal, launch WSL with the command `wsl`:
	1. If this is your first time launching WSL, it will prompt you to set the username and password for your Ubuntu distribution. Once this is done, you may close the Ubuntu terminal popup (not the Windows PowerShell terminal).
	- This effectively starts your Linux subsystem (like a separate OS) running inside your Windows OS. Anything you type in the terminal will be executed inside your Linux subsystem. To exit the subsystem, press `Ctrl+D`.
	- With only one distribution installed, you will automatically be running the Ubuntu distribution of Linux (each distribution is like a different flavor of the Linux OS).
7. Install FEniCSx:
	1. Go to the FEniCSx 0.8 [download page](https://fenicsproject.org/download/) and copy the three lines of code to download FEniCSx for **Ubuntu Linux via apt**. Paste the code into your terminal (right-click the active terminal line) and hit Enter or Y (for yes) for any prompts.
	- Note that the FEniCS project has two versions of their software: FEniCS (old) and FEniCSx (new). Be careful when searching and make sure you are on the documentation for FEniCSx, as this is the version that we use and is still being updated.
	- Note that the download may take a while (about 10 minutes with fairly fast Wi-Fi). Do not interrupt the download. A progress bar should appear at the bottom of the terminal indicating the download progress.
8. Install CUDA Nvidia:
	1. Update your entire WSL system via `sudo apt-get update`. This updates all of your packages (bits of downloaded code, in addition to the baseline code to run the subsystem, the kernel).
	- "apt" is a package manager. It is a piece of code that downloads packages from the internet using the name of the package you give it; it also removes, updates, and formats packages.
	2. Install CUDA Nvidia with `sudo apt-get install -y nvidia-cuda-toolkit`.
	3. Check to see that WSL can now see your GPU with `nvidia-smi`. You should see a table being generated with the name of your graphics card somewhere in that table.
9. Run your VSCode in your WSL session:
	1. Open VSCode in Windows.
	2. After you install the WSL extension, you should see a new sidebar icon that looks like a monitor—if you hover over it, it should say "Remote Explorer"—click on it.
	3. Make sure that the drop-down menu labeled "WSL Targets" is expanded.
	4. Hover over the Ubuntu distribution strip and, on the right side, click the icon that looks like a new tab or window. Upon hovering over the icon, it should say "Connect in New Window." Now, VSCode is running virtually in your WSL subsystem. The Python environment running inside the virtual VSCode session can now see the FEniCSx 0.8 package installed inside your WSL's PATH.
	5. Alternatively, you could navigate within your wsl terminal to the directory of your choice and open it within a vscode instance using `code .`
10. Create a file:
	1. Click "Create New File." VSCode will prompt you to specify the directory for the file.
	2. By default, it will give you the option of `/home/your_username/testfile.py`, but I would change it to `/home/your_username/codeprojects/testfile.py` for better organization. Upon pressing Enter, VSCode will ask if you want to create the new directory called "codeprojects." Click "OK."
	
	- Congratulations! You have now successfully installed FEniCSx 0.8 on Windows via WSL. All files created within your virtual VSCode session can be saved and reopened, persisting between sessions. You can even see the files you created during your WSL session in Windows File Explorer.
	
	- To reopen WSL anytime, just repeat steps 3 and 6, open your previous file, and start coding.
	- When coding, any error messages you encounter pertaining to missing packages can usually be solved with `pip install` or `apt install`

## Errors that might be encountered
### Packages are not installed
1. Follow the error to install the packages using apt or pip
### Jupyter kernel crashes because it has bad xserver connection
1. At the moment, there seems to be no solution to this error. It seems that the frame buffer is not able to reach the pyvista plotting module causing inevitable segmentation errors.
2. It seems unreliable to try to get Fenics running on windows as a single update in any of its dependencies might cause a new error, halting progress.