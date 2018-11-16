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

My pipeline consisted of 5 steps. 

##### 1. Grayscale

![alt text][image1]

##### 2. Gaussian Blur

![alt text][image2]

##### 3. Canny Edge Detection

![alt text][image3]

##### 4. Mask

![alt text][image4]

##### 5. Hough Lines

![alt text][image5]

##### 6. Weighted Image

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
