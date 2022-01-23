<h1>Odometer Reader Program For SONIC AUTOMOTIVE</h1>
(Complete Prototype Phase on 20200218)
<h2>Computer Vision Code: Read Numbers from  Odometer</h2>


<h1>Modeling</h1>
<h1>Description of model</h1>
<i>•	The model takes the following steps to achieve the reading of the mileage:

•	Uses EasyOCR to find all text detections in the image

•	Determines whether a ‘mi’ or ‘km’ text is found.

•	Confirms that the text found is not ‘mph’ or ‘km/h’

•	Checks the largest length detections and confirms if a number is attached to it, and returns it.

•	If a number is not attached to the label text found, returns largest number found in image.

•	We created our own Class in order to store important information about our detections, such as the top-left and bottom-right coordinates of the bounding box, as well as the detected text.
</i>

(Please note that the subscription was taken off and this information could be found in the local drive)

<b>Experimentation:</b><br />
1.	How did you set up your experiments?

•	By examining the provided Sonic Automotive images, we noticed a correlation between the position of the mileage number and its label, whether it was ‘mi’, ‘miles’, or ‘km’. That correlation allowed us to locate the mileage number after a series of steps that start with applying an optical character recognition algorithm over the image.<br />
2.    Datasets used: Train, Validation, Test split information

•	Since our method, unlike a neural network, does not depend on training/testing split to work, we used approximately 20 images out of the provided 100 to come up with our solution. These 20 images had the mileage number in different locations compared to its label, and allowed us to come up with a solution that works with most of them.<br />
3.	Experimentation with different models or methods

•	Besides this method, we are still experimenting with a neural network with training data composed of 2000+ images. So far, our current method has proved to work quite reliably with the images, but we will be checking whether a neural network would offer better results.<br />

<h1>Results<h1>
<h2>Model Performance</h2>

<b>Accuracy = TP+TN / ALL | 98 + 0 / 113 = 87 %</b><br />

<b>Precision = TP / TP+FP | 98 / 98 + 12 = 89 %</b><br />

<b>Recall = TP / TP+FN | 98 / 98 + 3 = 97 %</b><br />


<h1>Literature Review</h1>

<b>1.	Motivation for using method (cite any existing work that you have used)
Effectiveness of Modern Text Recognition Solutions and Tools for Common Data Sources
By: Kirill Smelyakov, Anastasiya Chupryna, Dmytro Darahan and Serhii Midina
http://ceur-ws.org/Vol-2870/paper15.pdf
The motivation for using this method was sparked by the above mentioned paper, which describes the effectiveness and performance of two different OCR tools, EasyOCR and TesserOCR. The paper gave us the idea of detecting a key feature in the Odometer (the mileage label) using an OCR tool, and then determining the mileage based on that information.</b><br />




<b>Sample Images:<br/></b>
Analog Meter

<img src=https://github.com/hkbtotw/OdometerReader/blob/master/TestImage/IMG_9090_[052334]_A1.JPG alt="Analog" width="200"/>

Detected Analog Digitbar by Object Detection

<img src=https://github.com/hkbtotw/OdometerReader/blob/master/TestImage/DetectedAnalog.jpg alt="Detected Analog" width="400"/>

Digital Meter:

<img src=https://github.com/hkbtotw/OdometerReader/blob/master/TestImage/IMG_9028[278168].JPG alt="Digital" width="200"/>

Detected Digital Digitbar by Object Detection

<img src=https://github.com/hkbtotw/OdometerReader/blob/master/TestImage/DetectedDigital.jpg alt="Detected Digital" width="400"/>
