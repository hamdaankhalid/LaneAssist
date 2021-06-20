Although not sure about how to put this code on a phone.I have a rough idea of what I want to do and here I will be writing it down

Instead of deep learning based lane detection approach use oldschool that I researched and use this awesome repo with everything from udacity done, and under MIT license -> https://github.com/hamdaankhalid/CarND-Advanced-Lane-Lines

- User opens app
- If camera has been calibrated -> Take to dashcam scene -> else -> Collect images for calibration
- Or maybe if it's a popular phone have it pre calibrated for distortion matrix and coefficient (game changer)
- Connect phone to vibration devices on left and right hands or on steering wheel.
- Place phone in phoneholder with dashcam view.
- Track mobile sensor to detect when above 50 mph and assume user is on highway and needs lane assist
- With lane assist on begin lane tracking and monitor distance from lane, if changed without warning send signal for motors to vibrate on whichever side the  driver is going to warn them.
- The lane change warning can be a voice command like "Lane" or maybe a sensor for the indicator ?

Potential problems:
- Fps relative to speed, at what point am I processing too slow for the speed? Warn user at that speed.
- How to put this bunch of python code into a phone!
