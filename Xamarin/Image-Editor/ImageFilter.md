---
layout: post
title: ImageFilter in Syncfusion SfImageEditor control in Xamarin.Forms
description: This section describes how the apply image filter support in SfImageEditor control for Xamarin.Forms platform
platform: xamarin.forms
control: ImageEditor
documentation: ug
---

# Image Filter in SfImageEditor

Using the image editor control, you can add effects such as Hue, Saturation, Brightness, Contrast, Blur, and Sharpen to the image. These effects can be applied from toolbar or using the ApplyImageEffect method. The [`ApplyImageEffect`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_ApplyImageEffect_Syncfusion_SfImageEditor_XForms_ImageEffect_System_Int32_) method contains two arguments: [`ImageEffect`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ImageEffect.html) and [`EffectValue`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_EffectValue). The ImageEffect is an Enum, which contains the following effects:

* Hue
* Saturation
* Brightness
* Contrast
* Blur
* Sharpen 
* None

The EffectValue are the corresponding ImageEffect values, which varies for each effect, and they are explained as follows.

## Hue

The Hue represents the dominant wavelength of the color. The value of hue effect ranges from -180 to 180.

{% highlight C# %}

public MainPage()
{               
    . . .
    editor.ApplyImageEffect(ImageEffect.Hue, 120);
    . . .
}

{% endhighlight %}

![SfImageEditor](ImageEditor_images/Hue.jpg)

## Saturation

The Saturation represents the intensity of the color. The value of the saturation effect ranges from -100 to 100.

{% highlight C# %}

public MainPage()
{               
    . . .
    editor.ApplyImageEffect(ImageEffect. Saturation, -80);
    . . .
}

{% endhighlight %}

![SfImageEditor](ImageEditor_images/Saturation.jpg)

## Brightness

The brightness represents how bright the color is. The value of brightness effect ranges from -100 to 100.

{% highlight C# %}

public MainPage()
{               
    . . .
    editor.ApplyImageEffect(ImageEffect.Brightness, -60);
    . . .
}

{% endhighlight %}

![SfImageEditor](ImageEditor_images/Brightness.jpg)

## Contrast

The contrast represents the color contrast of an image. The value of contrast effect ranges from -100 to 100.

{% highlight C# %}

public MainPage()
{               
    . . .
    editor.ApplyImageEffect(ImageEffect. Contrast, -30);
    . . .
}

{% endhighlight %}

![SfImageEditor](ImageEditor_images/Contrast.jpg)

## Blur

The Blur represents the clearness of the image. The value of blur effect ranges from 0 to 6.

{% highlight C# %}

public MainPage()
{               
    . . .
    editor.ApplyImageEffect(ImageEffect.Blur, 4);
    . . .
}

{% endhighlight %}

![SfImageEditor](ImageEditor_images/Blur.jpg)

## Sharpen

Sharpen is used to highlight edges and fine details in an image. The value of sharpen effect ranges from 0 to 6.

{% highlight C# %}

public MainPage()
{               
    . . .
    editor.ApplyImageEffect(ImageEffect.Sharpen, 2);
    . . .
}

{% endhighlight %}

![SfImageEditor](ImageEditor_images/Sharpen.jpg)

N> The Image Effect enum also contains “None” option, which removes all the previously applied effects, which are not saved displays the original image. When applying effect through the Apply Image effect method, the effects will be saved automatically. But, if you apply effect from toolbar, each effect will be saved only when clicking the OK button, else all the applied effects will not be saved.

![SfImageEditor](ImageEditor_images/ImageFilter.jpg)