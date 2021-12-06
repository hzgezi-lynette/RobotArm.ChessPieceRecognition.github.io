## OxRAM-Robot-Arm: Chess Piece Recognition (my first Machine Learning project)

Hi, this is one task within the Project OxRAM-Robot-Arm: https://github.com/OxRAMSociety/OxRAM-Robot-Arm

My background is materials science. I am focus on electrochemicamistry. So no robot background. I will make this blog easy to read for everyone. So if I can get this work, you can get it work. :)

### Story

Yeah, to increase the readability, let's start from a story. I am an materials scientist working on energy storage. I am familiar with beakers and lab work. My only experiences with coding is learning C++ years before to pass the exam... Zero experiences of Machine Learning and Robot. Happy.

I started to learn 3D printing in 2019 and was very lucky to get access to various of 3D printers (Form2, MarkForged M2, UltimakerS5, Photocentric, Solidscape). I spent about half a year to learn each of them from scratch. Two FMD. One SLA. One DoD. One DLP. I got familiar with different filaments, resins and print heads. Each printer has its own advantages and limitations (avoiding the word 'disadvantages'). Then I was able to fix some problems of them and do the maintainess. Also able to match the application with printers (from materials and resolution point of view). A bit proud. 

Then 2020 was a bit special. I had more time to hug my computers and explore coding. From MatLab to Python, step by step, all small tasks. In 2020, I gained more programme skill. 

So in the skill set pocket, there is a '3D printing'. There is a 'programming'. Let's try to find some interesting application to merger them together and learn from practice! Yeah! ROBOT!

Then I found the university society  https://github.com/OxRAMSociety and this OxRAM-Robot-Arm project. I love this team. All team members are very patient with all my questions. I started my very first Robot and Machine Learning journey. 

### 1. Objective
This project is to build a robotic arm using open source softwares and 3D printed parts. The first application is to play chess. One of the first steps for the arm is to recognize a chess piece via machine learning techniques. Which come to the theme of this Blog (finally). 

### 2. Lable images (LabelImg)

1. The first step is to label the images. The package that I am using is LabelImg (https://github.com/tzutalin/labelImg) on Mac. 
<img width="1432" alt="image" src="https://user-images.githubusercontent.com/63501033/120902137-9d07cd80-c636-11eb-9054-16785963e0c3.png">
The annotation was saved in a txt. file in the same folder. All images were labeled in the same way. 
2. Save all the labeled image and annotation in a folder 'images' and compress to 'images.zip'
3. Upload this 'images.zip' file to my google drive under folder named 'yolov3


### 3. YOLOv3

Then I use YOLO to achieve the machine learning.Follow the instruction in https://pysource.com/2020/04/02/train-yolo-to-detect-a-custom-object-online-with-free-gpu/

### 4. Trials on Pawn recognition

## 1) First test on 30 images

Believe me, it is always good to start from a small amount of data to try and get a feeling of the workflow. 
I got 30 images. Lable them one by one. And then did the training for half an hour. After some debug, there is no error message anymore! Although it was only able to recgnize the pawn in a easy image as the following.

<img width="76" alt="image" src="https://user-images.githubusercontent.com/63501033/120901414-9414fd00-c632-11eb-8ce7-ea6be6b7b0fc.png">


## 2) Increase the size of testing data set to 67 images
It seems that the previous methodology works. Now let's increase the size of testing data set to 67 images, and train the model for 6 hours. 
The results show both success and fail cases.
Success cases:
1) All the image that with only a pawn can be recognized
 <img width="51" alt="image" src="https://user-images.githubusercontent.com/63501033/120902551-ece79400-c638-11eb-9eab-983cefb0dc03.png">
2) Pawns in different focal plane can be recognized
<img width="203" alt="image" src="https://user-images.githubusercontent.com/63501033/120902582-143e6100-c639-11eb-9246-3b7c4d6f89d6.png">
3) Pawns in different tilting angle can be recognized
<img width="282" alt="image" src="https://user-images.githubusercontent.com/63501033/120902612-3637e380-c639-11eb-8446-511d332fca72.png"> <img width="234" alt="image" src="https://user-images.githubusercontent.com/63501033/120902616-3df78800-c639-11eb-810e-d203d1f6da04.png">
4)Pawns from different camera angles can be recognized
 <img width="217" alt="image" src="https://user-images.githubusercontent.com/63501033/120902571-04bf1800-c639-11eb-8616-c2d7ea513cfa.png"> <img width="106" alt="image" src="https://user-images.githubusercontent.com/63501033/120902626-46e85980-c639-11eb-8f8e-3e03dc943d5b.png"><img width="160" alt="image" src="https://user-images.githubusercontent.com/63501033/120902816-62079900-c63a-11eb-9b8c-7816cea18068.png">
5)A pawn among other chess pieces can be recognized
<img width="98" alt="image" src="https://user-images.githubusercontent.com/63501033/120902632-5667a280-c639-11eb-8613-fdad5f5482ca.png">
<img width="175" alt="image" src="https://user-images.githubusercontent.com/63501033/120902640-654e5500-c639-11eb-8b94-d09929feeb74.png">

Fail cases:

1)Can't recognize a pawn behind other object

<img width="204" alt="image" src="https://user-images.githubusercontent.com/63501033/120902662-78612500-c639-11eb-810a-e87fe56ca673.png">

2)In some cases, can't recognize a pawn in a different focal plain

<img width="184" alt="image" src="https://user-images.githubusercontent.com/63501033/120902687-a0e91f00-c639-11eb-938d-d4ff4e85bb08.png"><img width="153" alt="image" src="https://user-images.githubusercontent.com/63501033/120902678-962e8a00-c639-11eb-9f6f-a73d4c4865ec.png">

3)Can't distinguish a pawn that the top share the same color with the bottom, when it is close with other chesspiece.

<img width="182" alt="image" src="https://user-images.githubusercontent.com/63501033/120903211-c9264d00-c63c-11eb-91c6-2cac0f998401.png">

4)Can't recognize a pawn when it is decorated with a crawn to the top. 

<img width="430" alt="image" src="https://user-images.githubusercontent.com/63501033/120902704-b8c0a300-c639-11eb-86b9-b47c9b2f1989.png">

Pacially seccess:
In an image with darker light, and different focal plan, only some of the pawn can be recognized.

<img width="385" alt="image" src="https://user-images.githubusercontent.com/63501033/120902708-bf4f1a80-c639-11eb-8ac7-e46409f718d5.png">

Always success when the top part could distinguished from the bottom via color.
<img width="620" alt="image" src="https://user-images.githubusercontent.com/63501033/120902738-f6253080-c639-11eb-8537-5b2f2039fddd.png">

Always fail in some cases (the light is less real)
<img width="476" alt="image" src="https://user-images.githubusercontent.com/63501033/120903066-e870aa80-c63b-11eb-86c8-f529f6f4686c.png">


Conclusions:
1) It is recommended to design/3D print a chess piece that the top is distinguished from the bottom
2) From the failed cases, it is possible that the bottom of the pawn is not necessary to be labeled in the 1st step. 

## 3) Lable to top of the chess piece only (63 training images and 4 testing imzges)
In this trial, I only label the top of the pawn. 

<img width="152" alt="image" src="https://user-images.githubusercontent.com/63501033/120903098-181fb280-c63c-11eb-8e17-da1ae290c3d8.png">

Following the same training workflow, the learning results are much more reliable. All the previous failed cases are successed this time.

<img width="228" alt="image" src="https://user-images.githubusercontent.com/63501033/120903190-a136e980-c63c-11eb-8073-9db673a5d7f0.png">
<img width="240" alt="image" src="https://user-images.githubusercontent.com/63501033/120903194-a5fb9d80-c63c-11eb-87aa-ead347e69b8c.png">
<img width="280" alt="image" src="https://user-images.githubusercontent.com/63501033/120903195-aa27bb00-c63c-11eb-84ab-f1ad0f5e2e98.png">
<img width="242" alt="image" src="https://user-images.githubusercontent.com/63501033/120903214-cf1c2e00-c63c-11eb-96d0-3f00bd740036.png">
<img width="235" alt="image" src="https://user-images.githubusercontent.com/63501033/120903228-df340d80-c63c-11eb-9054-ff8e00530b91.png">
<img width="286" alt="image" src="https://user-images.githubusercontent.com/63501033/120903235-e3f8c180-c63c-11eb-9e9a-0464eedd75ea.png">
<img width="236" alt="image" src="https://user-images.githubusercontent.com/63501033/120903238-e65b1b80-c63c-11eb-8f08-58428b745c95.png">

Interestingly, although the pawns with a different focal plain can be recognized, the middle pawn with a crown is still challenging. 

<img width="532" alt="image" src="https://user-images.githubusercontent.com/63501033/120903278-35a14c00-c63d-11eb-944c-401177180e8a.png">

Testing images (the machine never see these images before):

<img width="421" alt="image" src="https://user-images.githubusercontent.com/63501033/120903453-19ea7580-c63e-11eb-8f82-c5b866a0d9c0.png">

<img width="265" alt="image" src="https://user-images.githubusercontent.com/63501033/120903455-1e169300-c63e-11eb-81a8-64ab5f2e5970.png">

<img width="313" alt="image" src="https://user-images.githubusercontent.com/63501033/120903457-2078ed00-c63e-11eb-9e79-a36cedc69add.png">

<img width="579" alt="image" src="https://user-images.githubusercontent.com/63501033/120903459-22db4700-c63e-11eb-8b53-4d3657b370fc.png">

Conclusion:
1) To label the top only helps the following training
2) The training results is good enough for the robot arm to recognize the pawn in a real life image. 

Limitation:

Lack of training images. All the images are online resources. Although I achieve a good training model with only 63 images, more training image will defenitly increase the stability and realiablity in following steps. 

### 5. Trials on Knight recognition
To apply the previous methodology on Knight recognition, 167 images are used as training data. The results shown that it is important that the image has a high-enough resolution. Which relates to the camero and reaction spead of the carema that attached on the robot arm. 

(to be continued...)


So, here is my first success on Machine Learning. The purpose of this work is to suppor the robot arm project... 



