## Video Player

### What is a Video Player?

A video player, also known as media player, is a program that allows the reproduction, in this case of video format files. Such as AVI, MP4, MPEG and many more.
Some of the most famous programs are VLC Media Player, DivX or QuickTime.


<img src="http://simosystems.eu/images/vlc.gif" width="150"><img src="http://images.apple.com/euro/quicktime/download/images/icon_qt_big.jpg" width="150"><img src="http://www.albinoblacksheep.com/download/icon/wmp.png" width="150">



### How it works?

The main process consists of three parts:

First, the information contained in the file is read.

Then, this information is passed by the specific codec with which the video has been encoded, in order to read the information that contained the original file. There are two types of codecs, with lost or no loss.

Finally, once we have this information, we store them in memory so they can be read.
![](http://i1152.photobucket.com/albums/p485/mikimik1997/Process_zps2xgitvkv.jpg)



Once we have all the video in memory, each frame, it takes the respective information obtained and is painted on the screen.

### Our Video Player
In our case, we will use the Video For Windows library, 
which although outdated, allows you to play videos very simply. 
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

### First steps

Before starting to write code, we must take into account that the 
program will not be able to play all types of video,
So we must first adapt the format of the video that we will need.

To do this, we must open the program that we use to render video (in this case adobe Premiere) or any with which we are accustomed to work.
We import the video that we want to reproduce in our program and export it in the following format and with the following codec:

Keep in mind that this codec does not compress the file and that it can take up a lot of memory.

Once we have the video and we can reproduce it in our project :)

### TODOs


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

### TODO 5
Clean the surface and texture.

### TODO 6
When you finish, clean the avi files used.


### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/mizquierdo97/VideoPlayer/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
