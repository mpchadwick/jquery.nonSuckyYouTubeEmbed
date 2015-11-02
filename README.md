# jquery.nonSuckyYouTubeEmbed

Embedding videos using YouTube's iFrame embed code sucks. Just how much does it suck you might ask? Well, each YouTube video you embed forces the user to download roughly 400K of data before they even click play. 

Use *jquery.nonSuckyYouTubeEmbed.js* for a huge performance boost whenever your site calls for embedded YouTube videos. This plugin takes the YouTube video ID as the ID attribute of the element it is called on and fetches the thumbnail image and displays that first (with a play button laid over). Only when the thumbnail is clicked does it fetch the heavy iFrame. Optimized for responsive design environments!

## Demo

Check out *jquery.nonSuckyYouTubeEmbed* live and in action [here](http://mpchadwick.github.io/jquery.nonSuckyYouTubeEmbed/index.html)...

## Usage

Create an element (or elements) with the ID attribute set to the video's YouTube ID. For example if the video's URL is youtube.com/watch?v=HoQN7K6HdRw then the ID is HoQN7K6HdRw.

```
<div id="CqZgd6-xQl8" class="nonSuckyYouTubeEmbed"></div>
```

Then call the plugin on that (or those) element(s).

```
$('.nonSuckyYouTubeEmbed').nonSuckyYouTubeEmbed();
```

## HTML Attributes

The following attributes can (and should) be set on each element that *jquery.nonSuckyYouTubeEmbed()* is called on. These attributes are set on the element rather than as options when calling the plugin so the plugin can easily be called on a group of elements where these attributes are different.

**data-width:** The width of the iFrame player. While *jquery.nonSuckyYouTubeEmbed* will make the iFrame responsive / fluid, this value, combined with data-height is used to calculate the iFrame's aspect ratio. This parameter is optional but recommended to avoid black bars on the sides of the video.

**data-height:** The height of the iFrame player. While *jquery.nonSuckyYouTubeEmbed* will make the iFrame responsive / fluid, this value, combined with data-width is used to calculate the iFrame's aspect ratio. This parameter is optional but recommended to avoid black bars on the sides of the video.

**data-alt:** The alt text for the thumbnail image. Optional, but recommended.

## Options

The following options are available when calling *jquery.nonSuckyYouTubeEmbed*...

**defaultWidth:** This will be used for the iFrame's width if the `data-width` attribute is not supplied.

**defaultHeight:** This will be used for the iFrame's height if the `data-height` attribute is not supplied.

**playBtnSrc:** Source of play button that is laid over thumbnail. Default uses data URI

**playBtnStyle:** If you are changing the play button source you will need to change the style as well to ensure that it is centered over the thumbnail. Here's a code snippet on [how to do that](http://css-tricks.com/snippets/css/exactly-center-an-imagediv-horizontally-and-vertically/). Parameter takes a string of CSS that will be used for the inline style attribute on the play button element.

**thumbStyle:** A string of CSS that will be used for the inline style attribute on the thumbnail image. Uses `width: 100%; height: auto; display: inline; cursor: pointer` by default to make images responsive. If you are changing this keep in mind that `display: inline;` is important for to keep the play button laid on top of the thumbnail.

## Browser Compatibility

Tested in the following browsers...

**On Mac OS X 10.9** 

- Chrome 31.0.1650.57
- Firefox 25.0.1
- Safari 7.0
- Opera 12.16

**Via BrowserStack**

- IE 7+ (With IE 7 you need to change play button source to non-dataURI)
- iOS 4+
- Android 4.0 (Motorola Razr)
- Android 2.2 (LG Optimus 2.2)

## Gotchas

- The videos are fetched with `autoplay=1` in the URL, but autoplay generally does not work on mobile, so users will have to click play one more time :/. See [this Stack Overflow thread](http://stackoverflow.com/questions/8141652/youtube-embedded-video-autoplay-feature-not-working-in-iphone)
