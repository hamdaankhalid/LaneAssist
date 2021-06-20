Although not sure about how to put this code on a phone.I have a rough idea of what I want to do and here I will be writing it down

* Caliberate camera for undistortion

Start video stream, for each frame:
- Take frame and undistort 
- take undistorted frame and perspective transform to birdseye
- put bridseye and in hls and hlv
- isolate left and right
- Combine isolated hsl with original frame
- Convert combined frame to grayscaled
- Gaussian blur to smoothen edges
- canny edge detection
- Hough transform for lines while accounting for curvature?
- Re-distort and overlay results on original frame.

WOAH I FOUND THIS https://github.com/Dt-Pham/Advanced-Lane-Lines/tree/b04b492814485ed18fd90bd3b77243b03c486300
