# Neural-Networks-Deep-Learning-Coursera
This repository contains my solutions for labs and programming assignments for the Coursera courses [Neural Networks and Deep Learning](https://www.googleadservices.com/pagead/aclk?sa=L&ai=DChcSEwibl7XGvuDyAhWemmYCHb1qDe0YABAAGgJzbQ&ae=2&ohost=www.google.com&cid=CAESQOD2tcu6_aOG19BQOlpccn0Cmr8YkV7DnKBmM6PU29a9xo8OdpHeIUD06IY6egfaZXmDM2hl4kJUH0ehxldr8bE&sig=AOD64_0h4_OF298BvRutFHaeiXl_3kAXPA&q&adurl&ved=2ahUKEwjOzazGvuDyAhWCfH0KHaDkAB4Q0Qx6BAgEEAE). 

- [Week 2: Python Basics with NumPy](https://github.com/Yuxinn-J/Neural-Networks-Deep-Learning-Coursera/blob/main/Python_Basics_With_Numpy.ipynb)
- [Week 2: Logistic Regression with a Neural Network mindset](https://github.com/Yuxinn-J/Neural-Networks-Deep-Learning-Coursera/blob/main/Logistic_Regression_with_a_Neural_Network_mindset.ipynb)
- [Week 3: Plannar data classification with a hidden layer](https://github.com/Yuxinn-J/Neural-Networks-Deep-Learning-Coursera/blob/main/Planar_data_classification_with_onehidden_layer.ipynb)
- [Week 4: Building your deep neural network: Step by Step](https://github.com/Yuxinn-J/Neural-Networks-Deep-Learning-Coursera/blob/main/Building_your_Deep_Neural_Network_Step_by_Step.ipynb)
- [Week 4: Deep Neural Network Application](https://github.com/Yuxinn-J/Neural-Networks-Deep-Learning-Coursera/blob/main/Deep%20Neural%20Network%20-%20Application.ipynb)

----
issues solved: `imread`, `imsave`, `imresize` from `scipy.misc` are deprecated

- Use `imageio.imread` instead
- Use `imageio.imsave` instead
- Use `np.array(Image.fromarray(image).resize((IMAGE_W,IMAGE_H)))` instead

Can try following codes.

```python
import imageio
from PIL import Image

# Read an JPEG image into a numpy array
img = imageio.imread('assets/cat.jpg')

plt.imshow(img)
plt.show()

print(img.dtype, img.shape)  # Prints "uint8 (400, 248, 3)"

# We can tint the image by scaling each of the color channels
# by a different scalar constant. The image has shape (400, 248, 3);
# we multiply it by the array [1, 0.95, 0.9] of shape (3,);
# numpy broadcasting means that this leaves the red channel unchanged,
# and multiplies the green and blue channels by 0.95 and 0.9
# respectively.
img_tinted = img * [1, 0.95, 0.9]

# Resize the tinted image to be 300 by 300 pixels.
img_tinted = np.array(Image.fromarray(np.uint8(img_tinted)).resize((300, 300)))

# Write the tinted image back to disk
imsave('assets/cat_tinted.jpg', img_tinted)
plt.imshow(img_tinted)
plt.show()
```
