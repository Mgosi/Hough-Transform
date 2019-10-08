# Hough-Transform

In this project, we perform Hough Transform which gives the edge lines of an image. Here are the steps followed in carrying this out.
1.  We first perform edge detection using Sobel Operator. 
2.  We then draw the Accumulator matrix which consists of (theta vs rho) matrix. Each line in the input image represents a single point in the (theta vs rho) space. Hence to find the maximum number of lines, we plot or express all the points of the image in the (theta vs rho) space.
3.  We convert the point and known theta value into rho as follows:
```
Rho = (xcos(theta) + ysin(theta))
```

4.  The accumulator matrix will generate a sine wave and highlight the most frequent point in the space. 
5.  Then we take the maximum frequency or votes for the points in the (theta vs rho) space and convert that into lines in the original image.
Figure
<p align="center">
  <br><br>
  <img src="Red Edge Lines.png" align = "center" width = 450>
  <figcaption><p align="center">Red Edge Lines</p></figcaption>
</p>

<p align="center">
  <br><br>
  <img src="Red Edge Lines.png" align = "center" width = 450>
  <figcaption><p align="center">Blue Edge Lines</p></figcaption>
</p>

<p align="center">
  <br><br>
  <img src="Edges-Accumulator.jpg" align = "center" width = 600>
  <figcaption><p align="center">Accumulator</p></figcaption>
</p>

6.  By doing so we get the vertical lines between (-5,5) theta values, while the diagonals are between (50,55) theta values. We find a list of all frequent points and then plot the corresponding lines for those points in the (x,y) plane.
```
No. of red lines detected is 6
No. of blue lines detected is 8
```

7.  We perform Hough Transform by using a Circle. 
8.  For each point we draw a circle, and the point which has the most number of intersections (voting) will be the center of the coin. 
9.  Hence we find the most frequent point centers and draw circles on the original image. By doing so, we detect the coins in the image.
