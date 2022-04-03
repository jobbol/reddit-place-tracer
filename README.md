**Reddit Place Tracer** is a browser based userscript for the 2022 Reddit /r/Place project which adds a transparent image on top of the canvas to aid communities with drawing the same image.  It shows how the canvas should look, where each pixel goes, and what color. The user must manually click on these spots.  It is *not an automated bot* and does not break any rules.

![Demo of the program](/images/demo1.gif?raw=true)

## Installation
1. Download the [TamperMonkey](https://www.tampermonkey.net/) extension for your web browser.![](/images/install-tampermonkey.png?raw=true)
	
2. Create a new script.
   1. Open the userscript from this **[link](https://github.com/lobcog/reddit-place-tracer/raw/main/userscript.user.js)**.  
   2. If it does not open in TamperMonkey skip to manual installation.
   3. Otherwise click **install**.

![](/images/install-script.png?raw=true)

3. Enable updates. 
   1. Go to Extensions > TamperMonkey > dashboard.
   2. Click on the installed script /r/Place Enter the Gungeon template.
   3. Go to settings tab.
   4. Click check for updates and save.

![](/images/auto-update.png?raw=true)

### Manual installation
If opening the script did not open in TamperMonkey:
1. Go to Extensions > TamperMonkey > Create a new script.
2. Copy all text of the userscript from this [link](https://github.com/lobcog/reddit-place-tracer/raw/main/userscript.user.js).
3. Paste text into the file.
4. Save file with **ctrl + s**.
5. TamperMonkey will not update manually copied scripts.

## Usage

1. Visit [/r/place](https://www.reddit.com/r/place/).  
2. If successfully installed, you will see additional buttons in the top left corner next to the close button.
	* The buttons in the top left will toggle each tracing template on and off.
	* Pixels in the canvas that do not match up with the template will be marked with tiny dots.
	* Correct these by placing new pixels on top.  Again, the script will not do this automatically.

![How to mark each spot](/images/usage1.png?raw=true)

## Creating or modifying templates (community leaders only)
Tracing templates must be PNGs at three times the current canvas size.  Use a site such as imgur.com or Discord attachments to host your templates online.

### Download the canvas
1. Visit [/r/place](https://www.reddit.com/r/place/).
2. Hit **F12** to open developer tools.
3. Go to Network tab.
4. Click record or hit **ctrl + E**.
5. Refresh the page with **F5**.
6. Wait for the canvas to load then immediately stop recording **ctrl + E**.
7. In the filter type in **png**.  
8. Sort by largest size and look for names starting with 16489.
9. Click on each image and preview.  Find the canvas images.  They are 1000 x 1000px.
10. Download these for editting.

### Make your templates
1. Open up your favorite pixel editor and stitch the canvas images together.
2. Resize to 300% of original size with aspect ratio kept.
3. Crop out everything but whatever you plan on drawing.  This will be your template.
4. Dither your template.  For each canvas pixel, erase everything but the center. So that when the template is placed on top of the canvas, the canvas can be see through the transparency.  You should have a bunch of dots.  Refer to other templates to see what it looks like.
5. Save as transparent PNGs.

### Make the script your own and add your templates
1. Make the script
	1. In your web browser open Extensions > TamperMonkey > dashboard.
	2. Open the script /r/Place Enter the Gungeon template.
	3. Copy the contents and paste it in a new script.
	4. Rename the script by changing this line `// @name         /r/Place Enter the Gungeon template`.
		* The spaces between @name and /r/ must not be altered.
2. Add/replace the templates in list.
	1. Find this array `const imgs`.
	2. Replace the objects with your templates.
		* name is used for the button togglers in top left.
		* src is a link to the image and should end in .png.



## Future plans
Possibly looking to add a download button for easier template creation and a ghost draw mode to help with planning.  Time has been very stretched though.

## Credit
This is a fork of oralekin's [original userscript](https://gist.github.com/oralekin/240d536d13d0a87ecf2474658115621b).
