# Dll-Injection

This program can injects DLL into running processes using thread hijacking. No remote thread is created, only existing thread is used for injection.

The injector injects shellcode into the target process, and then a running thread in the target process is hijacked to execute the injected code. The injected code calls the LoadLibrary function to load the DLL.

Usage: ZwInjector [PID] [DLL name]

Flow of injection

1) Parse the DLL name and the target process ID from command line.

2) Allocate buffer for the shellcode and DLL name.

3) Copy the shellcode to the buffer.

4) Copy the DLL name to the end of shellcode.

5) Open the target process handle.

6) Allocate memory in the target process.

7) Find a running thread to hijack.

8) Get the context of the target thread.

9) Write the eip register to the shellcode.

10) Write the address of LoadLibrary to the shellcode.

11) Write the shellcode and DLL name to the target process.

12) Hijack a running thread in the target process to execute the shellcode.

13) The hijacked thread executes the shellcode. The shellcode calls the LoadLibrary function to load the DLL.

14) The shellcode returns, and the thread continue to execute its own code.

# FOR EDUCATIONAL ONLY USE WITH YOUR OWN RISK 

Please Support My Ass on YouTube :  https://www.youtube.com/channel/UC1Hu0kEfFYR1075s6WPr91w

Kesimpulannya ialah program ini dapat menginject Running Processes Menggunakan Thread Hijaccking, dan menggunakan Injector yang akan menginject shellcode ke Running Processes.

# Created By Ardean Bima Saputra [Zwinject]

My Portofolio : astrobox.epizy.com
