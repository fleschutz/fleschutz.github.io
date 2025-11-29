![Image](/img/BannerBoat.jpg)

(image: pixabay.com)

Application Crash Dumps on Windows
==================================

**Crash dumps (aka 'memory dumps' or 'core dumps') are extremely helpful to investigate application crashes or hangups. To retrieve and to analyze those crash dumps follow the instructions below. This works on all versions of Windows beginning with Vista and Server 2008.**

... ![Bild](/img/MF.png) *By Markus Fleschutz* 🕑 *May 06, 2020*

## 1️⃣ Enable Crash Dumps

Per default, no crash dump is written when a Windows application stops abnormally. To enable this perform the following:

1. Open the **Registry Editor** (e.g. by executing `regedit`).
2. Search for the registry key `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\Windows Error Reporting\LocalDumps`
3. Create the key (if not present already): right click → New → Key, and name it `LocalDumps`

**NOTE:** Windows updates sometimes set this back to the default value, therefore disabling crash dumps!

## 2️⃣ Make the Application crash

Reproduce the problem and make the application crash. In case the application hangs start the **Task Manager** (e.g. by pressing `Ctrl-Alt-Delete`), right click on the process and select `Create dump file`.

Start the **Windows Explorer** and locate the dump file in the folder `%LOCALAPPDATA%\CrashDumps` with the file suffix `.dmp`.

Example dump file: `C:\Users\<USERNAME>\AppData\Local\CrashDumps\App.exe.3652.dmp`

**NOTE:** per default, this folder contains up to 10 dump files only! Dump #11 will replace the oldest dump file #1. Therefore, move dump files into another folder to avoid removal!

## 3️⃣ Analyze the Crash Dump

Please note that this step is done by software developers only. Normally, you just send the crash dump file with a bug report to the software vendor.

1. Copy the `.dmp` crash dump file into the folder where the corresponding `.pdb` files are located (this will help to resolve the symbolic names of functions, methods, variables, etc.).
2. Double-click the `.dmp` file - this should start the development environment (e.g. *Visual Studio*) and should show basic information. Then click on `Debug with Native Only` (in the upper right corner)
3. Click on `Call Stack` (lower right corner) to view the call stack of the current thread and the local variables.
4. Do not forget to select the other threads to check their call stack and the local variables!
