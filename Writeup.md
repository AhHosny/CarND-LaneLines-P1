# **Finding Lane Lines on the Road** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)


### My pipeline consists of the following steps:
---
1.Converting image to grayscale

2.Applying a Gaussian blur to the image

3.Applying Canny edge detection

4.Masking the image so that only the region of interest is processed

5.Running the Hough transform to identify lines

6.Converting those lines into single straight lines

7.Smoothing the result with a moving average filter

8.Plotting the lines on top of the image

### Draw single lines
---
**In order to draw a single line on the left and right lanes, I modified the function draw_lines().This function works as follows:**

1.Separate the right and left line based on their slope

2.Average the line ending x,y coordinates for each side

3.Calculate the slope and intercept of each average line

4.Using the slope and intercept, extend the lines to the bottom and apex of the lane

5.Update the moving average of the last few lines and the new lines

6.Plot the moving average lines

### Potential shortcomings
---
**Smoothing of line**

In the videos the detected lane lines are jittering quite bad, especially in the challenge video. A smoothing between the frames would solve this.


### Possible improvements
---
While this pipeline works on the first two videos, I am getting a float infinity error on the optional third video.
The challenge video is hard because there is very little contrast between the yellow line and the light surface. Besides having lots of shadows, tire marks and other noise. Some tweaking will be required. If I figure this issue out, I will resubmit.
