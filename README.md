**Advanced Lane Finding Project**

The goals / steps of this project are the following:

* Compute the camera calibration matrix and distortion coefficients given a set of chessboard images.
* Apply a distortion correction to raw images.
* Use color transforms, gradients, etc., to create a thresholded binary image.
* Apply a perspective transform to rectify binary image ("birds-eye view").
* Detect lane pixels and fit to find the lane boundary.
* Determine the curvature of the lane and vehicle position with respect to center.
* Warp the detected lane boundaries back onto the original image.
* Output visual display of the lane boundaries and numerical estimation of lane curvature and vehicle position.

[//]: # (Image References)

[output_project_video]: ./output_images/project_video.jpg "Project Video Output"
[output_challenge_video]: ./output_images/challenge_video.jpg "Challenge Video Output"
[output_harder_challenge_video]: ./output_images/harder_challenge_video.jpg "Harder Challenge Video Output"

[output_project_video_debug]: ./output_images/project_video_debug.jpg "Project Video Debug Output"
[output_challenge_video_debug]: ./output_images/challenge_video_debug.jpg "Challenge Video Debug Output"
[output_harder_challenge_video_debug]: ./output_images/harder_challenge_video_debug.jpg "Harder Challenge Video Debug Output"

[calibration1]: ./output_images/calibration1.jpg "calibration1.jpg"
[calibration2]: ./output_images/calibration2.jpg "calibration2.jpg"
[calibration3]: ./output_images/calibration3.jpg "calibration3.jpg"
[calibration4]: ./output_images/calibration4.jpg "calibration4.jpg"
[calibration5]: ./output_images/calibration5.jpg "calibration5.jpg"
[calibration6]: ./output_images/calibration6.jpg "calibration6.jpg"
[calibration7]: ./output_images/calibration7.jpg "calibration7.jpg"
[calibration8]: ./output_images/calibration8.jpg "calibration8.jpg"
[calibration9]: ./output_images/calibration9.jpg "calibration9.jpg"
[calibration10]: ./output_images/calibration10.jpg "calibration10.jpg"
[calibration11]: ./output_images/calibration11.jpg "calibration11.jpg"
[calibration12]: ./output_images/calibration12.jpg "calibration12.jpg"
[calibration13]: ./output_images/calibration13.jpg "calibration13.jpg"
[calibration14]: ./output_images/calibration14.jpg "calibration14.jpg"
[calibration15]: ./output_images/calibration15.jpg "calibration15.jpg"
[calibration16]: ./output_images/calibration16.jpg "calibration16.jpg"
[calibration17]: ./output_images/calibration17.jpg "calibration17.jpg"
[calibration18]: ./output_images/calibration18.jpg "calibration18.jpg"
[calibration19]: ./output_images/calibration19.jpg "calibration19.jpg"
[calibration20]: ./output_images/calibration20.jpg "calibration20.jpg"

[gray_calibration1]: ./output_images/gray_calibration1.jpg "gray_calibration1.jpg"
[gray_calibration2]: ./output_images/gray_calibration2.jpg "gray_calibration2.jpg"
[gray_calibration3]: ./output_images/gray_calibration3.jpg "gray_calibration3.jpg"
[gray_calibration4]: ./output_images/gray_calibration4.jpg "gray_calibration4.jpg"
[gray_calibration5]: ./output_images/gray_calibration5.jpg "gray_calibration5.jpg"
[gray_calibration6]: ./output_images/gray_calibration6.jpg "gray_calibration6.jpg"
[gray_calibration7]: ./output_images/gray_calibration7.jpg "gray_calibration7.jpg"
[gray_calibration8]: ./output_images/gray_calibration8.jpg "gray_calibration8.jpg"
[gray_calibration9]: ./output_images/gray_calibration9.jpg "gray_calibration9.jpg"
[gray_calibration10]: ./output_images/gray_calibration10.jpg "gray_calibration10.jpg"
[gray_calibration11]: ./output_images/gray_calibration11.jpg "gray_calibration11.jpg"
[gray_calibration12]: ./output_images/gray_calibration12.jpg "gray_calibration12.jpg"
[gray_calibration13]: ./output_images/gray_calibration13.jpg "gray_calibration13.jpg"
[gray_calibration14]: ./output_images/gray_calibration14.jpg "gray_calibration14.jpg"
[gray_calibration15]: ./output_images/gray_calibration15.jpg "gray_calibration15.jpg"
[gray_calibration16]: ./output_images/gray_calibration16.jpg "gray_calibration16.jpg"
[gray_calibration17]: ./output_images/gray_calibration17.jpg "gray_calibration17.jpg"
[gray_calibration18]: ./output_images/gray_calibration18.jpg "gray_calibration18.jpg"
[gray_calibration19]: ./output_images/gray_calibration19.jpg "gray_calibration19.jpg"
[gray_calibration20]: ./output_images/gray_calibration20.jpg "gray_calibration20.jpg"

[drawCorner_calibration1]: ./output_images/drawCorner_calibration1.jpg "drawCorner_calibration1.jpg"
[drawCorner_calibration2]: ./output_images/drawCorner_calibration2.jpg "drawCorner_calibration2.jpg"
[drawCorner_calibration3]: ./output_images/drawCorner_calibration3.jpg "drawCorner_calibration3.jpg"
[drawCorner_calibration4]: ./output_images/drawCorner_calibration4.jpg "drawCorner_calibration4.jpg"
[drawCorner_calibration5]: ./output_images/drawCorner_calibration5.jpg "drawCorner_calibration5.jpg"
[drawCorner_calibration6]: ./output_images/drawCorner_calibration6.jpg "drawCorner_calibration6.jpg"
[drawCorner_calibration7]: ./output_images/drawCorner_calibration7.jpg "drawCorner_calibration7.jpg"
[drawCorner_calibration8]: ./output_images/drawCorner_calibration8.jpg "drawCorner_calibration8.jpg"
[drawCorner_calibration9]: ./output_images/drawCorner_calibration9.jpg "drawCorner_calibration9.jpg"
[drawCorner_calibration10]: ./output_images/drawCorner_calibration10.jpg "drawCorner_calibration10.jpg"
[drawCorner_calibration11]: ./output_images/drawCorner_calibration11.jpg "drawCorner_calibration11.jpg"
[drawCorner_calibration12]: ./output_images/drawCorner_calibration12.jpg "drawCorner_calibration12.jpg"
[drawCorner_calibration13]: ./output_images/drawCorner_calibration13.jpg "drawCorner_calibration13.jpg"
[drawCorner_calibration14]: ./output_images/drawCorner_calibration14.jpg "drawCorner_calibration14.jpg"
[drawCorner_calibration15]: ./output_images/drawCorner_calibration15.jpg "drawCorner_calibration15.jpg"
[drawCorner_calibration16]: ./output_images/drawCorner_calibration16.jpg "drawCorner_calibration16.jpg"
[drawCorner_calibration17]: ./output_images/drawCorner_calibration17.jpg "drawCorner_calibration17.jpg"
[drawCorner_calibration18]: ./output_images/drawCorner_calibration18.jpg "drawCorner_calibration18.jpg"
[drawCorner_calibration19]: ./output_images/drawCorner_calibration19.jpg "drawCorner_calibration19.jpg"
[drawCorner_calibration20]: ./output_images/drawCorner_calibration20.jpg "drawCorner_calibration20.jpg"

[undistorted_calibration1]: ./output_images/undistorted_calibration1.jpg "undistorted_calibration1.jpg"
[undistorted_calibration2]: ./output_images/undistorted_calibration2.jpg "undistorted_calibration2.jpg"
[undistorted_calibration3]: ./output_images/undistorted_calibration3.jpg "undistorted_calibration3.jpg"
[undistorted_calibration4]: ./output_images/undistorted_calibration4.jpg "undistorted_calibration4.jpg"
[undistorted_calibration5]: ./output_images/undistorted_calibration5.jpg "undistorted_calibration5.jpg"
[undistorted_calibration6]: ./output_images/undistorted_calibration6.jpg "undistorted_calibration6.jpg"
[undistorted_calibration7]: ./output_images/undistorted_calibration7.jpg "undistorted_calibration7.jpg"
[undistorted_calibration8]: ./output_images/undistorted_calibration8.jpg "undistorted_calibration8.jpg"
[undistorted_calibration9]: ./output_images/undistorted_calibration9.jpg "undistorted_calibration9.jpg"
[undistorted_calibration10]: ./output_images/undistorted_calibration10.jpg "undistorted_calibration10.jpg"
[undistorted_calibration11]: ./output_images/undistorted_calibration11.jpg "undistorted_calibration11.jpg"
[undistorted_calibration12]: ./output_images/undistorted_calibration12.jpg "undistorted_calibration12.jpg"
[undistorted_calibration13]: ./output_images/undistorted_calibration13.jpg "undistorted_calibration13.jpg"
[undistorted_calibration14]: ./output_images/undistorted_calibration14.jpg "undistorted_calibration14.jpg"
[undistorted_calibration15]: ./output_images/undistorted_calibration15.jpg "undistorted_calibration15.jpg"
[undistorted_calibration16]: ./output_images/undistorted_calibration16.jpg "undistorted_calibration16.jpg"
[undistorted_calibration17]: ./output_images/undistorted_calibration17.jpg "undistorted_calibration17.jpg"
[undistorted_calibration18]: ./output_images/undistorted_calibration18.jpg "undistorted_calibration18.jpg"
[undistorted_calibration19]: ./output_images/undistorted_calibration19.jpg "undistorted_calibration19.jpg"
[undistorted_calibration20]: ./output_images/undistorted_calibration20.jpg "undistorted_calibration20.jpg"


[test1]: ./output_images/test1.jpg "test1.jpg"
[test2]: ./output_images/test2.jpg "test2.jpg"
[test3]: ./output_images/test3.jpg "test3.jpg"
[test4]: ./output_images/test4.jpg "test4.jpg"
[test5]: ./output_images/test5.jpg "test5.jpg"
[test6]: ./output_images/test6.jpg "test6.jpg"
[straight_lines1]: ./output_images/straight_lines1.jpg "straight_lines1.jpg"
[straight_lines2]: ./output_images/straight_lines2.jpg "straight_lines2.jpg"

[undistorted_test1]: ./output_images/undistorted_test1.jpg "Undistorted test1.jpg"
[undistorted_test2]: ./output_images/undistorted_test2.jpg "Undistorted test2.jpg"
[undistorted_test3]: ./output_images/undistorted_test3.jpg "Undistorted test3.jpg"
[undistorted_test4]: ./output_images/undistorted_test4.jpg "Undistorted test4.jpg"
[undistorted_test5]: ./output_images/undistorted_test5.jpg "Undistorted test5.jpg"
[undistorted_test6]: ./output_images/undistorted_test6.jpg "Undistorted test6.jpg"
[undistorted_straight_lines1]: ./output_images/undistorted_straight_lines1.jpg "Undistorted straight_lines1.jpg"
[undistorted_straight_lines2]: ./output_images/undistorted_straight_lines2.jpg "Undistorted straight_lines2.jpg"

[binary_test1]: ./output_images/binary_test1.jpg "Binary test1.jpg"
[binary_test2]: ./output_images/binary_test2.jpg "Binary test2.jpg"
[binary_test3]: ./output_images/binary_test3.jpg "Binary test3.jpg"
[binary_test4]: ./output_images/binary_test4.jpg "Binary test4.jpg"
[binary_test5]: ./output_images/binary_test5.jpg "Binary test5.jpg"
[binary_test6]: ./output_images/binary_test6.jpg "Binary test6.jpg"
[binary_straight_lines1]: ./output_images/binary_straight_lines1.jpg "Binary straight_lines1.jpg"
[binary_straight_lines2]: ./output_images/binary_straight_lines2.jpg "Binary straight_lines2.jpg"

[color_binary_test1]: ./output_images/colorBinary_test1.jpg "Color Binary test1.jpg"
[color_binary_test2]: ./output_images/colorBinary_test2.jpg "Color Binary test2.jpg"
[color_binary_test3]: ./output_images/colorBinary_test3.jpg "Color Binary test3.jpg"
[color_binary_test4]: ./output_images/colorBinary_test4.jpg "Color Binary test4.jpg"
[color_binary_test5]: ./output_images/colorBinary_test5.jpg "Color Binary test5.jpg"
[color_binary_test6]: ./output_images/colorBinary_test6.jpg "Color Binary test6.jpg"
[color_binary_straight_lines1]: ./output_images/colorBinary_straight_lines1.jpg "Color Binary straight_lines1.jpg"
[color_binary_straight_lines2]: ./output_images/colorBinary_straight_lines2.jpg "Color Binary straight_lines2.jpg"

[linear_line_fit_straight_lines1]: ./output_images/LinearLineFit_straight_lines1.jpg "Linear Fit Line straight_lines1.jpg"
[linear_line_fit_straight_lines2]: ./output_images/LinearLineFit_straight_lines2.jpg "Linear Fit Line straight_lines2.jpg"


[bird_view_test1]: ./output_images/birdView_test1.jpg "Bird View test1.jpg"
[bird_view_test2]: ./output_images/birdView_test2.jpg "Bird View test2.jpg"
[bird_view_test3]: ./output_images/birdView_test3.jpg "Bird View test3.jpg"
[bird_view_test4]: ./output_images/birdView_test4.jpg "Bird View test4.jpg"
[bird_view_test5]: ./output_images/birdView_test5.jpg "Bird View test5.jpg"
[bird_view_test6]: ./output_images/birdView_test6.jpg "Bird View test6.jpg"
[bird_view_straight_lines1]: ./output_images/birdView_straight_lines1.jpg "Bird View straight_lines1.jpg"
[bird_view_straight_lines2]: ./output_images/birdView_straight_lines2.jpg "Bird View straight_lines2.jpg"

[bird_view_with_parallel_line_straight_lines1]: ./output_images/birdViewWithParallelLine_straight_lines1.jpg "Bird View with parallel line straight_lines1.jpg"
[bird_view_with_parallel_line_straight_lines2]: ./output_images/birdViewWithParallelLine_straight_lines2.jpg "Bird View with parallel line straight_lines2.jpg"

[line_fit_test1]: ./output_images/LineFit_test1.jpg "Line Fit test1.jpg"
[line_fit_test2]: ./output_images/LineFit_test2.jpg "Line Fit test2.jpg"
[line_fit_test3]: ./output_images/LineFit_test3.jpg "Line Fit test3.jpg"
[line_fit_test4]: ./output_images/LineFit_test4.jpg "Line Fit test4.jpg"
[line_fit_test5]: ./output_images/LineFit_test5.jpg "Line Fit test5.jpg"
[line_fit_test6]: ./output_images/LineFit_test6.jpg "Line Fit test6.jpg"
[line_fit_straight_lines1]: ./output_images/LineFit_straight_lines1.jpg "Line Fit straight_lines1.jpg"
[line_fit_straight_lines2]: ./output_images/LineFit_straight_lines2.jpg "Line Fit straight_lines2.jpg"

[histogram_test1]: ./output_images/histogram_test1.jpg "Histogram test1.jpg"
[histogram_test2]: ./output_images/histogram_test2.jpg "Histogram test2.jpg"
[histogram_test3]: ./output_images/histogram_test3.jpg "Histogram test3.jpg"
[histogram_test4]: ./output_images/histogram_test4.jpg "Histogram test4.jpg"
[histogram_test5]: ./output_images/histogram_test5.jpg "Histogram test5.jpg"
[histogram_test6]: ./output_images/histogram_test6.jpg "Histogram test6.jpg"
[histogram_straight_lines1]: ./output_images/histogram_straight_lines1.jpg "Histogram straight_lines1.jpg"
[histogram_straight_lines2]: ./output_images/histogram_straight_lines2.jpg "Histogram straight_lines2.jpg"

[lane_boundary_test1]: ./output_images/LaneBoundary_test1.jpg "Lane Boundary test1.jpg"
[lane_boundary_test2]: ./output_images/LaneBoundary_test2.jpg "Lane Boundary test2.jpg"
[lane_boundary_test3]: ./output_images/LaneBoundary_test3.jpg "Lane Boundary test3.jpg"
[lane_boundary_test4]: ./output_images/LaneBoundary_test4.jpg "Lane Boundary test4.jpg"
[lane_boundary_test5]: ./output_images/LaneBoundary_test5.jpg "Lane Boundary test5.jpg"
[lane_boundary_test6]: ./output_images/LaneBoundary_test6.jpg "Lane Boundary test6.jpg"
[lane_boundary_straight_lines1]: ./output_images/LaneBoundary_straight_lines1.jpg "Lane Boundary straight_lines1.jpg"
[lane_boundary_straight_lines2]: ./output_images/LaneBoundary_straight_lines2.jpg "Lane Boundary straight_lines2.jpg"

## Camera Calibration (computing camera matrix and distortion coefficients.)
1. Convert all color images of chess board in the folder 'camera_cal' to gray scale images.
2. Use `cv2.findChessboardCorners()` to find the 9x6 corner grid`. Only 17 / 20 of images can be used as 3 of them do not all 9x6 corner grid.
3. Use `cv2.cornerSubPix()` to increase the accuracy of the corner positions and store all the 2D points in image plane to `imgpoints[]'.
4. Use `numpy.mgrid()` to create 3D point in real world space to `objpoints[]`.
5. Pass all the points to `cv2.calibrateCamera()` to compute the camera matrix and the distortion coefficients.
6. We can pass the camera matrix and the distortion coefficients to `cv2.undistort()` to undistot the image.

They are implemented in P2.ipynb [2].

The following table show the images at each step and also the undistorted image.

|Original|Gray Image|Find ChessBoard|Undistorted|
|:--:|:--:|:--:|:--:|
|![calibration1]|![gray_calibration1]|![calibration1]|![undistorted_calibration1]|
|![calibration2]|![gray_calibration2]|![drawCorner_calibration2]|![undistorted_calibration2]|
|![calibration3]|![gray_calibration3]|![drawCorner_calibration3]|![undistorted_calibration3]|

## Pipeline (test images)

### Distortion-corrected image of the test images.

The following table show the undistorted images of the road in folder 'test_images' using the same camera matrix and distortion coefficients.

|Original|Undistorted|
|:--:|:--:|
|![test1]|![undistorted_test1]|
|![test3]|![undistorted_test3]|
|![straight_lines1]|![undistorted_straight_lines1]|

### Thresholding to create binary image using color transforms and gradients.

1. Compute the image to HSV Image.
2. Compute the image to HLS Image.
3. From HSV image, select pixels when the corresonding hue is between 40&deg; - 80&deg;, saturation is over 24% and valu is over 16%. It is trying to extract yellow line.
4. From HLS image, select pixels when the corresonding light channel is over 78%. It is trying to extract white line.
5. From HLS image, compute the x gradient using sobel mark on the light channel. Select pixels when the gradient is over 31% or its maximum. It is trying to extract lines for different colors.
6. In the following color binary images, different colors show the lines extracted from different methods. Red represents  the white lines, Green represents the lines from gradient. Blue represents the yellow lines.

They are implemented as function `detectRoad()` in P2.ipynb [5].

|Undistorted|Binary In Color|Binary|
|:--:|:--:|:--:|
|![undistorted_test1]|![color_binary_test1]|![binary_test1]|
|![undistorted_straight_lines1]|![color_binary_straight_lines1]|![binary_straight_lines1]|

### Computing perspective transformation to create bird view
1. Select straight_lines1.jpg and straight_line2.jpg from the folder 'test_images'.
2. Use the above thresholding to extract the left line and the right line from the road.
3. Apply a trangle mask to the binary images so that it only contains the pixels for the lines.
4. Use `numpy.polyfit()` with order 1 to get the linear left line and the right linear right line.
5. Compute the x coordinates when both lines cut at y = 719 (Image Bottom) and y = 450.


|The Linear Line in striaight_line1.jpg|The Linear Line in striaight_line2.jpg| 
|:-------------------:|:-------------:| 
|![linear_line_fit_straight_lines1]|![linear_line_fit_straight_lines2]| 

6. Compute the distances in x axis between left and right line at y = 719 (Image Bottom) and y = 450.
7. Compute the average of the distances from both images. Get the average distances at y = 719 (Image Bottom) and y = 450.
8. Recompute the left line and right line with the average distances at y = 719 (lImage Bottom) and y = 450, but placing the lines at the center in horizontal direction.
9. We want project the left line to (320, 0) and (320, 720) and project the right line to (960, 720) and (960, 0). We would compute the perspective transformation matrix from the following source and destination points.

| Source              | Destination   | 
|:-------------------:|:-------------:| 
| 579.55780029, 460   | 320, 0        | 
| 700.44219971 , 460  | 320, 720      |
| 195.11116028, 720   | 960, 720      |
| 1084.88879395, 720  | 960, 0        |

They are implemented in P2.ipynb [6].

The resulted images show that both images of straight lines are parallel.

|Original|Undistorted|Bird View|
|:--:|:--:|:--:|
|![straight_lines1]|![undistorted_straight_lines1]|![bird_view_with_parallel_line_straight_lines1]|
|![straight_lines2]|![undistorted_straight_lines2]|![bird_view_with_parallel_line_straight_lines2]|
|![test1]|![undistorted_test1]|![bird_view_test1]|

### Identify lane-line pixels and fit their positions with a 2nd order polynomial

After the binary image in bird view is created, the lane line would be fitted to a 2nd order curve in the following way:
1. Create the histogram from the binary image. There should be two peaks in the histogram. The leftmost one represents the left line. The rightmost one represents the right line.
2. The x-coordinates of the 2 peaks can act as a start point from the bottom. Only the activated pixels within a window `newWinWidth x (Image Height / slideWinSize` would be consider as good pixel if the number of activated pixels reach a threshold `minPix`.
3. If the number of activated pixels reach a threshold `minPix`, find the mean positions of activated poixel within the window. The mean positions become the center of next window in upper positon. If the number of activated pixels do not reach a threshold `minPix`, the the center of next window in upper position would kept unchanged.
4. Only the activated pixels within a window `newWinWidth x (Image Height / slideWinSize` would be consider as good pixel if the number of activated pixels reach a threshold `minPix`.
5. Repeat Step 3 - Step 4 for `slideWinSize` until the windows reach the top of the image. If the number of activate pixels does not reach a threshold `minPix' for 2 times consecutively. The sliding window search would stop as it may come across outliner.
6. The good pixels would be fit to a 2nd order equation using `numpy.polyfit()`.
7. Then two 2nd order curve can be found. The left one represents the left one. The right one represents the right one.

They are implemented as the method `processNewImage` of class `LaneLines` in P2.ipynb [9].

The following table shows the computed histogram and the line fit progress for several test images.

|Lane Boundary|Bird View|Histogram|Line Fit|
|:--:|:--:|:--:|:--:|
|![straight_lines1]|![bird_view_straight_lines1]|![histogram_straight_lines1]|![line_fit_straight_lines1]|
|![test2]|![bird_view_test2]|![histogram_test2]|![line_fit_test2]|
|![test3]|![bird_view_test3]|![histogram_test3]|![line_fit_test3]|

### Calculation of the radius of curvature of the lane and the position of the vehicle with respect to center
The 2nd order equation f(y) = Ay^2 + By + C have found in the last sections. However, the unit is in the unit of pixels. We need to compute the ratio of the pixel and the meter in the real world.

According to the U.S regulations, the lane width is 3.7 meters. From the calculation of the perspective transformation, we project the road width to 640 pixels. Therefore, the meter per pixel in x direction is 3.7 / 640.

According to the U.S regulations, the dash line is 3 meters long each. From the bird view image showing straight line, we observe that the length is about 107 pixels. Therefore, the meter per pixel in y direction is 3 / 107.

Transform all the points in good pixel using the ratio of the pixel and the meter and then fit a new curve f(y) = Ay^2 + By + C.

The radius of curvature would be (1 + (2Ay + B) ^ 2) ^ (3 / 2) / |2A|. 

To compute the position of the vehicle with respect to center, subtract x-coordinates the center of the image from the average of f(y) = Ay^2 + By + C at the bottom of the image of the left line and the right line. The final offset would be in meter if all the calculation is in meter.

The pixel to meter ratio is impleted as the class `BirdViewSIConvertor` in P2.ipynb [8].
The radius of curvature is implemented as the method `getCurve` of class `LaneLines` in P2.ipynb [9].

|Result of test2.jpg|
|:--:|
|![undistorted_test2]|
|Left Curvature: 280 m|
|Right Curvature: 398 m|
|The vehicle is 3.802 m left of the center.|

### Lane area Projection back to the undistorted image.

From the section of Computing perspective transformation to create bird view, we compute the perspective transformation using the following source and destination points.

| Source              | Destination   | 
|:-------------------:|:-------------:| 
| 579.55780029, 460   | 320, 0        | 
| 700.44219971, 460   | 320, 720      |
| 195.11116028, 720   | 960, 720      |
| 1084.88879395, 720  | 960, 0        |

When we transfrom the Lane area back to the undistorted image, we can use the perspective transformation using the following source and destination points.

| Source        | Destination         | 
|:-------------:|:-------------------:| 
| 320, 0        | 579.55780029, 460   | 
| 320, 720      | 700.44219971, 460   |
| 960, 720      | 195.11116028, 720   |
| 960, 0        | 1084.67077637, 720  |

They are implemented in P2.ipynb [6] and used in [11] and [12]

The following shows the example of lane area projection.

||Lane|Boundary||
|:--:|:--:|:--:|:--:|
|![lane_boundary_test1]|![lane_boundary_test2]|![lane_boundary_test3]|![lane_boundary_test4]|
|![lane_boundary_test5]|![lane_boundary_test6]|![lane_boundary_straight_lines1]|![lane_boundary_straight_lines2]|

## Pipeline (video)
### Pipeline of the line finding from video

The pipeline of the line finding from video is described below.
1. When the current state does not contains any historical data, it make use of the pipeline of the test image which is described below.
2. When there is result from the previous frame, the sliding window search would be different the sliding window would following the line fit from the last frame with smaller window width `existWinWidth`.
3. When there are points (good pixels) from the previous frames, the points from the previous `pointKeptForLastFrameSize` frames would be included to compute the new fitted line. It make the pipeline more robust when the current frame does not contains enough good pixels to compute the new fit line. It can also make the pipeline more robuts to outliers.
4. The computed new fit line is not the resultant line, but will be added to the history of the line fit. The resultant line would be computed by average the the coefficients of the last `coefAvgSize` frames. It makes the pipeline even more robust.
5. If the resultane lines are not reasonable, all the historical data would be deleted and start from step 1 again. For example, the widths of the road at the bottom or at the top are abnormal. The left line crosses the right line in the image. All of these lines would be rejected and start from step 1 in the next frame again.

They are implemented as the method `processNewImage` of class `LaneLines` in P2.ipynb [9].

It work well for the project_video.mp4.
It also work well for challenge_video.mp4 except there is not very good when there is shadow under the bridge.
However, the pipeline does not work in harder_challenge_video.mp4

| project_video.mp4 | challenge_video.mp4 | harder_challenge_video.mp4 |
|:-------------:|:----------------:|:----------------:| 
|[![output_project_video]](./output_video/project_video.mp4)|[![output_challenge_video]](./output_video/challenge_video.mp4)|[![output_harder_challenge_video]](./output_video/harder_challenge_video.mp4) |

The following video are also created for debug. 
| project_video.mp4 | challenge_video.mp4 | harder_challenge_video.mp4 |
|:-------------:|:----------------:|:----------------:| 
|[![output_project_video_debug]](./output_video/project_video_debug.mp4)|[![output_challenge_video_debug]](./output_video/challenge_video_debug.mp4) | [![output_harder_challenge_video_debug]](./output_video/harder_challenge_video_debug.mp4) |

## Discussion

### Problems and Possible Improvement
1. It is difficult to set the threshold in threshold binary image. One set of parameters may work better for darker background while it may work worse for brighter background. One set of parameters may work better for brighter background hilw it may work worse for dark background. It is better to detect the background in the road area and apply different parameters automatically. 
2. The current sliding window search cannot handle sharp turn which happen frequently in harder_challenge_video.mp4 because the the sliding window only search in vertical direction. We should design a scheme so that it can search in all directions.
3. The current pipeline for video contains two parameters `pointKeptForLastFrameSize` and `coefAvgSize`. `pointKeptForLastFrameSize` specifies the maximum of the number of recent frames to compute he new fitting line. `coefAvgSize` specifies the maximum of the number of recent fitting lines which are used to compute the output fitting line. Larger number of them can handle outlier, lighting, or unexpected object more robustly, but also make it less responsive.
