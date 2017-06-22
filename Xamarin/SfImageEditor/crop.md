---
layout : post
title : Cropping Image in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to crop an image in ImageEditor for Xamarin.Forms
platform : Xamarin.Forms
control : ImageEditor
documentation : ug
---

# Crop

The image editor control gives you an option to crop the image as desired. Cropping the image can be done in two ways:

* From Toolbar
* Cropping programatically

### From Toolbar

From the `Transforms` submenu, click on the `Crop` button. It will enable cropping and a selector region appears on top of the image which stretches to the size of the image. The toolbars will disappear while cropping is enabled and only `Cancel` and `OK` buttons will be available. To disable cropping region, click on `Cancel` button. Click on the `OK` button after selecting the desired area for cropping and the toolbars will be reappear after the cropping operation is completed.

### Cropping Programatically

Cropping operation can be done programmatically in two ways:

* Enable Cropping and Selecting the Crop region visually
* Manually enter the cropping area

#### Handling the cropping tool

The `ToggleCropping` method in the SfImageEditor control is used to enable and disable a cropping region placed over the image to visually choose the area for cropping. After the crop area is selected, the `Crop` method is called which in turn crops the selected region and displays the cropped image on the ImageEditor.

{% tabs %}

{% highlight C# %}

editor.ToggleCropping();

// After selecting the crop area visually
editor.Crop();

{% endhighlight %}

{% endtabs %}



## Manually enter the cropping area

If you want to manually enter the cropping rectangle without even enabling the cropping funtionality, you can make use of the overloaded Crop(Rectangle rect) method. This can be done by defining a rectangle yourself and pass it to Crop(rect) method.

{% tabs %}

{% highlight C# %}

editor.Crop(new Rectangle(100,100,150,200));

{% endhighlight %}

{% endtabs %}

