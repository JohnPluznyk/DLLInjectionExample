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
In order to run this program you need to pass two arguments to it when using it via the terminal.  The first argument should be the process name your wish to inject your DLL file into and the second should be the path to the DLL file.  (usage: Injector_LoadLibrary <process name> <path to dll>).  

Create Remote Thread:
---------------------

find Pid By Name:
------------------
