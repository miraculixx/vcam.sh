vcam.sh - virtual cam with background for Linux
===============================================

This uses v4l2loopback and ffmpeg to create a virtual cam and merge
it with a background using the chromakey filter. Thus it works best
with a greenscreen. Different configurations can be set up using a
configuration file and easily selected from the command line.

Installation
------------

    $ vcam --install

    
This installs all dependencies and set ups an initial configuration
file. 

Usage
-----

Note the `vcam` command is a non-blocking command that launches ffmpeg 
in the background. Use multiple calls to start and stop the cam or
view its status.s

This sets up the vcam.

    # use the default background
    $ vcam

Preview cam image in browser.

    # you may have to select the "vcam" in browser settings
    $ vcam --view

Select a background. The list is generated from the vcam.ini config file.

    $ vcam --select /
    1) office
    2) private
    3) neutral
    4) shelf
    5) global
    #?

Show live vcam status

    $ vcam --status
    user  1192388  0.0  0.0   9248   744 pts/0    S+   15:00   0:00 grep ffmpeg
      overlay -> Stream #0:0 (rawvideo)
    Press [q] to stop, [?] for help
    [swscaler @ 0x55b00f28d400] deprecated pixel format used, make sure you did set range correctly
    Output #0, video4linux2,v4l2, to '/dev/video4':
      Metadata:
        encoder         : Lavf58.29.100
        Stream #0:0: Video: rawvideo (YUY2 / 0x32595559), yuyv422, 768x432 [SAR 1:1 DAR 16:9], q=2-31, 132710 kb/s, 25 fps, 25 tbn, 25 tbc (default)
        Metadata:
          encoder         : Lavc58.54.100 rawvideo
        frame= 4882 fps= 25 q=-0.0 Lsize=N/A time=00:03:15.28 bitrate=N/A dup=195 drop=0 speed=   1x    
        video:3163536kB audio:0kB subtitle:0kB other streams:0kB global headers:0kB muxing overhead: unknown
    
Stop the cam

    $ vcam --stop

Help
----

    $ vcam -h 
    
    vcam - virtual cam background for linux
    Copyright (c) miraculixx at github.com/miraculixx
    
    vcam [option]
    
    Options:
    --help          Display help
    --select=VALUE  Select configuration (VALUE=/ to show menu)
    --image=PATH    png file, PATH can be a local file or remote http:
    --size=VALUE    size, defaults to 640x480
    --output=VALUE  size, defaults to /dev/video4
    --camera=VALUE  size, defaults to /dev/video2
    --rate=VALUE    frame rate, defaults to 25
    --overlay=VALUE overlay position x:y, defaults to 100:0
    --crop=VALUE    crop position x:y, defaults to 200:200
    --blurred       blur background
    --install       install dependencies
    --stop          stop cam
    --status        show cam status
    --view          view cam in browser
    --config=PATH   config file, defaults to $HOME/.config/vcam.ini
    --edit          edit config
    

Image sources
-------------

The sample images are licensed as follows:

* [office] camback_640480.png Unsplash License (https://unsplash.com/license)
  Photo by <a href="https://unsplash.com/@alesiaskaz?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Alesia Kazantceva</a> on <a href="https://unsplash.com/s/photos/office-background?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
 
* [shelf]  shelfview_640480.png Unsplash License (https://unsplash.com/license)
  Photo by <a href="https://unsplash.com/@luisabrimble?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Luisa Brimble</a> on <a href="https://unsplash.com/s/photos/book-shelf?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a> 

* [private] privateview_640480.png Unsplash License (https://unsplash.com/license)
  Photo by <a href="https://unsplash.com/@andriyko?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Andriyko Podilnyk</a> on <a href="https://unsplash.com/s/photos/room-background?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
  
* [ocean] niceview_640480.png Unsplash License (https://unsplash.com/license)
  Photo by <a href="https://unsplash.com/@goodspleen?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Alexandre Chambon</a> on <a href="https://unsplash.com/s/photos/ocean-view-room?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
  
* [neutral] neutralview_640480.png Unsplash License (https://unsplash.com/license)  
  Photo by <a href="https://unsplash.com/@woods?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Joe Woods</a> on <a href="https://unsplash.com/s/photos/white-wall?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
  

License
-------

MIT License

Copyright (c) 2022 miraculixx @github.com

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
