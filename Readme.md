# ETKRes-Arcade
Resources for Emuteca: Arcade

Icons, images, texts, videos, etc. for use with [Emuteca](https://github.com/Chixpy/Emuteca).

## About MAME resources

By default, Emuteca will search and use multimedia resources based in videogame's name when importing game's data from de default database. Specifically; **groups** will search files this way, while games will use their filenames.

Therefore, I'll note two things:
1. Using files named with MAME style, only games will have images but not groups.
2. Using this repository with MAME (or other compatible frontend) will not work at all.

You can read more about media files in [Emuteca's Web Page](https://chixpy.github.io/Emuteca/pages/Media-Files.html) (but it's in spanish...)

Actually, Emuteca **can** use MAME filenames. There is a script that create the arcade database from a MAME executable and that script can be modified to automatically set the parent's filename to group's mediafile. Another way; may be easier, it's to edit the arcade group database (.egl file, which is actually a .cvs) and copy ID column into Mediafilename's one. (Yes, Emuteca internally uses MAME id as internal group id)

![Emuteca using MAMU icons...](https://chixpy.github.io/Emuteca/img/WhyEmuteca/EmutecaGroup.png)

### Why Emuteca is not using MAME filename schema by default?

In Emuteca, game parentship is a little different than MAME. In MAME, a *parent* is actually a *game*; while in Emuteca a group only is a *container* used for grouping game versions. A *MAME parent* is a *game version* in Emuteca.

As in other systems; Emuteca tries to minimize the need of a exclusive image, icon, title, etc. for every single game version. This is the main goal for grouping in Emuteca, one image for all game versions and, optionally, we can assign other specific images to different versions (And when I say 1 imagen it can be many images).

In more than 20 years... Nobody thinked about it? A simply fallback to parent searching images?

And... I don't answer the question yet, LOL.

Well, in the beggining, Emuteca took care about using MAME standard filename schema. But after thinking about, this way we can assign more than one image to a group, files are easyly identified by filename, we don't care if a game file id is changed in MAME, etc.

- ***Note:***
  - Files used directly by MAME, like Artwork or Samples, must have their MAME filenames, obviously. They don't are interesting for Emuteca anyways (Artworks maybe a little..., but there are artwork preview images)

### And Main Boards, Flyers, and other no-console stuff?

In Emuteca you can change all media folders as needed in System Editor. No problem here, except that they must edited manually.

### And "other" machines supported by MAME?

**Other machines** are... **other systems**. 

There is a little *mess* here. Loading arcades in MAME is different than loading a software to a system emulated by MAME, they must be handled in their respective systems for loading their software.

But, you can run many systems as is, without any software (microcomputers); and there are some machines that are not arcade but are *self-contained* (handhelds, chessborads, etc...). In this case it's better use a system for this kind of emulated machines.

## Download

Use GIT to clone the repository or download it in zip:

https://github.com/Chixpy/ETKRes-Arcade/archive/main.zip

## About Images

### Screenshot, Titles

***Rule #1:*** No filters to screenshots.

All images in .png format at original arcade resolution. There are many different resolutions... and there are games that use overscan (output image is bigger than actuallly intended to be) but we will keep it.

### ~~Front, Back, Spine,~~ Manual, Ads, Reviews, ~~Media,~~ Other

- ***Note:*** 
  - In Emuteca you can change all media folders as needed in System Editor for Flyers, Mainboards, Controls, etc.

Generally:

  * Scanned .jpg images 
  * Maximum of 2048px in its largest side, if its smaller don't scale it up.
  * If it's larger than 2048px, it's best to crop (see below) before scaling it down to 2048. Keeping aspect ratio.
  * Trying not to resave it many times. There are some transformations that can be done without lossing quality...

For game's media (Front, Back, Spine, Manual and Media):

  * Box Front, Back and Spine in separated images and cropped without any border. 
  * Media: Whole cart, CD, etc. scanned and cropped without any border (if possible)

For Magazine texts:

  * Crop original page image to article text and game images, with a little border.

For Maps (or magazine game guides):

  * If it's a magazine game guide: Same as Magazine texts.
  * If it's a digital map (made of screenshots or similar): Better in .png format and keep it as is (do not remove author, or other info; and if it's bigger than 2048px keep the size too)

For non Scanned images, as photographs, maybe we want to keep same rules. 

### Icons, Logos

Rule #1: Only 1 image for group or game. No folders with multiple images.

- ***Note about MAMU icons:***
  - MAMU icons, althougt they are beautiful, they are heavyly edited, rescaled and aspect ratio fixed. They will not be there, but there is not problem for using them in Emuteca (after renamed or group database edited).

Icons are mainly extracted from game screenshots at original resolution. Usually they are protagonist frames, lives icons or a recognizable icon.

Logos are usually extracted from Title or Main Menu screens.

All images are .png format. Width and Height are variable, using it's original size without resizing to a fixed size or adding more border to make it square. Emuteca handle they automatically.

The only time that the image will be scaled is when all 'icon pixels' are 2x2, 3x3, etc. pixels.

After extracting the icon image with transparent background, a border is added: Middle grey, half transparency (128, 128, 128, 128). 

[Emuteca](https://github.com/chixpy/emuteca) has [ETKIconBorder](https://github.com/Chixpy/Emuteca/blob/master/bin/Tools/ETKIconBorder.exe) tool in its distribution. A simple image editor to cut, extract, make transparency in images and apply filters to original image.

Alternatively, there is a [GIMP's script](https://github.com/Chixpy/Emuteca/tree/master/bin/Tools/Icon%20Border%20Gimp%20script) too, that can add the border automatically after transparent background is created. But it's slooooow.

## About Texts

Raw text .txt.

Better if:

  * Empty line between paragraphs.
  * No new line inside paragraphs (Textbox has wordwrap activated).
  