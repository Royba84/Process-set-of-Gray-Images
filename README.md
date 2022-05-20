The task:

![image](https://user-images.githubusercontent.com/105777016/169494100-7f08b2f2-b512-40e8-b4d1-9edf5f7cbf2c.png)

Introduction & goals:

On this assignment our main goal is to find a way to improve bad looking photograph and make it look prettier, using variety of functions and methods LUT,Min&Max algorithm etc..
First, we found a photograph on the internet and changed its properties
(more on that later).
After that, we proceeded to the coding stage where we implemented variety of functions such as:
Create_LUT
ApplyLUTonGrayImage
Spoil_good_looking_Image
CreateMinMaxLUT
Min_Max_Algorithm

 Original photo:
 
 ![image](https://user-images.githubusercontent.com/105777016/169495080-60d67fc3-34b0-49ef-b5a3-58b9a7261e37.png)
 Gray photo:
 
 ![image](https://user-images.githubusercontent.com/105777016/169495124-4b328abe-faec-465f-a277-d5c7755a2854.png)

As we mentioned on the introduction, we found on the internet a good looking photograph consisting variety of fruits and vegetables. We resized the image to 320x240 dimensions and made sure it’s from CGA true-color (24 bpp) bmp file type.
 After all that, we converted it to a gray image.

![image](https://user-images.githubusercontent.com/105777016/169495297-12d65a77-f917-481b-b772-5432d0998d28.png)

![image](https://user-images.githubusercontent.com/105777016/169495314-856e2b4a-79bc-4e23-9fbe-fa903f89b74d.png)

On the upper photo  we can see our gray image. 
On this side we can examine (using BmpViewer) that the photo colors are “higher” and more scattered 
(according to the profilers graphs). 
On the photo below we can see our spoiled photo which unlike the gray photo it is more centered (according to the profilers graphs).
On the following slides we will try to take this spoiled photo and make it look better.

Spoiled photo:

![image](https://user-images.githubusercontent.com/105777016/169495765-881c55e2-f344-456d-ae5b-42611730c09d.png)

Fixed photo:

![image](https://user-images.githubusercontent.com/105777016/169495807-e7a89513-eb23-4231-b73e-2ecea8bf7bf6.png)

From observing the result we can see that the fixed photo is much brighter than the original one. However, in the field of image processing, eye sight might deceive us and we must use artificial tools (such as BMPViewer etc..) to examine the quality of the fix in a way that is not arguable.
The red marker shows the point we chose to test in both photos, the values to compare here are the R,G,B sections and the profilers graphs.

Min-Max algorithm fix:
gray image: 

![image](https://user-images.githubusercontent.com/105777016/169495935-ca953829-667a-482b-a2e4-6fedb28fc83e.png)

fixed image:

![image](https://user-images.githubusercontent.com/105777016/169495995-ebb52629-e0b5-4416-bfa3-7979dd79ef78.png)

Here we can see the Gray image against the fixed photo, we can see that the values are about the same (92 vs 89) and also this inaccuracy might occur because of the fact that the cursor is not 100% exactly at the same point.

Another try on a better quality photo:

original:![image](https://user-images.githubusercontent.com/105777016/169496218-d2fa254b-3526-4be5-b75a-807b254b96a9.png)

gray:![image](https://user-images.githubusercontent.com/105777016/169496240-72df5644-1dad-4bcb-9297-dd5fc5d9ab9a.png)

![image](https://user-images.githubusercontent.com/105777016/169496362-172dd39f-6552-4048-9d23-61afe08dd311.png)
this time with more detailed and less “white” part on the image 

![image](https://user-images.githubusercontent.com/105777016/169496497-8f554635-7ace-4175-83cd-2a763c69f3c3.png)


### Explanation of the functions that were in use:

functions that were used in order to spoil our original photo. In short:
Create_LUT- Takes care of the values of each pixel and updates the min/max Pixel values.

ApplyLUTonGrayImage- Here we simply implement what we have done on Create_LUT on our photo ((img[row][col]) in the code).

Finally, Spoil_good_looking_Image -  uses the 2 functions above with certain constants (B,C,F,G)
And spoil our image according to them.


On this assignment we were dealing 
with contrast & brightness properties 
of a photo.In order to get an optimal 
improvement of a photo we have done 
the following calculations and implemented them in our code:

![image](https://user-images.githubusercontent.com/105777016/169496745-486ac58e-dfbb-459e-b3a3-49f60dca2964.png)

The mechanism of this algorithm works like this in a nutshell:
First we made an assumption that some higher values than PIXEL_MinVal and some have lower values than PIXEL_MaxVal.
Then we find Min&Max Pixel values and after that calculate the 
coefficients c,b (mentioned above). 
Eventually we calculated the LUT and applied it for each pixel of the image.


