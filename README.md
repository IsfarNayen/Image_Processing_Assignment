# Image Processing Guideline
This repository contains an image processing notebook designed for Kaggle. The notebook demonstrates how to load, process, and save images using OpenCV and PIL (Pillow) in a Kaggle environment.

<h2>Features </h2>

- Load and display images in Kaggle
- Convert images to black and white (grayscale)
- Save processed images in the Kaggle working directory

<h2>Prerequisites:</h2>

- Matplotlib
    - image - For Loading image
    - pyplot - For visualizing image and dimensions of the image
- Pillow - For resizing
- OpenCV - For converting RGB image to Greyscale image

<h2>Steps</h2>

- **Install Dependencies**

    Kaggle notebooks come pre-installed with necessary libraries, but if running locally, install them using:
    ```python
    pip install opencv-python pillow matplotlib
    ```
- **Clone the Repository**
    ```python
    git clone https://github.com/IsfarNayen/image-processing-kaggle.git
    cd image-processing-kaggle
    ```

- **Run the Notebook**
    - Upload the notebook to Kaggle Notebooks and run it.
    - Alternatively, run locally using Jupyter:
    ```python
    jupyter notebook image-processing-kaggle.ipynb
    ```

<h2>Some Important parts in the code:</h2>

- **Load Image by matplotlib.image:**
```python
img = mpimg.imread("/kaggle/working/understanding-your-dog-s-body-language.jpg")
```
- **Display Image by matplotlib.pyplot:**
```python
matplotlib.pyplot.imshow(img)
```

<br>
    <img src="assets/coloured.png" alt="B&W_img" width=auto>
<br>

- **Resize by Pillow:**
```python
from PIL import Image
dog_image = Image.open("/kaggle/working/understanding-your-dog-s-body-language.jpg")
resized_image = dog_image.resize((200 , 200))
```
<br>
    <img src="assets/coloured_shrinked.png" alt="B&W_img" width=auto>
<br>

- **Saving Image by Pillow**
```python
resized_image.save('New_resized_image_to_200*200*3.jpg')
```

- **Checking Dimensions and Plotting:**
Saving in the previous part is done for plotting by matplotlib.pyplot.
```python
img = mpimg.imread('/kaggle/working/New_resized_image_to_200*200*3.jpg')
img.shape
matplotlib.pyplot.imshow(img)
```

- **Converting RGB to Grayscale by OpenCV or cv2 library**
```python
import cv2
img = cv2.imread(pic)
B&W_img = cv2.cvtColor(img, cv2.COLOR_RGB2GRAY)
```

- **Grayscale image shown by OpneCV**

B&W image was supposed to load by cv2.imshow('B&W_img'), but in google colab or kaggle, this function don't work. So alternative 2 ways are shown below:

- Way 1(More efficient and found in internet):
```python
from google.colab.patches import cv2_imshow
cv2_imshow(bw_img) #showing image by cv2
```

<br>
    <img src="assets/B&W_shrinked.png" alt="B&W_img" width=auto>
<br>

- Way 2(My created way from Pillow by saving):
```python
img = Image.fromarray(bw_img)
img.save('dog_BlackandWhite.jpg')
img = mpimg.imread('/kaggle/working/dog_BlackandWhite.jpg')
plot = plt.imshow(img)
```
<br>
    <img src="assets/B&W_shrinked(My_way).png" alt="B&W_img" width=auto>
<br>

<h2>My Contributions:</h2>

I have implemented the image processing workflow in Kaggle using an alternative approach. Specifically:

- Loading Image from Pillow: Instead of OpenCV, I used Pillow to handle image operations effectively.
- Alternative Processing Flow: The grayscale conversion and saving operations were performed using Pillow instead of OpenCV, providing another method for image manipulation.
- Code Optimization: Ensured efficient execution by structuring the code in a way that enhances clarity and performance.

<h2>Author</h2>

- Github: [IsfarNayen](https://github.com/IsfarNayen)