## OxRAM-Robot-Arm: Chess Piece Recognition (my first Machine Learning project)

Hi, this is one task within the Project OxRAM-Robot-Arm: https://github.com/OxRAMSociety/OxRAM-Robot-Arm

My background is materials science. I am focus on electrochemicamistry. So no robot background. I will make this blog easy to read for everyone. So if I can get this work, you can get it work. :)

### Story

Yeah, to increase the readability, let's start from a story. I am an materials scientist working on energy storage. I am familiar with beakers and lab work. My only experiences with coding is learning C++ years before to pass the exam... Zero experiences of Machine Learning and Robot. Happy.

I started to learn 3D printing in 2019 and was very lucky to get access to various of 3D printers (Form2, MarkForged M2, UltimakerS5, Photocentric, Solidscape). I spent about half a year to learn each of them from scratch. Two FMD. One SLA. One DoD. One DLP. I got familiar with different filaments, resins and print heads. Each printer has its own advantages and limitations (avoiding the word 'disadvantages'). Then I was able to fix some problems of them and do the maintainess. Also able to match the application with printers (from materials and resolution point of view). A bit proud. 

Then 2020 was a bit special. I had more time to hug my computers and explore coding. From MatLab to Python, step by step, all small tasks. In 2020, I gained some programme skill. 

So in the skill set pocket, there is a '3D printing'. There is a 'programming'. Let's try to find some interesting application to merger them together and learn from practice! Yeah! ROBOT!

Then I found the university society  https://github.com/OxRAMSociety and this OxRAM-Robot-Arm project. I love this team. All team members are very patient with all my questions. I started my very first Robot and Machine Learning journey. 

### 1. Objective
This project is to build a robotic arm using open source softwares and 3D printed parts. The first application is to play chess. One of the first steps for the arm is to recognize a chess piece via machine learning techniques. Which come to the theme of this Blog (finally). 

### 2. Lable images (LabelImg)

The first step is to label the images. The package that I am using is LabelImg (https://github.com/tzutalin/labelImg) on Mac. 

### 3. YOLO

Then I use YOLO to achieve the machine learning.




### 4. Trials on Pawn recognition

## 1) First test to get a feeling of the workflow

Believe me, it is always good to start from a small amount of data to try and get a feeling of the workflow. 
I got 20 images. Lable them one by one. And then did the training. After some debug, there is no error message anymore! Although it was only able to recgnize the pawn in a easy image as the following.

## 2) Increase the size of testing data

## 3) Result analysis

## 4) Lable to top of the chess piece only

## 5) Result analysis No. 2


### 5. Trials on Knight recognition

So, here is my first success on Machine Learning, and 


```markdown


You can use the [editor on GitHub](https://github.com/hzgezi-nims/RobotArm.ChessPieceRecognition.github.io/edit/main/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.
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

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/hzgezi-nims/RobotArm.ChessPieceRecognition.github.io/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
