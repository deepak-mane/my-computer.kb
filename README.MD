# MY COMPUTER KNOWLEDGEBASE


1. [KEYBOARDS]
2. [Shutdown computer in 20min] 
```#shutdown /t 1200 /s```

### Import-Module : The specified module 'activedirectory' was not loaded because no valid module file was found in any module directory
For non-servers this requires Remote Server Administration Tools for Windows __
- Windows 7: http://www.microsoft.com/en-us/download/details.aspx?id=7887
- Windows 8: http://www.microsoft.com/en-us/download/details.aspx?id=28972
- Windows 10: https://www.microsoft.com/en-au/download/details.aspx?id=45520

### Download MP3 from YouTube using YouTube DL

Requirements
- Youtube DL : Download video from YouTube
- FFmpeg : Convert video to mp3
- Configuration
  - Linux Mint
  - Open add-on preferences (about:openwith)
  - Click Add button, then open following path: /usr/bin/gnome-terminal
  - In the newly created section, Click Edit button
```
Name : Youtube mp3
Arguments :
-e "youtube-dl --extract-audio --audio-format mp3 --audio-quality 0 -o '/home/username/Music/%(title)s.%(ext)s' %s"
Replace /home/username/Music as the path to your output directory
```
- Windows
  - Create a new directory by name youtube2mp3 (or any name) to contain the installation file. E.g. C:\Users\username\Documents\youtube2mp3
  - Copy youtube-dl.exe file into youtube2mp3 directory
  - Extract the downloaded file from FFmpeg, in bin directory, copy two files ffmpeg.exe and ffprobe.exe into youtube2mp3 directory
  - Adding youtube2mp3 directory to PATH Environment Variable (a.k.a. Windows System PATH)
  - Open add-on preferences (about:openwith)
  - Click Add button, then select path to youtube-dl.exe file in youtube2mp3 directory
  - In the newly created section, Click Edit button
```
Name : Youtube mp3
Arguments :
--extract-audio --audio-format mp3 --audio-quality 0 -o "C:/Users/username/Music/%(title)s.%(ext)s" %s
Replace C:/Users/username/Music as the path to your output dir
```

``` powershell
foreach ($song in get-content('C:\Users\deeps\songs_list.txt')) {
    # Start-Process -NoNewWindow -FilePath "E:\INSTALL\YOUTUBE\youtube-dl.exe" -ArgumentList "$song"

    $YoutubedlCommand = "youtube-dl.exe --extract-audio --audio-format mp3 --audio-quality 0 -o 'C:/Users/%USERNAME%/Music/%(playlist)s/%(playlist_index)s - %(title)s.%(ext)s' $song"
    Invoke-Expression "$YoutubedlCommand"
}
```
