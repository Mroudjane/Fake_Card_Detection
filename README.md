# Card Tampering Detection

The purpose of this project is to detect whether a provided card is original or not. This projectcan help different organization detecting fake employees or customers ID Cards.

## Calculate structural similarity of original card (reference card) and user uploaded card.
create a folder to save the save the images

## Loading original and user provided images

#Resize images and convert format
Resize both images to the same size. Then, convert the tampered image to the original image format.
to change tampered image format we just have to save the image with the right format. In the code section above we changed the original image format from JPEG to PNG.

## Display images

![alt text](img/Unknown.png)
![alt text](img/Unknown.png)

## Comparing the two cards
### Reading the images using OpenCV.
During this step we will use a gray scale to simplify the comparison.
A coloured image is far more complex to understand by a machine because it has 3 channel (RGB) while the gray scale has only one channel.

The SSIM help determine the coordinates of the differences between the images. The lower SSIM score is the lower is the similarity.

Threshold function in computer vision applies an adaptive threshold to the stored  image. It transforms the grayscale image into a binary image using the *cv2* function. 

We can only find and reteive contours on binary images. The contours is used for shape analysis and recognition. The *grab_contour* fucntion alows to "grab" the appropriate value of the contours.

Bounding rectangle alows to find the ratio of width and height of bounding rectangle of the object.After that we can draw bounding box where images are different.

![alt text](img/Unknown.png)
![alt text](img/Unknown.png)
Contour didn't help detect the difference between the two images.

## Display Difference and Threshold in black and white

![alt text](img/Unknown.png)
![alt text](img/Unknown.png)

We can see here that there IS a difference between the two images. If there was no difference thare wouln't be any black portion on the image generated.
We can see from this image that the threshold between the two images is very high as the there is a very big white areas in the generated image.

##summary

The Structural similarity of images helped in finding the difference between the shapes of original and user uploaded images.
Computing the threshold and contour alowed us to do shape analysis and shape recognition.

As SSIM is around 31% we can say with very good confidence that the user privided a fake ID.

Visualising the differences and similarities between imafes confirmed the theoritical findings.

