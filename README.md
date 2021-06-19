# Add Lane Assistance to any car using your phone!

## Inspiration:
- My mustang is stupid, I want to have some sort of smartness in it via my phone.

## Notes as I research on this:

### Canny
- Canny edge detection : Edge detection algorithm, takes frame and extracts edges.
- For canny edge detection use grayscale so we can reduce noise from RGB channel since canny works by detecting where contrast in pixel occurs.
- Sometimes blur the image/image background to further reduce noise, before performing canny edge detection.
- Canny takes 2 thresholds value and detects min contrast between those 2 thresholds as edge.

### ROI
- Region of interest, ability to remove part of image that we dont care about. 
- Take height and width of image, lay on the image a mask of the image, with our ROI is of its own white color. Perform bitwise operation between mask and image, so wherever it is white it willl pass where black it wont!
