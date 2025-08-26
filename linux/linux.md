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

### Installing Clamav antivirus 

https://wiki.debian.org/ClamAV

Install 


```
sudo apt install clamav clamav-daemon clamav-freshclam clamdscan
```

Enable Clamav service 

```
sudo systemctl is-enabled clamav-daemon && sudo systemctl status clamav-daemon
```


run the 'freshclam' command below to update your anti-virus database.

```
sudo freshclam
```

Enable freshclam service 

```
sudo systemctl enable --now clamav-freshclam
```

Check freshclam service is running 

```
sudo systemctl status clamav-freshclam
```

-- Scaning files / directories 

check first clamav daemon is running 

```
sudo systemctl status clamav-daemon
```
-- to scan single file 

    ```
    clamscan file.doc
    ```

-- to scan a directory 
    ```
    clamscan /home/
    ```

-- scan and show only infected files 
```
clamscan -i /home/
```

-- scan a directory recursively and print only infected files 

```
clamscan -i -r /home
```

--  move infected files to a directory  with  --move option 

```
clamscan -i -r --move=/home/$USER/infected /home/
```

--  NOTE  IMP   file size 

By default ClamAV will not scan files larger than 20Mb. In order to override that setting the options --max-filesize=2000M --max-scansize=2000M must be appended to the command. Where the size 2000M may be replaced as necessary by the user. An example is provided bellow.

```
clamscan --max-filesize=3000M --max-scansize=3000M --recursive=yes --infected /home
```

## Automatic Scanning and Real Time protection with ClamAV Daemon

dit the ClamAV daemon configuration '/etc/clamav/clamd.conf'


Insert the configuration below to configure automatic scan for directories such as '/home', '/etc', and '/var'. The '?ScanOnAccess' will enable real-time protection through the 'clamd' to scan files when they're accessed.

```
ScanOnAccess yes
OnAccessIncludePath /home
OnAccessIncludePath /etc
OnAccessIncludePath /var
```

Save the file and exit the editor.

Now run the 'systemctl' command below to start and enable the 'clamav-daemon' service.'

```
sudo systemctl restart clamav-daemon
```

Lastly, check the 'clamav-daemon' service status to ensure it is running.

```
sudo systemctl status clamav-daemon

```

Debugging ClamAV
The default log file for ClamAV is located in the '/var/log/clamav/clamav.log' file. You can check the log file with the 'tail' command below.
```
tail -f /var/log/clamav/clamav.log
```

Now run the 'tail' command below to check the log file for the 'freshclam' service that will automatically update your anti-virus database.
```
tail -f /var/log/clamav/freshclam.log
```

You can also monitor the ClamAV service status using the 'clamdtop' command.
```
clamdtop
```











