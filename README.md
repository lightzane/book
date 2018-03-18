# Book
Turns HTML contents into a simple book.
<br>
A simple book alike feel and look in a web application for reading text especially stories or novels.<br>
Started the project by prioritizing **display** in _mobile_ apps.<br>
<br>

>**Purpose**: Hope **booklovers** will love

<br>

```Book``` plugin made by **JP Aguilar**<br>
email: bhest.pat@gmail.com; jp.eaguilar@gmail.com
<br>

#### MOBILE FIRST
The display is first optimized for mobile devices.<br>
Hence, not yet optimized for desktop.<br>
Still in development...
<br>

## # Features

The book is default to have a memory and can store and remember the reader's last page.\
This was done using **HTML5** ```localStorage```.

<br>

### # Book Navigation
**MOBILE**

Control                     | Will Do
----------------------------|-------------------------------
_swipe left_<br>_tap right_ | turns to ```next``` page
_swipe right_<br>_tap left_ | turns to ```previous``` page
_swipe up_                  | brings back the book information panel

**DESKTOP**

Control                     | Will Do
----------------------------|-------------------------------
_click right_               | turns to ```next``` page
_click left_                | turns to ```previous``` page
_double click_              | brings back the book information panel

<br>

## # Pre-requisites
**CSS**
```
bootstrap.min.css
```

**Javascript**
```
jquery-3.3.1.min.js
bootstrap.min.js
```
<br>

## # Getting Started
Put in ```<head>``` and in ```<body>```, respectively:
```html
<link rel="stylesheet" href="css/book.css">
<script src="js/book.js"></script>
```
Must place ```book.js``` below the pre-requisites.
<br>

## # Plugin
Put this below ```<script src="js/book.js"></script>```
```html
<script>
	$('#sample').book()
</script>
```
<br>

## # HTML Skeleton
The ```Book``` plugin's targeted DOM (in this case: ```#sample```) will always have a ```width=100%``` and ```height=100%```<br>
So just wrap it up in another container to control your own ```width``` and ```height```.
```html
<div id="sample">
	<div class="load"></div>
	<div class="text">
		<!-- Your Text Content Template Goes Here! -->
	</div>
</div>
```
**IMPORTANT**<br>
Your **Content** must follow the template that the ```Book``` can recognize.
<br>

## # Content Template

There are 2 types of content:
- Image *(default)*
- Text

### Image Text as Content
Contents must contain ```<img>``` 
```html
<div id="sample">
	<div class="load"></div>
	<div class="text">
		<!-- These 3 are OPTIONAL -->
		=title("Your book title") 				<!-- default: "Untitled" -->
		=author("Book author") 					<!-- default: "Anonymous" -->
		=synopsis("About the book summary...") 	<!-- default: BLANK and will not be displayed -->
	</div>
	<img src="image-url-01.svg" data-page-number="nope"> <!-- no page number -->
	<img src="image-url-02.svg">
	<img src="image-url-03.svg">
</div>
```

**NOTE**
- The image that will be provided will vary in size and may not cover the whole page.
- Prefer to use transparent background when your image contains only text or typography.
<br>

### Text as Content
Contents will not read ```<img>``` tag, but still can display an image as a page.
```javascript
$('#sample').book({ imageText : false })
```

```html
<div class="text">

	<!-- These 3 are OPTIONAL -->
	=title("Your Book Title") 				<!-- default: "Untitled" -->
	=author("Book Author") 	  				<!-- default: "Anonymous" -->
	=synopsis("About the book summary...")  <!-- default: BLANK and will not be displayed -->


	((Book Cover Title))=cover("Subtitle for the cover")

	Your first paragraph goes here. With a second sentence in this paragraph.
	This will become your 2nd paragraph.

	This is also will become a new paragraph. You may say this is the 3rd paragraph.
	But you can play with it and experiment.

	((Chapter Header))

	The cover parameter will cover a whole page.
	While having no parameters will make your title be on the same page with your paragraphs.

	It is okay to have as many paragraph as you want.
	The Book plugin will make a new page accordingly if it overflowed your pages.

	(())

	But you can force this contents to a new page by using a blank header.

	((img/page.png))=image
	((img/page.png))=image

	Another alternative for the cover is the "image" parameter.
	And the values inside the parameter should be the image URL.

	(())=cover("a dedication for everyone")

	The above has a blank title, and will only display the subtitle.

</div>
```

**NOTE**
- The image that will be provided will vary in size and may not cover the whole page.
- Prefer to use transparent background when your image contains only text or typography
<br>

# IMPORTANT NOTES !!!
**_DO NOT ENTER TOO MUCH CONTENT_**<br>
The code was to loop to each word. Too many words may cause the application to hang.<br>
For now, make images if text is too much. This will prevent the code to loop or cause lag.<br>

## # Text Images (SVG) - Guidelines
Follow these guidelines if you are to create a text image as pages:
- **Artboard Size** - ```360px``` ```640px```
- **Transparent** background
- **Font size** - ```16pt```
- **Indent size** - ```32pt``` (2x font size)
- **Margin** - less than 10% of artboard size
- Create **outlines** to convert the text to vector for scalability
- **Roboto Slab** (Light) font face used

Reference: [The Butterfly](https://timelights.github.io/book/sample-thebutterfly)

<br>
<br>

```Book``` plugin made by **JP Aguilar**<br>
email: bhest.pat@gmail.com; jp.eaguilar@gmail.com

[//]: # ( N O T E S  - T O -  D E V E L O P E R )

[//]: # (To see a user-friendly layout of this file -- Go to this site : stackedit.io)
[//]: # (uigradients.com/<#name>)
[//]: # (#LastFantasy = #e55e88 #61c4e4 -- Hot Pink and Light Blue !!!NOTE!!! This is my own!)
[//]: # (#PacificDream = #34e89e #0f3443 -- Light Green and Dark Teal)

[//]: # (if pure text image, get size from mydevice.io - 360px 640px)
[//]: # (if not pure text image, get size from viewportsizes.com/mine or look at book.js //viewport sizes )
[//]: # (viewport = 360px 560px )

[//]: # ( Adobe Illustrator ! )

[//]: # ( Source Hans Serif - Korean Hangul font)
[//]: # (Other font: https://github.com/adobe-fonts/source-han-serif/blob/release/OTF/Korean/SourceHanSerifK-Light.otf)