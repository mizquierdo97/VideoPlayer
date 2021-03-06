# Video Player

### What is a Video Player?

A video player, also known as media player, is a program that allows the reproduction, in this case of video format files, Such as AVI, MP4, MPEG and many more.
Some of the most famous programs are VLC Media Player, DivX and QuickTime.


<img src="http://simosystems.eu/images/vlc.gif" width="150"><img src="http://images.apple.com/euro/quicktime/download/images/icon_qt_big.jpg" width="150"><img src="http://www.albinoblacksheep.com/download/icon/wmp.png" width="150">



### How it works?

The main process consists of three parts:

First, the information contained in the file is read.

Then, this information is passed by the specific codec with which the video has been encoded, in order to read the information that contained the original file. There are two types of codecs, lossless and lossy.

Finally, once we have this information, we store them in memory so they can be read.
![](http://i1152.photobucket.com/albums/p485/mikimik1997/Process_zps2xgitvkv.jpg)



Once we have all the video in memory, each frame we take the respective information obtained and it's painted on the screen.

### Our Video Player
In our case, we will use the Video For Windows library, 
which although outdated, allows to play videos very simply. 
Like all libraries it has its advantages and disadvantages:

Advantages:
Very intuitive and easy to start working with.
Simple and intuitive

Disadvantages:
Little documentation
Low flexibility
Supports few video codecs: MRLE, Cinepak, Intel Indeo, Microsoft Video 1


Although the disadvantages would be very noticeable if we needed to do something very complex,
 they are not so important in small projects.

For our program, we will use SDL2 to play the video on screen using the textures, we will explain later.

![](http://cdn.makeuseof.com/wp-content/uploads/2015/03/lossless-vs-lossy-compression-dragonfly.png)

Diferences between lossles and lossy 

### First steps

Before starting to write code, we must take into account that the 
program will not be able to play all types of video,
So we must first adapt the format of the video that we will need.

To do this, we must open the program that we use to render video (in this case Adobe Premiere) or any with which we are accustomed to work.
We import the video that we want to reproduce in our program and export it in the following format and with the following codec:

![](https://i.gyazo.com/d3bbb92adfbeee68da6b1ad6aa73c09e.png) ![](https://i.gyazo.com/2c1390f2c98b8023fbd084ffe28109b9.png)
![](https://i.gyazo.com/6dd00c99f9549e308e0a975f5b3b77f5.png)

Keep in mind that this codec does not compress the file and that it can take up a lot of memory.

Once we have the video and we can reproduce it in our project :)

## TODOs


### TODO 0
Init library and header:
You will need Vfw.h, dshow.h and vfw32.lib

### TODO 1
Init the Video

```markdown
App->video->Initialize("Video Name.avi")
```
### TODO 2
Every frame you should take one frame of the video. Remember to cap max frames from your program to frames per second of the video.


### TODO 3
Create a surface. This surface will recieve the data of actual frame.

You can use SDL_CreateSurfaceFrom
![](http://i1152.photobucket.com/albums/p485/mikimik1997/BUFFER_zpssdsmq4ab.gif)


### TODO 4
Now you can convert the surface to a texture and Blit it. Remember to go to next frame.

At this point, the video should be reproduced

<img src="https://i.giphy.com/XreQmk7ETCak0.gif" width="400">


### TODO 5
Clean the surface and texture.

### TODO 6
When you finish, clean the avi files used.


## More Documentation

### About video compression and codecs
Video Compression: <https://www.youtube.com/watch?v=qbGQBT2Vwvc>

Codecs: <https://www.youtube.com/watch?v=GhWki9a7s18>

### Video For Windows
Microsoft Documentation: <https://msdn.microsoft.com/es-es/library/windows/desktop/dd757708(v=vs.85).aspx>

Video For Windows tutorial with OpenGl: <http://nehe.gamedev.net/tutorial/playing_avi_files_in_opengl/23001/>


### Direct Show
Microsoft Documentation: <https://msdn.microsoft.com/en-us/library/windows/desktop/dd375454(v=vs.85).aspx>

### VLC
Documentation: <http://www.videolan.org/developers/vlc/doc/doxygen/html/group__libvlc.html>
