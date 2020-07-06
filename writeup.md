# Backgrounds and gradients

Backgrounds and gradients helps us to create a good design . We can use image , solid color an gradients in the backgrounds to make our web page more beautiful.

## Background color

We have a property to set background solid color which is "background-color" or we can use the shorthand property "background" . Background shorthand property can  have image, color or gradient value also. Background-color property accepts the RGB, RGBa, HSL, HSLa, hexadecimal values, color keywords etc.

```
div {
    background-color: #bada55;
  }
```

## Adding Background Image

To add background image "background-image" property is used or we can use "background" shorthand property also . One thing is to be notice that background image dose  not increase the height of an element so element should have some height see the background image . To placed  the path of  the image this property has a function in  it that  is ```url()``` . We have to put the image path inside the brackets .

```
div {
    background-image: url("pattern.png");
  }
```

Adding only the image's path we don't get a better result so we have some other properties to prevent the default behaviour of background image .

### Background repeat

This property have four different values : "repeat", "no-repeat", "repeat-x" and "repeat-y". The "repeat" value is the default value for this property i.e. background repeat horizontally and vertically and "no-repeat" value stops the background image from repeating . The "repeat-x" repeats the background horizontally and "repeat-y" repeeats the background vertically .

```
div {
    background-image: url("pattern.png");
    background-repeat: no-repeat;
  }
```

### Background Position

The "background-position" property accepts two values at a time , first value is for horizontal offset and the second value is for vertical offset . By default first value is 0 (left) and second value is 50% (50% to the bottom). The values can be all general length value or keywords value , keyword values are "left", "right", "top" and "bottom". The left top or 0 0 value will position the background image at the left top corner and right bottom or 100% 100% will position the image in the right bottom corner of the element.

![background-position](https://raw.githubusercontent.com/suraj122/AC-STYLE-images/master/backgroun-and-gradients/bg-position.svg)

```
div {
    background-image: url("pattern.png");
    background-repeat: no-repeat;
    background-position: 16px 50%;
  }
```

### Shorthand Background Property

```
div {
    background: #bada55 url("pattern.png") 16px 50% no-repeat.
  }
```

The first value is for background-color, second for background-image, third and fourth for background-position, and last is for background-repeat.

It recommended that while using background image shorthand property always provides a fallback background-color. In case, the image is not displayed, the color will display in the background.

### Background Size Property

By using the length values in this property we can set the width and height of the background image with space-separated. This property accepts two value the first value specifies the width and the second value specifies the height of the image. Specifying only one value will set the width of the background image and height will be auto to preserve the aspect ratio. The auto value can be used for any of the width and height to preserve the aspect ratio of the image. Percentage value will be in relation to the element's size not the background image's size.

```
div {
    background: url("pattern.jpg") 0 0 no-repeat;
    background-size: auto 75%;
  }
```

This property accepts some single keyword too i.e. "cover" and "contain". Using the cover value will resize the image to cover the element's background(height and width) completely. The image will stretch or shrink to cover entirely but the aspect ratio of the image will be preserved and the contain value will also resize the image to reside inside the width and height of the element. Here also the aspect ratio of the image will be preserved, but the image will shrink or stretch to remain within the width and height of the element.

## Adding CSS Gradient

Gradients treated as a background image so we can use "background-image" or "background" property to set a gradient to the background . CSS allows us to apply two types of the gradient: linear-gradient and radial-gradient.

### Linear Gradient Background

Linear gradient can be applied using linear-gradient() function within the background or background-image property. The linear-gradient() function must have two or more than two colors. The first value will be the beginning color and the last value will be the ending color value. In the middle somewhere the browser will handle the transition between the colors. By default, the linear gradient background colors will move top to bottom within an element. However, you can control the direction of the colors.

```
.hero {
    background-image: linear-gradient(#4747df, #00ccff);
  }
```

#### Controlling the Direction of Gradient

We can control the gradient direction by adding keyword value or degree value before the colors . The keywords values are "to right", "to left", "to top", "to bottom", "to right top", "to right bottom", "to left top", "to left bottom", "to top right", "to top left", "to bottom left" and "to bottom right". The "to bottom" value is the default value .

```
.hero {
    background-image: linear-gradient(to right, #4747df, #00ccff);
  }
```
In this example the gradient will start from left and end at right.

```
.hero {
    background-image: linear-gradient(to top right, #4747df, #00ccff);
  }
```
In this example the gradient will start from bottom left corner and end at top right corner. We can also use degree for this which will be "45deg". The degree value is also based on the same concept that we all know, 0 through 360.

```
.hero {
    background-image: linear-gradient(45deg, #4747df, #00ccff);
  }
```

### Radial Gradient Background

Like linear-gradient, there is radial-gradient background also in CSS where color moves radially. It can be applied using the radial-gradient() function, with the same values as we have applied in linear-gradient. The first color starts from center and end at the edge of the content .

```
.bg-secondary {
    background-image: radial-gradient(#4747df, #00ccff);
  }
```

>We can stops the color of any gradient

#### Gradient Color Stop

If we add only some colors to the gradient then browser will show the color equally so we can stops the color and give a specific width to the colors be placing  a length value after the color separated by space .

```
.hero {
    background: linear-gradient(#df4747, #247cca 75%, #06b407);
  }
```

We can stops the color fully (color does not mixed with each other) by placing the same length value to each color which means the first color stops at the specific length value and second color will starts from the same length value.

 ```
 .bg-secondary {
     background: radial-gradient(#df4747 50%, #247cca 50%)
   }
 ```

## Multiple Background Images

We can have many background images separating by commas. The first value will be the foremost background image and the last value will the rearmost background image. The value between first and last will sit between the foremost and rearmost background image.

```
div {
    background:  url("foreground.png") 0 0 no-repeat, url("middle-ground.png") 0 0 no-repeat, url("background.png") 0 0 no-repeat;
  }
```

The multiple background concept is with images only. You cannot combine the background-color and background-image at the same time. But we can use transparent color with images separating by space.

```
div {
    background: rgb(0, 0, 0, 0.5) url("pattern.png") 0 0 no-repeat;
  }
```
Or we can use gradient with background images by placing two same color to the gradient.

```
div {
    background: url("pattern.png") 0 0 no-repeat, linear-gradient(#D2EBFF, #D2EBFF);
  }
```
