### Youtube

#yt-dlp 

install
    sudo apt update && sudo apt install yt-dlp
update yt-dlp  to latest 
    yt-dlp -U 

how to download video

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

    yt-dlp  -f bestvide+bestaudio/best   <URL>

    -- use authentication 

    yt-dlp  --cookies-from-browser chrome  -f bestvide+bestaudio/best  <URL>



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
        Example : record a left monitor  in  a  two monitor system   wihout audio
         ffmpeg -video_size 1920x1080 -framerate 30 -f x11grab -i :1.0 screen_left.mp4

         record right 
          ffmpeg -video_size 1920x1080 -framerate 30 -f x11grab -i :1.0+1920,0 screen_right.mp4

          with audio  left screen

          list audio  devices  using pipe-wire 
          pw-cli  list-objects | grep node.name

          "alsa_output.usb-Logitech_Logi_USB_Headset_000000000000-00.analog-stereo"


           ffmpeg -video_size 1920x1080 -framerate 30 -f x11grab -i :1.0  -f pulse -i alsa_output.usb-Logitech_Logi_USB_Headset_000000000000-00.analog-stereo screen_-c:v libx264 -preset ultrafast -c:a aac left.mp4

        -- convert / extract audio from  video 

        ffmpeg -i  <video>  audio.wav 





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


