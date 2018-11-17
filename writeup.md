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

Instead of endlessly applying the low and high threshold to see what had the best outcome over all of the images, I added an auto canny script to figure it out.

![alt text][image3]

#### 4. Applied an image mask to only capture lane lines

![alt text][image4]

#### 5. Created image with annotated lane lines

![alt text][image5]

##### a. Applied Hough Lines to get an array of line coordinates
##### b. Using the array of lines, created an estimated left and right lane represented by a single line each

I modified the draw_lines() by first eliminating lines I thought were bad: single pixels, or lines with a given slope but on the wrong side of the image.  I also thought about looking at the line slopes and eliminating lines that had odd slopes that were odd compared to other slopes for each line within a group on a given side but I didn't get that far.  I then split the lines in 2 groups: left and right lane lines.  From there I took the median slope of the lines in each group as well as the median line based on each's coordinates as the "single slope and line of truth".  Lastly I took these single lines per lane and stretched them to the bottom and mid top of the image.  However, this trick would only work for lanes that go in a straight line

#### 6. Merged annotated lane lines with original image

![alt text][image6]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
