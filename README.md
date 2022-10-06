# Easy zoom plugin
Plugin to increase individual elements of the image when moving the cursor over it.

In the header we include the files:

```js
<script type="text/jаvascript" src="https://ajax.googleapis.com/ajax/libs/jquery/1.6.1/jquery.min.js"></script>
<script type="text/jаvascript" src="easyzoom.js"></script>
```

# HTML

```html
<a href="large.jpg" class="zoom"><img src="small.jpg" alt="Город"></a>
```

This plugin is configurable with a few options and simple CSS properties.

# CSS

In styles, you need to specify the size, location and appearance of the pop-up element with an enlarged image.

```css
#easy_zoom{
    width:600px;
    height:400px;    
    border:5px solid #eee;
    background:#fff;
    color:#333;
    position:absolute;
    top:15px;
    left:400px;
    overflow:hidden;
    -moz-box-shadow:0 0 10px #555;
    -webkit-box-shadow:0 0 10px #555;
    box-shadow:0 0 10px #555;
    /* vertical and horizontal alignment used for preloader text */
    line-height:400px;
    text-align:center;
}
```

Of course, you can tweak and change these settings in CSS.

# Plugin Options

**id**

**Default value:** "easy_zoom"
The ID of the newly zoomed element. You can use your own name, but do not forget to correct it in CSS then.

**parent**

**Default value:** "body"
Specifies the DOM element into which the element created by the zoom will be inserted. You can insert it anywhere in the DOM by editing this parameter.

**append**

**Default value:** "true"
If set to true (default) the newly created element will be inserted as the last child of the parent element. If set to false, then the newly created element will be inserted as the first child element of the parent element.

**preload**

**Default value:** "Loading..."
A message that appears before a large image is loaded. Any text can be used. If you want to use a GIF image, it's better to embed it via background.

**error**

**Default value:** "There has been a problem with loading the image."
In case a large image is not found or cannot be loaded, this error message will appear. You can edit this setting to your liking.

**Here is a code example of how the above options can be used:**

```js
jQuery(function($){
    
    $('a.zoom').easyZoom({
        id: 'imagezoom',
        preload: '<p class="preloader">Loading the image</p>'
        parent: '#container'
    });
});
```