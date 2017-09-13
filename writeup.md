# **Finding Lane Lines on the Road** 
---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 
1. Convert images to grayscale.
2. Blur images by Gaussian algorithm。
3. Use Canny edge detection to find edges.
4. Implementing a Hough transform on edge detected Image inside the region of interest.
5. Draw lines based based on Hough transform results and merge the pictures of lines onto original images. 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...
1. Seperate lines into the left and the right based on the slopes.
2. Calculate the average slope and the average middle position of lines for the left and the right respectively.
3. Get the left and right line based on the slope and middle position.
4. Draw part of lines above only inside the region of interest.

### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when 
there were shadows on the road which were recognized as lines by mistake 
then it would influence the result of the average slope and middle positions.

Another shortcoming could be the region of interests would not be likely fixed,
it would change on drivings.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to filter out the exceptions of lines by removing those ones of the most largest slopes,
we should keep the lines with close slopes.
