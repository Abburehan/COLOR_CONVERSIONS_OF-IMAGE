# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By: ABBU REHAN
### Register Number: 21223240165


## Output:

### i) Read and display the image
```Python
    import cv2
    image=cv2.imread('Rehan.jpg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('Rehan',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
   
#### OUTPUT:
![rehan1 1](https://github.com/Abburehan/COLOR_CONVERSIONS_OF-IMAGE/assets/138849336/fbf41187-12a1-4479-920e-eee3251f4151)

<br>
<br>

### ii)Write the image
```Python
    import cv2
    image=cv2.imread('Rehan.jpg',0)
    cv2.imwrite('rehan1.1.jpg',image)
```
#### OUTPUT:
![rehan1 2](https://github.com/Abburehan/COLOR_CONVERSIONS_OF-IMAGE/assets/138849336/ba14496c-5ba0-410f-bbb4-aed0f684522a)

<br>
<br>


### iii)Shape of the Image
```Python
    import cv2
    image=cv2.imread('Rehan.jpg',1)
    print(image.shape)
```

#### OUTPUT:
![rehan1 3](https://github.com/Abburehan/COLOR_CONVERSIONS_OF-IMAGE/assets/138849336/10f59803-a279-4e2f-ab35-22676ea30517)

<br>
<br>


### iv)Access rows and columns
```Python
      import random
      import cv2
      image=cv2.imread('Rehan.jpg',1)
      image=cv2.resize(image,(400,400))
      for i in range (150,200):
        for j in range(image.shape[1]):
           image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
       cv2.imshow('part image',image)
       cv2.waitKey(0)
       cv2.destroyAllWindows()
```
 
#### OUTPUT:
![rehan1 4](https://github.com/Abburehan/COLOR_CONVERSIONS_OF-IMAGE/assets/138849336/8e82835a-911a-4531-8606-00161c8a56bf)

<br>
<br>

### v)Cut and paste portion of image
```Python
     import cv2
     image=cv2.imread('Rehan.jpg',1)
     image=cv2.resize(image,(400,400))
     tag =image[150:200,110:160]
     image[110:160,150:200] = tag
     cv2.imshow('partimage1',image)
     cv2.waitKey(0)
     cv2.destroyAllWindows()
```
 
#### OUTPUT:
![rehan1 5](https://github.com/Abburehan/COLOR_CONVERSIONS_OF-IMAGE/assets/138849336/c5a906f6-df57-4a0a-b45c-a6816b8b8c65)

<br>
<br>

### vi) BGR and RGB to HSV and GRAY
```Python
    import cv2
    img = cv2.imread('Rehan.jpg',1)
    img = cv2.resize(img,(300,200))
    cv2.imshow('Original Image',img)

    hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
    cv2.imshow('BGR2HSV',hsv1)

    hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
    cv2.imshow('RGB2HSV',hsv2)

    gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
    cv2.imshow('BGR2GRAY',gray1)

    gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
    cv2.imshow('RGB2GRAY',gray2)

    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
#### OUTPUT:
![rehan1 6](https://github.com/Abburehan/COLOR_CONVERSIONS_OF-IMAGE/assets/138849336/7132b5f9-d85e-4811-b39f-4024e9e90e8f)

<br>
<br>

### vii) HSV to RGB and BGR
```Python
import cv2
img = cv2.imread('Rehan.jpg')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### OUTPUT:
![rehan1 7](https://github.com/Abburehan/COLOR_CONVERSIONS_OF-IMAGE/assets/138849336/5d91dc77-b7d3-4858-9699-1bcd406fdc92)

<br>
<br>

### viii) RGB and BGR to YCrCb
```Python
import cv2
img = cv2.imread('Rehan.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### OUTPUT:
![rehan1 8](https://github.com/Abburehan/COLOR_CONVERSIONS_OF-IMAGE/assets/138849336/08dbf424-c95d-40aa-b1d1-0de9ee85b6e8)
<br>
<br>

### ix) Split and merge RGB Image
```Python
import cv2
img = cv2.imread('Rehan.jpg',1)
img = cv2.resize(img,(300,200))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### OUTPUT:
![rehan1 9](https://github.com/Abburehan/COLOR_CONVERSIONS_OF-IMAGE/assets/138849336/c3ea7e33-add0-4528-a0b2-c3305288bc7e)

<br>
<br>

### x) Split and merge HSV Image
```Python
import cv2
img = cv2.imread("Rehan.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### OUTPUT:
![rehan1 10](https://github.com/Abburehan/COLOR_CONVERSIONS_OF-IMAGE/assets/138849336/26108c46-d490-420c-8c64-519e6e78d214)

<br>
<br>

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
