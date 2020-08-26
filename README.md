<img src="https://github.com/Godson-Thomas/Colour_Detection-Python/blob/master/Files/detected.gif" width="500"  /> <br><br>
# Google  T-Rex Offline game
All of us will be familiar with the offline DINO game which the chrome provides for the users to play when there is no internet connection.We will be using the given python codes along with the necessary modules for playing ( without any human actions ) google's T-Rex game.


## Libraries Used :
- PyAutoGUI
- OpenCV
- Numpy
- mss
- PIL
<br><br>
# Steps
## Installation


1. We will be using Jupyter Notebook for writing the code.Make sure you have Jupyter Notebook installed.<br><br>
2. Lauch your Jupyter Notebook<br><br>
3. Now we have to install the libraries.Type the code one by one in the cell of Jupyter Notebook and run it.

```
pip install opencv-python
```
```
pip install pyautogui
```
```
pip install numpy
```

```
pip install mss
```
```
pip install Pillow
```

<br><br>
* ## Code 
  - Full code.   [click here]()<br><br>
4. Open your chrome (note : Without internet connectivity)<br>

5. Import the necessary libraries. 
```
import numpy as np
import cv2
from mss import mss
from PIL import Image
import pyautogui
```
<br>

6. Code for taking screenshot of the required area & for taking actions.
```
mon = {"top": 230, "left": 140, "width": 90, "height": 66}#area of interest on the screen

k = 1
while 1:
    img = mss().grab(mon)  # capturing the screen shot
    img = np.array(img)  # conveting the image to numpy arrays

    cv2.imshow("Screen", img)  # just displaying the image
    p_cac = img[28, :, 0]  # storing the blue colour's value of all pixels from 28th pixel
    p_bird = img[1, :, 0]  # storing the blue colour's value of all pixels from 1st pixel

    # print (p_cac)
    # print (p_bird)
    p_cac_sum = np.sum(p_cac)  # sum of all the blue values at 28th position
    p_bird_sum = np.sum(p_bird)
    print(p_cac_sum)


    if p_cac_sum < 21970:

        pyautogui.press('up')

    if p_bird_sum < 21970:

        pyautogui.keyDown('up')
    if cv2.waitKey(25) & 0xFF == ord('q'):

        cv2.destroyAllWindows()
        break
```
<br>

