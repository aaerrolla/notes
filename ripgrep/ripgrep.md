###  ripgrep 
    faster sensible grep
    
    Install
    ```
    sudo apt install ripgrep
    ```

    Configuration:  no spesific config

    Use:
    rg "pattern_to_search"  # this will  list all the files that contains pattern in all sub directories

    rg "pattern" /path/to/file   # serach in /path/to/file 

    rg "pattern" /path/to/dir  # serach in /path/to/dir 

    use option  -i  for case insensitive search 
    option  -F   # no regEx interpretation 

    -A 3  # show 3 lines after the matching line 
    -B 3 # show 3 lines beofer the matching line 

    
