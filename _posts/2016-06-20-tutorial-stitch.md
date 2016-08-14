---
layout: default
categories: post
---

## Tutorial for stitching video with premiere and Hugin

The purpose was to use only Open-source software or solution but we start with premiere for the moment
Each part we do with premiere can be done with an other dedicated Open-source software
The only tricky part is maybe the audio synchronization...

## Process

### Synchronize and convert to frames with premiere

- Import all the video to premiere
 * all the video need to be rename, the first is the left video, 1.mpg, 2.mpg, 3.mpg....
- synchronize all the video together
 * select all the video on premiere -> right click -> "synchronize" (or "create multi-camera source sequence")
 * ![multi-cam](https://fablabwgtn.github.io/Mobile-360/images/create-multi-cam.png "multi cam synchronize")
 * select audio  -> Ok
 * ![audio synchronization](https://fablabwgtn.github.io/Mobile-360/images/audio-synch.png "audio synchronization")
 * verify if the video are synchronize
 * ![verification](https://fablabwgtn.github.io/Mobile-360/images/synchro.png "synchro verification")
- export frames
 * select the first left video
 * go to file -> export -> media
 * ![export media](https://fablabwgtn.github.io/Mobile-360/images/export-media.png "export")
 * change the output format, match the output size with the input, select a folder where you have to put all your picture set and name the file 1.tiff for the first one then increment for the others, change the frame rate if you need
 * ![export settings](https://fablabwgtn.github.io/Mobile-360/images/export-tiff.png "export settings")
 * export and wait
 * do it for all the video sequence

### Stitch the first panorama with Hugin

- select one set of image to make the pattern with Hugin and put in a separate folder
- rename they all to have something like that : 1abcd.tiff, 2abcd.tiff, 3abcd.tiff, 4abcd.tiff,...
- carefully do the first panorama with hugin
 * lot of tutorial on their website
 * ![hugin](https://fablabwgtn.github.io/Mobile-360/images/hugin.png "hugin")
- save the project with this name : xxxx.pto
- copy this project file into the folder with all the picture set

### Batch all the image set with custom software and Hugin batch tool

- batch copy the template project with processing tool (you can easily modify the source code to adapt to your project)
 * [hugin project copy tool](https://github.com/drachezoil/batch-hugin-project)
 * open the software "batch-Hugin"
 * select the pto project template on the right folder
 * set the start image index and the end index (if the picture are from 10000.tiff to 10952.tiff you put 0 to 952)
 * start the creation of all the project file
 * ![processing tool](https://fablabwgtn.github.io/Mobile-360/images/batch-processing.png "processing tool")
- batch stitch the image set with hugin batch tool
 * open hugin batch processor and select the folder with all the pto files
 * ![Hugin batch folder](https://fablabwgtn.github.io/Mobile-360/images/.png "Hugin batch folder")
 * wait until he have fully loaded all the project then start
 * then wait one night at least...

### Convert to a video with premiere

- copy all the output picture to an other folder (000.tiff to 952.tiff, not the 1000.tiff or 2432.tiff for example)
- import frames into premiere
 * file -> import -> select the right folder -> select only the FIRST panorama -> select "image sequence" -> OK
- add audio, effect, ...
- export to a video
 * move to the active project
 * file -> export -> media
 * change the output format, the fit, the output folder then export
 * ![export settings](https://fablabwgtn.github.io/Mobile-360/images/export-vid.png "export settings")

 Done!!!

## [Result](https://youtu.be/RmWAzwVhAo0)
