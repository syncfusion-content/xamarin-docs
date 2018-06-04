---
layout : post
title : Shapes in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to add text in ImageEditor for Xamarin.Forms
platform : xamarin.forms
control : ImageEditor
documentation : ug
---

# Text

To add the desired text elements over the image, use the following two ways:

* From Toolbar
* Using Code

### From Toolbar

To add text from the toolbar, click the Text icon in the toolbar. When the Text is tapped, a pop-up window will appear. To add the text over the image, type the desired text, and click OK. To close the pop-up window, click CANCEL button. By dragging, the text can be moved to the desired place, and Text can be resized with the help of handle.

#### Change Color of the selected Text

To change the color of the selected text, select the desired text, and click the color buttons available in the sub menu.

### Using Code

You can also add the desired text elements over the image programmatically. The `AddText` method in the SfImageEditor control is used to add the text based on the string value and `TextSettings`.

#### TextSettings

TextSettings is defined to set the values for `Color`, `FontSize` and `FontFamily`. By default there are six types of font familiy has been given in toolbar that are 
`Arial`, `Noteworthy`, `Marker Felt`, `SignPainter`,`Bradley Hand`, `Snell Roundhand`.


{% tabs %}

{% highlight C# %}

    editor.AddText("New Text", new TextSettings(){Color = Color.Green, FontSize = 16d, FontFamily="Noteworthy"});

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/text.png)

# Custom Font Family

Download the custom fonts file in ttf file format and add these fonts into required folder in particular project file.

#### Android

Add the custom fonts into Assets folder in sample.Droid project.
   
Right click the font file and open properties, in that Change the "Build Action" property of every font file as "AndroidAsset" and "Copy to output directory" to "Copy Always".
    
![SfImageEditor](ImageEditor_images/AndroidCustomFont.png)
    
Finally use the below code snippet to apply custom font family for forms Android. In forms Android you just give the font family name.

{% tabs %}

{% highlight C# %}

    editor.AddText("New Text", new TextSettings(){FontFamily="Pacifico"});

{% endhighlight %}

{% endtabs %}

#### iOS

Add the custom fonts into Resource file in sample.iOS project.
    
Change the "Build Action" property of every font file as "BundleResource" and "Copy to output directory" to "Copy Always".

![SfImageEditor](ImageEditor_images/iOSCustomFont1.png)
    
Open the "info.plist" file and select "Source" at the bottom of the file.
After open the source file you should need to add "Fonts provided by application" into the source file and add the downloaded custom fonts name with .ttf extension.

![SfImageEditor](ImageEditor_images/iOSCustomFont2.png)

Finally follow the below code snippet to apply custom font family in Forms iOS.

{% tabs %}

{% highlight C# %}

    editor.AddText("New Text", new TextSettings(){FontFamily="Pacifico"});

{% endhighlight %}

{% endtabs %}

#### UWP

Add the custom fonts into Assets folder in sample.UWP project.

Right click the font file and open properties, in that change the  "Build Action" property of every font file as "Content" and "Copy to output directory" to "Copy Always".
    
![SfImageEditor](ImageEditor_images/UWPCustomFont.png)

Finally use the below code snippet to apply custom font family in forms UWP. While you give the path, You should mention font file name with .ttf extension and "#" symbol
with font family name.

{% tabs %}

{% highlight C# %}

    editor.AddText("New Text", new TextSettings(){FontFamily="Assets/Pacifico.ttf#Pacifico"});

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/FontFamily.png)