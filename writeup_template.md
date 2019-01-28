# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report



---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My image processing pipeline consisted of following steps:

1. Convert RGB image to grayscale.
2. Apply Canny edge detection.
3. Get the size of the image and calculate the vertices for image masking.
4. Now apply Hough transform to detect lines
5. Overlap the detected lines to the initial image.


* Converted the initial image using OpenCV API cv2.cvtColor()
* Detected the edges using canny API cv2.Canny(img, low_threshold, high_threshold)
    low_threshold : threshold for the minimun gradient magnitude
    high_threshold : threshold for the maximum gradient magnitude such that strong edges and noise is supporessed.

* Next step is to apply a mask to the original image. For that we need to calculate the region of the mask.
* Region of mask is the area of the lane in which car is moving.
* Region of mask helps to remove the unwanted objects so that the required area (Lane lines) are targeted.
* Next step is to find the lines using Hough Transform.
* I've modified draw_lines() to find the lines and make the pipelines on the provided image.


