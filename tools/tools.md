### Youtube

#yt-dlp 

install
    sudo apt update && sudo apt install yt-dlp
how to download
    yt-dlp <url-of-youtube-video>
how to download best quality 
    yt-dlp -f bestvideo+bestaudio/best  <URL>
    
    How it works 
    This command instructs yt-dlp to select the best separate video and audio streams and merge them, 
    or to fall back to the best combined format if merging isn't possible. 
    You can specify the container format, such as MP4, with --merge-output-format mp4.
 
    Command Breakdown
    yt-dlp: The command-line tool itself. 
    -f bestvideo+bestaudio/best: This is the key for best quality: 
    bestvideo: Selects the highest quality video stream. 
    bestaudio: Selects the highest quality audio stream. 
    +: Tells yt-dlp to download these streams separately. 
    /best: If separate streams are not available or cannot be merged, it will default to the best format available as a single file. 
    --merge-output-format mp4: (Optional) Specifies the container format, like MP4, for the final merged file. 
    <URL>: The URL of the video you want to download

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

        # extract audio from video 
        ffmpeg -i <input_file>  -o 

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


