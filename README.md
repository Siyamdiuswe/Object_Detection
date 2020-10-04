# H1 YOLO: Real-Time Object Detection on windows 10


Followed this site: https://gitee.com/suiyifan/darknet#how-to-compile-on-windows-legacy-way

or: https://www.youtube.com/watch?v=DjO9UtSON6U&t=448s&ab_channel=ZODtheTechGOD

*How to compile on Windows (legacy way):
Installation part:
1.Install graphics card drivers
2.Install cuda 10.1
3. install cuDNN 7.6(copy files to cuda 10.1(Nvidia gpu toolkit))
4. install opencv 3.x (path: C:\opencv_3.0\opencv\build\include & C:\opencv_3.0\opencv\build\x64\vc14\lib)
5. Install microsoft visual stidio(2017 better)
6.Add paths of cuda 10.1 on environment path
7. open build\darknet\darknet.sln, set x64 and Release (https://hsto.org/webt/uh/fk/-e/uhfk-eb0q-hwd9hsxhrikbokd6u.jpeg)
and do the: Build -> Build darknet. Also add Windows system variable CUDNN with path to CUDNN: https://user-images.githubusercontent.com/4096485/53249764-019ef880-36ca-11e9-8ffe-d9cf47e7e462.jpg

8. Find files opencv_world320.dll and opencv_ffmpeg320_64.dll (or opencv_world340.dll and opencv_ffmpeg340_64.dll) in C:\opencv_3.0\opencv\build\x64\vc14\bin and put it near with darknet.exe

9. Check that there are bin and include folders in the C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0 if aren't, then copy them to this folder from the path where is CUDA installed

***10. Finally buid darknet
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
Then you'll notice darknet.exe on C:\darknet-master\build\darknet\x64 file

#Useful Commands

cd

cd

cd C:\darknet-master\build\darknet\x64

.............................................................................

###For Images from data directory

darknet.exe detect cfg/yolov3.cfg yolov3.weights data/dog.jpg

darknet.exe detect cfg/yolov3.cfg yolov3.weights data/eagle.jpg

darknet.exe detect cfg/yolov3.cfg yolov3.weights data/horses.jpg

darknet.exe detect cfg/yolov3.cfg yolov3.weights data/person.jpg

darknet.exe detect cfg/yolov3.cfg yolov3.weights data/scream.jpg

darknet.exe detect cfg/yolov3.cfg yolov3.weights data/giraffe.jpg

darknet.exe detect cfg/yolov3.cfg yolov3.weights E:/test.jpg


.............................................................................

Multiple Images:

darknet.exe detect cfg/yolov3.cfg yolov3.weights

E:/test.jpg

data/dog.jpg

data/person.jpg

***Ctrl-C to exit the program once you are done


.............................................................................

Changing The Detection Threshold:

Doesn't work with multiple images


darknet.exe detect cfg/yolov3.cfg yolov3.weights E:/test.jpg -thresh 0


.............................................................................

Tiny YOLOv3:


darknet.exe detect cfg/yolov3-tiny.cfg yolov3-tiny.weights data/dog.jpg


.............................................................................

YOLOv4:

darknet.exe detector demo cfg/coco.data cfg/yolov4.cfg yolov4.weights data/dog.jpg


.............................................................................


Real-Time Detection on a Webcam:


darknet.exe detector demo cfg/coco.data cfg/yolov3.cfg yolov3.weights

darknet.exe detector demo cfg/coco.data cfg/yolov3-tiny.cfg yolov3-tiny.weights

darknet.exe detector demo cfg/coco.data cfg/yolov4.cfg yolov4.weights


.............................................................................


video file:
 
cd

cd

cd C:\darknet-master\build\darknet\x64

darknet.exe detector demo cfg/coco.data cfg/yolov3.cfg yolov3.weights E:/test.mp4


cd

cd

cd C:\darknet-master\build\darknet\x64

darknet.exe detector demo cfg/coco.data cfg/yolov3-tiny.cfg yolov3-tiny.weights 

E:/test.mp4


cd

cd

cd C:\darknet-master\build\darknet\x64

darknet.exe detector demo cfg/coco.data cfg/yolov4.cfg yolov4.weights E:/test.mp4

