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
### Developed By: vasanth s
### Register Number: 212222110052


## Output:

### i) Read and display the image

```
import cv2
img=cv2.imread('dpi .jpg',1)
cv2.imshow('colorimage',img)
cv2.waitKey(0)
```
### output:![1](https://github.com/vasanth0908/COLOR_CONVERSIONS_OF-IMAGE/assets/122000018/cb517ed4-6344-402e-952c-1909be0de454)

### ii)Write the image

```
import cv2
g_image=cv2.imread('dpi .jpg',0)
cv2.imwrite('dpi .jpg',g_image)
```
### output:![2](https://github.com/vasanth0908/COLOR_CONVERSIONS_OF-IMAGE/assets/122000018/a6114e0e-0601-4c48-bdf0-20ac9942cce6)

### iii)Shape of the Image

```
import cv2
image=cv2.imread('dpi .jpg',1)
print(image.shape)
```
### output:![3](https://github.com/vasanth0908/COLOR_CONVERSIONS_OF-IMAGE/assets/122000018/997438c4-7469-4ece-8ace-db5d051e0397)


### iv)Access rows and columns
```
import random
import cv2
image=cv2.imread('dpi .jpg',1)
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
### output:![4](https://github.com/vasanth0908/COLOR_CONVERSIONS_OF-IMAGE/assets/122000018/cf94423b-a73e-4f83-ab4c-febae502c1da)


### v)Cut and paste portion of image
```
import cv2
image=cv2.imread('dpi .jpg',1)
image=cv2.resize(image,(400,400))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('partimage1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### output:![5](https://github.com/vasanth0908/COLOR_CONVERSIONS_OF-IMAGE/assets/122000018/baaa3650-5478-490a-8f40-e3a0e21d5b09)


### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('dpi .jpg',1)
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

### output:![6](https://github.com/vasanth0908/COLOR_CONVERSIONS_OF-IMAGE/assets/122000018/9e550189-f9f3-417a-9c30-68ef88f35f4f)


### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('dpi .jpg')
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

### output:![7](https://github.com/vasanth0908/COLOR_CONVERSIONS_OF-IMAGE/assets/122000018/77dcdb44-52b3-4ffb-b089-c6ff05b0a0f8)


### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('dpi .jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

### output:![8](https://github.com/vasanth0908/COLOR_CONVERSIONS_OF-IMAGE/assets/122000018/b4416167-ddb3-4236-8594-1aace97fc7f2)


### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('dpi .jpg',1)
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

### output:![9](https://github.com/vasanth0908/COLOR_CONVERSIONS_OF-IMAGE/assets/122000018/e07e6658-cca5-451f-81d5-9c8e1dc86596)


### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("dpi .jpg",1)
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

### output:![10](https://github.com/vasanth0908/COLOR_CONVERSIONS_OF-IMAGE/assets/122000018/9f9dad18-3e0c-4975-9cf4-92f3214c57ee)





## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







