# responsive-images
A guide to best responsive design practices for handling and working with image contents

### Getting Up and Running
###### Why Responsive Image?
* A lot of web pages in today day and age make use of images a lot throughout an web page for better visualization and playfulness
* Usually, 62% of contents on web pages consist of images and graphics, so it is super important for make images show up clearly and properly based of different devices
* To provide viewers high quality images, with fewest bytes possible

### Units, Formats, and Environments
* How to calculate total bits?

        Total bits = (pixels) * (bits per pixel)
        OR, (less pixels) * (better compression) = (less bytes)
    
* Always try to use relative sizing to better scale your images on different screen sizes
    ```css
        .image-container {
          width: 100vw;
        }  
        /*
          Relative sizing has been implemented with max width set to 50%. 
          So now, no matter what device you are on, the width of the image will always be relative to the .image-container element.
          But also, keep in mind, since we used the "max-width" property instead of "width," the image will only expand or shrink to 50% of .image-container, UNTIL it starts surpassing its natural width
        */
        img {
          max-width: 50%;  
        }
    ```
* Setting Image Size Relative to Window Size
    ```css
      .img-1 {
          /*sets the height of the image to 50% of view width*/
          width: 50vw;
          /*sets the height of the image to 100% of view height*/
          height: 100vh;
      } 
      .img-2 {
          /*sets the height and width to view minimum (the shorter size between the window height and width)*/
          width: 100vmin;
          height: 100vmin;
      } 
    ```   
* Raster vs. Vector Images
    * Raster images are made from small dotted pixels whereas vector images are smaller picture chunks combined together to make a larger image
    * Vector images usually scale better visually and in clarity with different screen sizes than raster images
    * Generally, raster image formats are in .png and.jpg; vector image formats are in .svg
    * The file size for vector images are also a lot smaller than raster images  
* Always try to use a smaller sized image whenever possible to shrink load time on a slower network. Size of the image should be no larger than how it should be shown on a page.
* To check page speeds based on image optimization, go to [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) to better investigate page optimization
* Remember the goal, images should not any larger in size than it needs to be viewed and also file size of the image should be compressed as much as possible to save load time on low networks
