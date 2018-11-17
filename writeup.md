# **Finding Lane Lines on the Road** 

### By: Bryan Campbell

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images_output/grayscale.jpg "Grayscale"
[image2]: ./test_images_output/gaussian_blur.jpg "Gaussian Blur"
[image3]: ./test_images_output/canny.jpg "Canny Edge Detection"
[image4]: ./test_images_output/mask.jpg "Mask"
[image5]: ./test_images_output/hough_lines.jpg "Hough Lines"
[image6]: ./test_images_output/weighted_img.jpg "Weighted Image"


---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 8 steps. 

#### 1. Applying the grayscale transform

![alt text][image1]

#### 2. Applying a Gaussian Noise kernel

![alt text][image2]

#### 3. Canny Edge Detection

Instead of endlessly applying the low and high threshold to see what had the best outcome over all of the images I added an auto canny script to figure it out.

![alt text][image3]

#### 4. Applied an image mask to only capture lane lines

![alt text][image4]

#### 5. Created image with annotated lane lines

![alt text][image5]

##### a. Applied Hough Lines to get an array of line coordinates

#### 6. Merged annotated lane lines with original image

![alt text][image6]

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
