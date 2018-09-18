---
layout : post
title : Shapes in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to add text in ImageEditor for Xamarin.Forms
platform : xamarin.forms
control : ImageEditor
documentation : ug
---

## Text

You can annotate the desired text elements to an image using the `AddText` method with customization options.

{% highlight C# %}

    editor.AddText("New Text");

{% endhighlight %}

## Customize text with TextSettings

You can customize the appearance of the text using the `TextSettings` property.

The `TextSettings` property consists of the following properties:

* [`Color`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfImageEditor.XForms~Syncfusion.SfImageEditor.XForms.TextSettings~Color.html): Defines the color of the desired text.
* [`FontSize`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfImageEditor.XForms~Syncfusion.SfImageEditor.XForms.TextSettings~FontSize.html): Specifies the desired font size of the text under text settings.
* [`FontFamily`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfImageEditor.XForms~Syncfusion.SfImageEditor.XForms.TextSettings~FontFamily.html): Specifies the desired font family for text. Six types of font families are available in toolbar: `Arial`, `Noteworthy`, `Marker Felt`, `SignPainter`, `Bradley Hand`, `Snell Round hand`.
* [`Bounds`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfImageEditor.XForms~Syncfusion.SfImageEditor.XForms.TextSettings~Bounds.html): Allows to set frame for the newly added `Text`. You can position the text wherever you want on the image. In percentage, the value of the text frame should fall between 0 and 100.
* [`Opacity`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfImageEditor.XForms~Syncfusion.SfImageEditor.XForms.TextSettings~Opacity.html): Changes the opacity of text.
* [`Angle`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfImageEditor.XForms~Syncfusion.SfImageEditor.XForms.TextSettings~Angle.html): Changes the angle of text.

{% tabs %}

{% highlight C# %}

    editor.AddText("New Text", new TextSettings(){Color = Color.Black, FontSize = 16d, FontFamily="Arial", Bounds = new Rectangle(20, 20, 35, 35), Opacity=0.5f, Angle=50});

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/text.png)

## Custom font family

Using a font that is not in the built-in typeface requires some platform-specific coding. The steps required for each platform are shown as follows.

Download the custom fonts in ttf file format, and add these fonts to required folder in particular project file.

### Android

Add the custom fonts to Assets folder in sample.Droid project.

Right-click the font file, and open properties. In properties, change the "Build Action" property of every font file to `AndroidAsset` and "Copy to output directory" to `Copy Always`.
    
![SfImageEditor](ImageEditor_images/AndroidCustomFont.png)
    
### iOS

Add custom fonts to resource file in sample.iOS project.

Change the "Build Action" property of every font file to `BundleResource` and "Copy to output directory" to `Copy Always`.

![SfImageEditor](ImageEditor_images/iOSCustomFont1.png)
    
Open the `info.plist` file, and select "Source" at the bottom of the file.

After opened the source file, add "Fonts provided by application" to source file, and add the downloaded custom fonts name with .ttf extension.

![SfImageEditor](ImageEditor_images/iOSCustomFont2.png)

### UWP

Add custom fonts to Assets folder in sample.UWP project.

Right-click the font file, and open properties. In properties, change the  "Build Action" property of every font file to `Content` and "Copy to output directory" to `Copy Always`.
    
![SfImageEditor](ImageEditor_images/UWPCustomFont.png)

The following code snippet shows applying custom font family. In forms, Android, and iOS, give the font family name, but in UWP, you should mention font file name with .ttf extension and "#" symbol
with font family name.

{% tabs %}

{% highlight C# %}

    if((Device.OS == TargetPlatform.Android)||(Device.OS == TargetPlatform.iOS))
        editor.AddText("New Text", new TextSettings(){FontFamily="Pacifico"});
    else
        editor.AddText("New Text", new TextSettings(){FontFamily="Assets/Pacifico.ttf#Pacifico"});
{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/FontFamily.png)

## Multiline text and text alignment

### Multiline text
You can annotate multiple line text over an image with the help of text preview window.

### Text alignment
`TextAlignment` is an enum type and text can be aligned with the help of text alignment enum values such as left, right and center. 

N> The default text alignment is `Left` and text alignment is not applicable for single line text.

{% highlight C# %}

    editor.AddText("Hello\nGood morning\nHave a nice day", new TextSettings() {TextAlignment = TextAlignment.Right });

{% endhighlight %}

![SfImageEditor](ImageEditor_images/multiline.png)

## Text Rotation

You can rotate and resize the text by enabling the `RotatableElements` property of image editor. `ImageEditorElements` is an enum type with values Text and CustomView as shown in the following code snippet.

{% tabs %}

{% highlight C# %}

    editor.RotatableElements = ImageEditorElements.Text;   

{% endhighlight %}

{% endtabs %}

N> The default value for RotatableElements is `None`.

You can rotate the text based on a particular angle using `Angle` property in `TextSettings` as shown in the following code snippet. 

{% tabs %}

{% highlight C# %}

    editor.AddText("New Text", new TextSettings(){Angle = 50});    

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/rotation.png)
