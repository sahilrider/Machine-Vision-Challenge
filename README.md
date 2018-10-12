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

# Flower Freshness Index

## Problem Statement
In Hotels, flowers are kept in flowerpots to create ambient experience. This looks
good till the flowers are fresh. When flowers are wilted, the effect is reversed.. So it is important to check the
freshness and keep it changed to retain the high level customer experience. This manual task can be automated
using machine vision. Continuous monitoring can be done using camera feed instead of random checks carried
by human.
<br>
For challenge purpose, consider set of flowers and confirm the freshness index

## Approach
<ul>
<li>For this challenge a scraped various types of flowers image from google.
<li>I divided entire image into two classes <i>fresh</i> and <i>wilted</i> and three sets which are <i>train</i>, <i>validation</i> and <i>test</i> set.
<li>I built a CNN model which is then trained on train data and validated on the validation dataset.
<li>After hyperparameter tuning, I tried my best to reduce overfitting.
<li>Further, Model is tested on the test data and prediction was made.
</ul>

## Model

<img src="Flower Freshness Index/model_summary.jpg" title="Model Summary">

## Result

Training Set Accuracy :   85.03% <br>
Validation Set Accuracy : 83.99% <br>
Test Set Accuracy : 77.5% <br>

<img src="Flower Freshness Index/predict_fresh.jpg" title="Fresh Flower">
<img src="Flower Freshness Index/predict_wilted.jpg" title="Wilted Flower">

## How to Use this notebook

### Method 1 : On Google Colab
<ul>
<li>Unzip the data file
<li>Upload whole folder to google drive
<li>Open notebook using Google Colab
<li>Turn on GPU acceleration
<li>Run the notebook
</ul>

### Method 2 : Using Anaconda

<ul>
<li> Install all dependencies
<li> Unzip data file
<li> Launch Jupyter Notebook using Anaconda navigator
<li> Run the notebook
</ul>

# Baggage Fitment Index

## Problem Statement
Normally overhead cabins in the aircraft are constrained by dimensions. So oversized baggage creates a lot of problems including delay when they are allowed to board the cabin. So before onboarding the passenger, baggage needs to be measured and indicate the customer to drop to luggage section. Few airports have physical model to do this task of fitment check. However it is cumbersome and time consuming, so it is advisable to use machine vision techniques so that customer need not do any additional task, thus creating superior customer experience.
<br>
For this challenge, assume two views of the camera are available.

## Approach
