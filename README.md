PhotoSwipe - The ultimate web photo gallery for your mobile device
==================================================================

[www.photoswipe.com](http://www.photoswipe.com)

Inspired by the iOS photo viewer and Google images for mobile, PhotoSwipe is a HTML/CSS/JavaScript based image gallery specifically targeting mobile devices.

The current version supports mobile handsets running WebKit based browsers, i.e. iOS, Android and Blackberry 6.

PhotoSwipe also runs on the desktop and has been tested on Chrome, Firefox, Safari and Internet Explorer 8 and above.



Features
--------

- Optimised for mobile devices running a WebKit browser.

- Runs on modern desktop browsers, including Internet Explorer 8 and above.

- Multiple input options including swipe gestures (both mouse and screen touches), keyboard control and an interactive on screen toolbar.

- Responsive to device orientation changes.

- Automatically scales images to maximise screen size and orientation.

- Works with your markup and semantic structure. Does not enforce any specific markup.

- Supports image captions.

- Slideshow feature to automatically play through images in the gallery.

- Uses hardware acceleration where possible for smoother transitions and effects.

- Comprehensive customisation options:

    - Presentation controlled via CSS
	
    - Set whether the gallery loops or not i.e. when you reach the end, is the next image the first image, or does the gallery show a bounce effect to indicate that you have reached the end.
  
    - Hide or show captions and toolbar
  
    - Change caption and toolbar positions
  
    - Set the speeds of all animations used, from sliding in to fading.


		
		
Getting Started
---------------

PhotoSwipe comes with an example site to help you get started. 

There are two distributions of the library:

- The default distribution optimised for WebKit and Mozilla based browsers. This distribution uses standard DOM querying and manipulation. It also uses CSS3 transformations for animations.

- The jQuery distribution that uses jQuery as it's engine. 

It is recommended for WebKit based mobile devices to use the default distribution. This distribution will run faster. It does not require jQuery (so one less library to download to your mobile device). It also uses CSS3 to achieve animation effects. This is extremely noticable when running on an iOS device as animation will use hardware acceleration and will feel more "native" to the device. The default distribution will also work on desktop WebKit browsers (such as Chrome and Safari) as well as Firefox.

Use the jQuery distibution if you need to support a wider range of browsers such as Internet Explorer etc. By default, this distributionn will not use hardware acceleration for animation on iOS devices so is noticably slower. You can however override the default animation functionality in jQuery by including the excellent [Animate Enhanced](https://github.com/benbarnett/jQuery-Animate-Enhanced) library.

Both default and jQuery distribution come with a jQuery plugin wrapper to bind elements to the gallery. So for the default distribution, if you really need to, you can still use jQuery to find your images in your HTML document, hook into the jQuery DOM ready event and use the jQuery PhotoSwipe plugin to display the library. The gallery will still be running on the default optimised engine, but you have the convience of jQuery to set things up should you need to.



Getting Started - Default Distribution
--------------------------------------

See "examples/index.html". 

This example assumes no jQuery at all and is heavily optimised for WebKit and Mozilla browsers.

	
Getting Started - Default Distribution (with jQuery plugin)
-----------------------------------------------------------
	
See "examples/jquery-plugin.html". 

This example assumes you want to use the convience of jQuery for initiating the gallery, but still the  optimised engine for WebKit and Mozilla browsers.

	
Getting Started - Default Distribution (with jQuery engine)
-----------------------------------------------------------

See "examples/jquery-engine.html". 

This example assumes you want to use jQuery for the gallery's engine as well as initiating the gallery. It is not advised to use this approach if you are targetting mobile WebKit based devices.

	
Options
-------

- **fadeSpeed**: The speed of any fading elements in milliseconds. Default "400"
	
- **slideSpeed**: How fast images slide into view in milliseconds. Default "250"
	
- **swipeThreshold**: How many pixels your finger has to move across the screen to register a swipe gesture. Default "50"
	
- **loop**: Whether the gallery auto-loops back to the beginning when you reach the end. Default "true"
	
- **flipCaptionAndToolbar**: Place the caption at the bottom and the toolbar at the top
	
- **captionDelay**: How long before the caption is hidden from view in milliseconds. Default "3000"
	
- **captionOpacity**: The opacity of the caption. Default "0.8"
	
- **hideCaption**: Whether to hide the caption or not. If an image does not have a caption, the caption will be hidden irrespective. Default "false"

- **showEmptyCaptions**: Shows a blank caption area even if a caption cannot be found for the current image. Default "false" 
	
- **toolbarDelay**: How long before the toolbar is hidden from view in milliseconds. Default "3000"
	
- **toolbarOpacity**: The opacity of the toolbar. Default "0.8"
	
- **hideToolbar**: Whether to hide the toolbar or not. Default "false"
	
- **slideshowDelay**: The delay between showing the next image when in slideshow mode
	
- **imageScaleMethod**: How images will fit onto the screen. Either "fit" or "zoom". "fit" ensures the image always fits the screen. "zoom" the image will always fill the full screen, this may cause the image to be "zoomed" in and cropped. Default "fit"
	
- **getImageSource**: Function to specify how the gallery obatins image sources. By default, the gallery assumes you send it a list of images with each image wrapped in an anchor tag. The anchor tag will contain the URL to the full size image. You can change this e.g. if you supply a list of images without an anchor tag, and supply the full size URL on the image's "rel" attribute:

		Code.photoSwipe('a', '#Gallery', {
		
			getImageSource: function(el){ 
				return el.getAttribute('rel'); 
			}
		
		});
	
- **getImageCaption**: Like "getImageSource", function to specify how the gallery obatins image captions. By default, the gallery looks for an images "alt" tag.

	
	
Keyboard controls for desktop browsers
--------------------------------------

- **Left cursor**: Previous image

- **Right cursor**: Next image

- **Escape**: Close gallery

- **Space bar**: Show toolbar / caption if they have faded from view. If both are hidden via the configuration, space bar will close the gallery
