# Importing Fonts  (Non-Google Fonts)

This article covers how to use your own fonts in your homebrewery document, specifically fonts that are not from the Google Fonts collection.

> If at all possible, try to find fonts in the Google Fonts collection that will work-- it will be much easier to use.  If you can't find a font there, continue on...

## Overview

The below steps will be covered:

* Create Github.com Account
* Find a font
* Use FontSquirrel.com to create web-font
* Upload web-font to Github
* Import into Homebrewery

### Create Github Account

Once you have your font you will need to host it somewhere on the internet, just like you do with the images in your brew using something like Imgur.  Imgur only hosts images, though, so you'll need a service that can host different file types-- such as **.CSS**. [Github.com](https://www.github.com) is a perfect spot for doing just that.  You'll need to create an account (free).   

> You may discover that you can skip all this if you have downloaded and installed a font on your computer and your brew displays the font just fine...but that only works when viewed from *your* computer!  Hosting your font online means it will be available to anyone viewing your brew.

### Find a Font

You of course will need a font.  There are *many* places to find fonts online.  Since this requires downloading files from the internet be sure you are downloading from reputable sites you trust.  Also, you should be downloading fonts with a permissive license and following the rules in the license.  You are responsible for any font you import into HB.  Two font websites to start with:

* [dafont.com](https://www.dafont.com/)
* [1001fonts.com](https://www.1001fonts.com/)

Look for font file types .woff2, .ttf, or .otf.  Once you have one, download it to your computer in a folder location you can find later.

### Use FontSquirrel to Generate Web-Font

Your font is now downloaded to your computer, but it is not available to access online-- you will need to convert it to a *web-font*.  [FontSquirrel.com](https://www.fontsquirrel.com/tools/webfont-generator) has a convenient generator to do this.  

* Go to the generator and upload your new font.
* Click "Expert" option
* In "Font Formats" choose only **woff2**
* In "TrueType Hinting" choose **Keep Existing** (though I do not have a strong opinion here, and if you have display issues on text with a very small pixel size you might reconsider this).
* "Vertical Metrics" change to **No Adjustment**
* "Subsetting" change to **No subsetting**
* "CSS" change the CSS Filename to `[your font name].css`

You can choose to have it save your settings and then check the agreement box at the bottom and submit. It will open a prompt to save a .zip file which you should save to a folder you can find later and with a name that makes sense.  Unzip the file.

### Upload Font to Github

Now you have a woff2 font and an associated .css file saved on your computer, and you need to upload those to place online where HB can access it.  Go to your github account and create a new Repository (Top of the left sidebar on your github homepage, a green "New" button). 

* Add a repository name such as "Homebrewery Assets" and a Description.
* Set it to a "Public" repo -- *Private repos won't work*
* "Create Repository"

From your new repo, find the "Add file" button and choose "Upload File".  Find where your unzipped webfont folder is and you can import the whole unzipped folder by dragging into github.  Click the "Commit change" button.

Go to this new folder in your repository and open the `.css` file.  The value for the `font-family` property is what your font is called, and what you will need to use in the homebrewery when applying it to an element.

### Import to Homebrewery

There is one more website you'll need to bridge the gap between your font hosted on Github and using in Homebrewery, [githack](https://raw.githack.com).  It's very easy to use, no signup required.  In Github, with your `.css` file open, copy the URL in your address bar.  Paste that address into the top box on githack and you will get two new URLs.  You can use either one-- the left one for 'production' is more ideal but if you think you have made a mistake in any of the previous steps, using the 'development' url might help.  Copy one of them.

In the Style Editor of Homebrewery, paste the URL into the following snippet which **must be at the very top of your Style Editor** (multiple imports can be at the top, though).

    @import url('url here');

The font is now available in the brew.  You will have to figure out how to apply to the elements you want, but basically it is like this:

    .page h1 {
        font-family: 'steambase';
        color: red;
    }

## Conclusion

If you followed the above steps, you have created a Github account, found a font, used various online tools like fontsquirrel and githack, and imported a new font into your homebrew.  This font is only available in brews where you have imported that URL, which can be reused in other brews.

Note that not all fonts have all the glpyhs/characters that your language may require.  Also, many fonts (particularly very artistic ones) only have one 'font' in their 'font-family', and do not have 'bold' or 'italic' pre-made.  The browser can typically fake those font styles but it may not be appealing.  You can create groups of fonts as well, but that is not covered here but there are plenty of resources for further learning online.
