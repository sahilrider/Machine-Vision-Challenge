# Machine-Vision-Challenge

This Machine Learning Challenge was given from TTH unit by TCS.
There were four sub challenges. They are:
<ol>
<li>Floor cleanliness index
<li>Flower freshness index
<li>Container filled index
<li>Baggage fitment index
</ol>

I have attempted to solve two challenges which are <i>Flower freshness index</i> and <i>Baggage fitment index.</i>

<hr>

## Flower Freshness Index

### Problem Statement
In Hotels, flowers are kept in flowerpots to create ambient experience. This looks
good till the flowers are fresh. When flowers are wilted, the effect is reversed.. So it is important to check the
freshness and keep it changed to retain the high level customer experience. This manual task can be automated
using machine vision. Continuous monitoring can be done using camera feed instead of random checks carried
by human.
<br>
For challenge purpose, consider set of flowers and confirm the freshness index

### Approach
<ul>
<li>For this challenge a scraped various types of flowers image from google.
<li>I divided entire image into two classes <i>fresh</i> and <i>wilted</i> and three sets which are <i>train</i>, <i>validation</i> and <i>test</i> set.
<li>I built a CNN model which is then trained on train data and validated on the validation dataset.
<li>After hyperparameter tuning, I tried my best to reduce overfitting.
<li>Further, Model is tested on the test data and prediction was made.
</ul>

### Model

<img src="https://github.com/sahilrider/Machine-Vision-Challenge/blob/master/Flower%20Freshness%20Index/model_summary.JPG" title="Model Summary">

### Result

Training Set Accuracy :   85.03% <br>
Validation Set Accuracy : 83.99% <br>
Test Set Accuracy : 77.5% <br>

<img src="https://github.com/sahilrider/Machine-Vision-Challenge/blob/master/Flower%20Freshness%20Index/predict_fresh.JPG" title="Fresh Flower">
<img src="https://github.com/sahilrider/Machine-Vision-Challenge/blob/master/Flower%20Freshness%20Index/predict_wilted.JPG" title="Wilted Flower">

### Testing Project

#### Method 1 : On Google Colab
<ul>
<li>Unzip the data file
<li>Upload whole folder to google drive
<li>Open notebook using Google Colab
<li>Turn on GPU acceleration
<li>Run the notebook
</ul>

#### Method 2 : Using Anaconda

<ul>
<li> Install all dependencies
<li> Unzip data file
<li> Launch Jupyter Notebook using Anaconda navigator
<li> Run the notebook
</ul>

<hr>

## Baggage Fitment Index

### Problem Statement
Normally overhead cabins in the aircraft are constrained by dimensions. So oversized baggage creates a lot of problems including delay when they are allowed to board the cabin. So before onboarding the passenger, baggage needs to be measured and indicate the customer to drop to luggage section. Few airports have physical model to do this task of fitment check. However it is cumbersome and time consuming, so it is advisable to use machine vision techniques so that customer need not do any additional task, thus creating superior customer experience.
<br>
For this challenge, assume two views of the camera are available.

### Approach

For solving this problem it is assumed that there are two views of the camera which are perpendicular to each other. Let us assume there is a scenario where luggages are passed and two perpendicular views of the luggage is captured. Now for measuring the dimension, we have taken a reference object whose dimensions are already known. Now as we know the dimension of the reference object, other's dimensions can be calculated wrt to that.
<br>
To solve this problem, I have used **opencv**.
<ul>
<li> First I applied Canny edge detection on the image.
<li> Found all the contours from the image
<li> Assumed the leftmost contour to be reference object and calculated pixelsPerMetric metric to calculate the dimensions.
<li> Calculated dimensions of all other contours.
<li> Assuming the baggage to be the largest object in the image. Dimensions of largest one is returned.
<li> From two images now we will have all the dimensions needed.
<li> These dimensions can be compared with the original constraints to see the baggage will fit or needs to be dropped.
</ul>

### Result

Original Dimension : 18 x 6 x 5.5
<br>
Observed Dimension : 18.88 x 6.52 x 6.14

Result can be improved by adding margin of error to the reference object.

### Testing Project

<ul>
<li> Install all dependencies 
<li> Write <i>python final.py</i> in command prompt, or
<li> Run the notebook using Anaconda
</ul>

# End Notes

Both challenges were solved in a span of 7 days. For increasing accuracy more time needs to be invested. All above mentioned projects are good and can be taken as a capstone project and they will yield good results.
