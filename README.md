*NOTE* This file just purely serves as documentation to understand the process of how DLL injection works.

The main goal of this project is to understand how DLL injection works.  All of the code needed to run this program can be found within the main.cpp file.
This code was taken from this blogpost https://kylehalladay.com/blog/2020/11/13/Hooking-By-Example.html .  The link to the following bloogpost is mainly
about function hooking and how it works on a x64 system.

The reamineder of this readme file will just be documentation on how a program like this DLL Injection program works.  BTW this is my first time reading C++
I am using ChatGPT plus to understand the functionality of this program.  I suggest to uye ChatGPT if any questions arise.

DOCUMENTATION on main.cpp
-------------------------

Main:
-----
In order to run this program you need to pass two arguments to it when using it via the terminal.  The first argument should be the process name your wish to inject your DLL file into and the second should be the path to the DLL file.  (usage: Injector_LoadLibrary [process name] [path to dll]).  If the two arguments are not passed the printHelp function will be exectued and the program will terminate.

After the two arguemnts are passed the program will reach this line of code (createRemoteThread(findPidByName(argv[1]), argv[2]);).  This line of code will take the two arguments passed.  The program will first execute the function (findPidByName) which is passed the processe's names that you wish to inject a DLL file into.  By passing in the process name the function will find the necessary data needed to identify that specific processes with in memory.

The second argument is simply the path to the DLL file that you wish to inject into the process.

find Pid By Name:
------------------
Starting with the first line of code we know that the function is going to return a data type of DWORD whihc stand for "Double Word" this is a data type defined in the Windows API. It is an unsigned 32-bit integer.  The function is designed to return a process ID (PID) which is typically a 'DWORD' value in the windows API.  The PID is used to uniquely identify a running process.  If the function successfully finds a process with the specified name, it returns the PID of that process.

The function take the a single argument, 'name', which is of type char pointer.

Variables "h" and "singleProcess":
'HANDLE h':
	- 'HANDLE' is a windows-specific types used for various objects, including process snapshots
'PROCESSENTRY32 singleProcess':
	- 'PROCESSENTRY32' is a structure that holds the information about a process


Question:  Would the program be simpler in terms of code, if one could just simply enter the PID instead of typing the process name.

Create Remote Thread:
---------------------
