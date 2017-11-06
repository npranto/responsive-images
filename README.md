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
* Remember the goal, images should not be any larger in size than it needs to be viewed and also file size of the image should be compressed as much as possible to save load time on low networks

### Images and Markup

##### Text Problems
* text as graphics does not scale well on different devices and the size of graphic file can also take a lot of space and affect load time
* file formats can also be a problem for graphics with text and photo, since as developers, you would have to pick between showing the text or the photo with better resolution; both usually does not scale well together as graphics
* also, texts with graphics makes it difficult to search for search engines; they may not be accessible for screen readers and the text can not be copied either
* __SOLUTION...__ always try to overlay the text on top of the image to treat the image and text differently on different devices

##### CSS Techniques
* limit animations, shadow effects and radius sizes as it affects page load time

##### Symbol Characters
* If possible, try to use unicode character codes (110,000+ characters available) for smaller graphics like an arrow or a smile emoji as they scale better like text

 
### Full Responsiveness
* Use "srcset" attribute for <img> elements to automate browser to choose appropriate image file to render based on screen size
* The browser automatically chooses the image with higher resolution density for quality image
    ```html
        <img src="./path/to/image_1x.jpg" srcset="./path/to/image_1x.jpg 1x, ./path/to/image_2x.jpg 2x"/>
    ```
* Art direction: choosing different image automatically with different screen sizes
    ```html
      <picture>
          <source media="(min-width: 650px)" srcset="./path/to/image-large.jpg" />
          <source media="(min-width: 400px)" srcset="./path/to/image-medium.jpg" />
          <img src="./path/to/image.jpg" />
      </picture>
    ```
* For accessibility purposes, we can also provide screen readers for visually disabled viewers to experience 