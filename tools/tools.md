### Youtube

#yt-dlp 

install
    sudo apt update && sudo apt install yt-dlp
update yt-dlp  to latest 
    yt-dlp -U 

how to download video

    yt-dlp <url-of-youtube-video>

how to download best quality 

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


