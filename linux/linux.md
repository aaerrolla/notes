### Finding correct executable 
    How to know which is the command on disc is responsible for a program running 

    readlink 

    Finding the proper executable can be challenging. For example, for Firefox, the proper executable is /usr/lib/firefox/firefox, not the one in /usr/bin.

    Here are a few ways you can find the correct file:

    readlink /proc/$(pgrep <executable> | head -1)/exe
    Ex: readlink /proc/$(pgrep firefox | head -1)/exe
    
    ```
    readlink /proc/$(pgrep firefox | head -1)/exe
    /usr/lib/firefox/firefox-bin
    ```


    Look for a process in your task manager. Some task managers may provide the executable path. Or readlink /proc/<PID>/exe.


