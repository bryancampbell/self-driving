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

My pipeline consisted of 6 steps. 

#### 1. Apply the grayscale transform

![alt text][image1]

#### 2. Apply a Gaussian Noise kernel

![alt text][image2]

#### 3. Appliy Canny Edge Detection

Instead of endlessly applying the low and high threshold to see what had the best outcome over all of the images, I added an auto canny script to figure it out.

![alt text][image3]

#### 4. Apply an image mask to only capture lane lines

![alt text][image4]

#### 5. Created image with annotated lane lines based on the image

##### a. Applied Hough Lines to get an array of line coordinates found in the image
##### b. Using the array of lines, created an estimated left and right lane represented by a single line each

I modified the draw_lines() by first eliminating lines I thought were bad: single pixels, or lines with a given slope but on the wrong side of the image.  I also thought about looking at the line slopes and eliminating lines that had odd slopes that were odd compared to other slopes for each line within a group on a given side but I didn't get that far.  I then split the lines in 2 groups: left and right lane lines.  From there I took the median slope of the lines in each group as well as the median line based on each's coordinates as the "single slope and line of truth".  Lastly I took these single lines per lane and stretched them to the bottom and mid top of the image.  However, this trick would only work for lanes that go in a straight line

![alt text][image5]

#### 6. Merged annotated lane lines with original image

![alt text][image6]


### 2. Identify potential shortcomings with your current pipeline

I noticed in my video the lines jumped around and weren't perfect.  The gray, blur, and canny I think may be just fine, but I believe the problem lies in the drawing of lines.  I was thinking that I could do a better job of filtering bad lines.  Currently I am using the median slope and lines for each side but there may be a better way to select the right slope and line.  I was thinking about doing the average slope and eliminating lines that's slope were too off compared to the average but it seems unpredictable so I didn't.  I was also thinking about changing the mask so anything on the inside of the lanes was also not visible.  I also thought about cutting the image in half (left and right side) and changing the hough line calculation more.  Lastly I was wondering if there was a way to crawl up the line from bottom to top and eliminate lines that were too eradict compared to the previous line.

The problem with my approach is that it doesn't account for lines with curves.  I was considering instead of doing 1 line, do 10 lines vertically with different slopes.  Each attempting to use a median slope and median line within that section and if none were found than using the average of the line above and below.  Also the mask would have to be very different.

Another problem is if there were cars between the lanes.  I was thinking about applying another mask just in case.

Lastly I wondered how well this would work at night and if the formula needs to change at all.


### 3. Suggest possible improvements to your pipeline

Next to each problem in this document I also had ideas on how I thought I could make it better. Beyond that, I was thinking I could add more debugging.  I added some.  For instanced I added lines for where the mask should be to make sure that lane lines weren't cut out.  I also added code to detect for images with bad lane lines and to print them out so I can see the process and where I went wrong.  There were many other things I was thinking about adding for myself but ended up not.  For instance, making a matrix of different kernel, canny threshold, hough line possible values and creating images with each variance at different times to see what the ideal numbers would be.
