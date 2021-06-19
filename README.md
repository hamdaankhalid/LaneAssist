# Add Lane Assistance to any car using your phone!

## Inspiration:
- New cars have fancy lane assists, most cars on the road don't, its a cool safety feature, that everyone can have. Im going to make it accessible for everyone.

## Notes as I research on this:

##Basics:

### ROI
- Region of interest, ability to remove part of image that we dont care about. 
- Take height and width of image, lay on the image a mask of the image, with our ROI is of its own white color. Perform bitwise operation between mask and image, so wherever it is white it willl pass where black it wont!
- Removes obvious noise

### Canny
- Canny edge detection : Edge detection algorithm, takes frame and extracts edges.
- For canny edge detection use grayscale so we can reduce noise from RGB channel since canny works by detecting where contrast in pixel occurs.
- Sometimes blur the image/image background to further reduce noise, before performing canny edge detection.
- Canny takes 2 thresholds value and detects min contrast between those 2 thresholds as edge.
- Run ROI before Canny

### Hough transform
- Even after ROI, Canny picks up too many lines, here comes Hough trnasformation.
- It basically finds the pattern of pixel, can do circle, shape, line, etc.
- cv2.HoughLinesP impplements probabilistic Hough transform algorithm for line detection. Finds line segments in a binary image. Returns coordinates of multiple lines detected.
- To draw lines on image we can use opencv to draw lines on the image.

## Basic-2 (perception and averaging lanes):

### Average slope intercept
- to erase erraneous lanes, we can merge/estimate lanes on left and lanes on right into 1 each, that way we are only focussing on a "single lane".
- Go through mulitple lines , based on the angle of slope (-ve slope vs +ve slope), find slope and intercept of line and put in left or right category, then take left fit and right fit lines, and calc average of left's average, and right's average -> Now we have left and right lanes slope and intercept respectively. 
- Convert slope and intercept to x,y coordinates.

## Advanced Lane detection ( Curvature - Distortion )

### Calibration & Perception
- Callibration is used to minimize/mitigate distortion from cameras.
- Each phone or lens or whatever I use to take video of the road, will have to be first used to collect 20 images of an chessboard, so that I can use for calibration and undistort images.
- Need a top down view to get rid of convergence of lane due to monocular vision.

## Thoughts
 Reproduce this on a phone, and upon bad lane keeping assist driver, maybe vibrate on the side where its going too far.

