1.0.	Introduction:
Object detection is a computer vision that uses programming to detect any object by using cameras, sensors, etc. Along with detecting it also get other information of that object such as type, location, date, time, etc. Its basic use in captioning, detecting, counting, tracking, etc. Detecting the object using deep learning is something to experiment on. And for that purpose, we decided on some steps and then worked according to the timeline created in the Gantt chart. They are as below: 
a)	Collecting the data, 
b)	Apply Pre-processing steps such as describing a total number of data, knowing data types, getting full information, finding missing values are present or not, cleaning the data, tokenizing text, etc. And visualize the data using the graphical method. To have a basic idea about ongoing things by observing the cleaned data.
c)	Model Building is an important step to get the best accuracy for the system. So, in short, it is done by dividing the data into 2 parts i.e., training data & test data. And changing the values helps to reach proper accuracy.
d)	Then performing User Interface i.e., GUI. For this purpose, planned to be creating a web page that is similar looking to google trends. But here, the new experiment is creating GUI but without using the flask library.
e)	Performing final tests to validate our project. All these steps are explained in detail as follows.

2.0.	 Collecting Data:
Usually, while working with any project many people prefer the well-furnished dataset whether it is in form of a table, videos, or images. For this Object detection project, we used our own recorded videos and images. From the time when decided to work on this project, also started recording the videos (recorded nearly 100 videos) but when it applied to the codes it creates the error. So first, for detecting vehicles 3 lines were drawn, the middle one for reference line, and the surrounding two for identifying the direction (whether vehicle going upward or downward). Now, the errors are due to the side angle (i.e. wrong angle), the cars will pass from the side, nothing will pass from between So, this way nothing is detected. Then, restart recorded the videos again but now considering the angle (from the bridge and high-level area), keeping the internet and location on ( to extract the video and image information such as date, time, area, location, etc). Thus, this way recorded own videos and click images.

3.0.	Pre-processing:
For this project, worked in 2 phases. i.e., implementation and User Interface. A detailed explanation is given below to know this project well. So, basically for this project inputs are videos and images which were recorded by us by keeping proper angle in mind, to count the vehicles such as cars, trucks, etc. The steps are as follows. Like checking missing values (it doesn’t have any missing values), cleaning data, removing stop words, etc. 
3.1.	Import the Required Libraries
The  Object Detection uses a list of various libraries as given below and for the user interface it uses cv2, moviepy, and os libraries for GUI, etc. The cv2 is a Video capture class open CV library used to import data from video and images. Using this library multiple processes are done on image and video. The tracker project file is a resource that consists of a zip file containing entire zip project files which consist of videos, images, HTML documentation and metadata as shown in figure 1 below:
![image](https://user-images.githubusercontent.com/74827127/170532804-524580ff-3420-4cc5-b3e0-d689b9ac23f8.png)
 
Figure 1: Import the required Libraries

3.2. Creating CSV variable to save useful Metadata
So, for saving the extracted data created a CSV variable using Metadata. Metadata is all about videos data. It helps in getting useful data from a large amount of big data. Mostly, it consists of a title, description, categories, etc. So, a CSV variable is created as shown in figure 2.

![image](https://user-images.githubusercontent.com/74827127/170532873-437e63a2-42c2-4f8e-bee8-2750b77f661f.png)

Figure 2: Created CSV file for Metadata

3.2.	Draw line for vehicle motion detection
      Next, an important step in drawing a line (works as a sensor) is to detect the motion of vehicles. So, need to draw 3 lines. The middle line is drawn and considered as a reference, while the surrounding two other lines are drawn for detecting the direction of vehicles. The upper first line is used for upward direction & the bottom line is for counting downward vehicles as shown in figure 3 below in an image.

![image](https://user-images.githubusercontent.com/74827127/170532905-c1b10527-4975-4cfe-88e2-7733f6fc6ed0.png)

Figure 3: Draw 3 lines for vehicle motion detection

 
3.4. Load and Display Data
For further processing display the loaded data from data CSV files which displays some names which can be detected by this system. It includes some names such as vehicles, animals and other things. Thus, displaying data be compared with the new output as shown in figure 4 below:
![image](https://user-images.githubusercontent.com/74827127/170532971-6eadf005-b317-4ab1-a546-fd2bd5d16ff7.png)
 
Figure 4: Load and display data
4.0.	 YOLO Model:
For modelling the ML Models are used such as Logistics, Linear, Regressions, etc. for getting better accuracy. For this object detection using deep learning opted YOLO uses neural networks and provides real-time object detection. YOLO means You Only Look Once. It is an algorithm based on regression, in this method it selects the part of an image along with classes and bounding boxes for the whole image. It works in two steps a) Detecting object regions and b) Classifying the object-related information. It is used to predict a class of following objects and specify object-related location such as longitude-latitude (i.e., location), video type, video size, date, time, etc. This algorithm is popular because of its speed and accurate result as it works at 45 FPS high speed. It is well-known for image classification, object detection, and pattern or text recognition and a subdomain of computer vision. Traditionally, neural networks were used for this purpose and now YOLO is used with bounding boxed and class probabilities with confidence as shown in figure 5 below:

![image](https://user-images.githubusercontent.com/74827127/170533393-b07c0992-cff1-4998-a05a-80b0fe3eb268.png)

Figure 5: YOLO Model

4.1.	YOLO (Intersection over Union method)
When the simple intersection is applied it has one con that it will detect the object but also detect the surrounding objects (along with the object) which can be considered as noise which can affect the system accuracy. To eradicate the intersection problem a perfect solution will be using Union over Intersection by using the formula given below. It will remove the bounding boxes problem which occurs in a simple intersection process. So, in this IOU method, first, take intersecting area between the bounding box and surrounding areas and this will cover the total area of both bounding boxes. Thus, intersection divided by Union gives the ratio of overlap total area as equation given below: ………………………………………….…..equation (1)
4.2.	Extracting Information Metadata
As explained earlier Metadata consists of useful data. It is just a context and description of the process data. It helps to organize, find, and understand data. When giving the videos and images in the system, it will give lots of data in unstructured form, then after cleaning it and extracting useful data and then arranging them, it will give something this in output, which consists of various information regarding the video, camera, store, etc. As shown here, the filename is ‘IMG_4074.mov’, file size is 27 MB, file type- .mov, and other information as shown in figure 6.

![image](https://user-images.githubusercontent.com/74827127/170533444-0375ee01-4e30-4eff-8838-f595d2eb0b6e.png)

Figure 6: Extracting information using Metadata

The next, step is to arrange this data in proper structure form, after removing punctuations, etc. So, here, the useful information we need is Date, time, and location (longitude and latitude). Thus, this is the data we required for further use, so eliminate all other data.
![image](https://user-images.githubusercontent.com/74827127/170533474-2751af0b-1651-47e7-99ff-bfde0984514c.png)

Figure 7: Extracting useful information 

Now, load the video files from the Capstone project file as shown in figure 8 below. Now, consider 2 columns one for videos and the other for the location of that videos. As shown here, we loaded 219 videos and the same number of locations.

![image](https://user-images.githubusercontent.com/74827127/170533506-40b4afbb-2e1b-404c-b9d0-195519e5e6ba.png)

Figure 8: Extracting data from given videos 

The column on the top left column of videos expanded in this part. It will show the increment and decrement of values belonging to the following number of vehicles such as car, bus, truck, etc as shown in figure 9. Different columns for increments and decrements depending on directions upward and downward.
 ![image](https://user-images.githubusercontent.com/74827127/170533523-bc4a2108-e18f-4a07-9d4d-e3fdeac0e56f.png)

Figure 9: Getting values depending on  directions 
5.0.	 User Interface
   The User Interface is something related to machines, it is a point in which the human user interacts with machine systems such as computers, applications, etc. The aim of creating UI is to make the user experience easy and effective. The ‘Object Detection using Deep Learning ‘project was prepared by using the YOLO model along with various other libraries and Metadata for extracting useful data. For the Graphical User Interface (GUI) we proposed the web page but this time without using the flask library. So, faced various challenges in processing and uploading data.  It is used to easily access and understand the concept behind data in a very simple manner. As it brings together various concepts from various interactions, visual design and information architecture as it is easy to understand web applications, and websites.
5.1.	Creating Web page
Basically, for creating a website or application flask library is used but for this webpage, proposed something new. For that get the idea from the Google trends page, so created a somewhat similar page including various locations, one main locality, time representations hourly and in minutes. Below is the web page link that will direct the user to the following page as given below:
 ![image](https://user-images.githubusercontent.com/74827127/170533559-51b88b8a-a2d1-4498-a798-fa8ff3b90e74.png)

Figure 10: Hourly traffic at various locations

As shown in the figure the line below the merged data will show the hourly data if we vary the pointer. Like now, from 5:00 to 6:00 shows traffic as it is considered as peak hour. It can be varied and can detect the traffic areas. So, this will eliminate the drawbacks for google maps. And similar to this the colour shows different types of traffic. Like light yellow is used for less traffic, orange for moderate traffic and red for highest traffic routes as it can be seen here in the above figure. And it shows 4 windows, 3 for various locations as named here Location_1, Location_2 and Location_3, while the big window on the left side shows the combinations of all 3 locations into one frame. And here, for locations, we considered the New York cities and 3 different cities to get different locations and different traffic. 
And this hourly data can be classified into minutes also as shown in figure 11. And here also it will vary according to a different time. It is reflected format which is converted from hourly into minutes to get information about each minute.
 ![image](https://user-images.githubusercontent.com/74827127/170533604-b0b0f2f5-81ca-402b-a624-574dc11e77d7.png)

Figure 11: Hourly time in minutes. 

6.0. Conclusions 
       After working on the “Object Detection using Deep Learning“ project, we can conclude that Yolo can be considered the best model for object detection and also successfully did the Graphical User Interface by applying a new concept. And mainly, it will eradicate the drawbacks of other map sites. Most important is that it can be useful to the government by various means for maintenance, development and other purposes.


7.0. References
1)	Aryan Garg, “Understanding of YOLO v3”, IEEE Journal, 2017 International Conferences, pp-200, 28760. December 2019.
2)	Grace Karimi, Yolo: Object Detection, an undergraduate student at Maseno University, Section Journal, EngEd Community, 2021
3)	Satya Mallick, Object tracking using Open CV, Article Learn Open CV, 159 comments, February 2017.
4)	Ayush Gupta, Getting started with object tracking library, Analytics Vidhya Journal, Data Science Blogathon, August 2021.
5)	I. Benarji, Graphical User Interface, 	Advance Technology Industrial, 24th European Symposium on Computer Vision, 2017

Web App: https://share.streamlit.io/surjitsingh790/streamlit-front-end/main/Testapp.py
