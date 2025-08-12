### Youtube

#yt-dlp 

install
    sudo apt update && sudo apt install yt-dlp
how to download
    yt-dlp <url-of-youtube-video>
how to download best quality 
    yt-dlp -S 


### GNOME Terminal

    how to scroll Text

    Scroll up     <shift> + PgUp   
    Scroll down     <shift> + PgDown

### Video Streaming  Recording 

#ffmpeg
    
    install
        sudo apt update && sudo apt install ffmpeg

    usage:
        ffmpeg -i <input_file>  # show information about the input_file 

### Transmission Daemon - Setting up command line transmission 

    install 
    ```
    sudo apt install transmission-daemon transmission-cli
    ```
    access the rpc url  at localhost:9091
    default username/password   transmission
    
    configure/ change default password , white list , etc 

    - first stop transmission-daemon
    ```
    sudo systemctl stop transmission-daemon.service 
    ```
    if you want to disable the service , so that  it wont start along with system
    
    ```
    sudo systemctl disable now transmission-daemon.service
    ```
    - edit the config ,  config file at /etc/transmission-daemon/settings.json
        change ipwhitelisting, password ,  download dir etc 
    
    start the service  
    ```
    sudo systemctl start transmission-daemon.service 
    ```

   #### Manage torrent with  transmission-remote 

    use  --auth <user:pass>  with  below commands 

    list torrent - transmission-remote -l
    stop a torrent -  transmission-remote -t <torrent_id> -S 
    start a torrent -   transmission-remote -t <torrent_id> -s 

    remove torrent  -   transmission-remote -t <torrent_id> -r 


###  Git, GitHub


#github

gh  :  tool to manage github repositories

install gh

sudo apt update && sudo apt install gh

- using gh
    initialize : 
        gh auth login   # follow steps 
            
    list repo
        
    create repo
    


- setup github ssh keys


