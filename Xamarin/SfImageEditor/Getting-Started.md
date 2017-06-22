---
layout: post
title: Getting Started for Essential Xamarin.Forms SfImageEditor
description: This section explains you the steps required to load an image to the image editor. Image editor has a built in toolbar which has options to edit the image with shapes, path, text, crop and flip.
platform: Xamarin
control: SfImageEditor
documentation: ug
---
# Getting Started

This section explains you the steps required to load an image to the image editor. Image editor has a built in toolbar which has options to edit the image with shapes, path, text, crop and flip.

## Reference Essential Studio components in your solution

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders, 

{Syncfusion Installed location}\Essential Studio\15.2.0.40\lib

N> Assemblies are available in unzipped package location in Mac.

Refer this [article](https://help.syncfusion.com/xamarin/introduction/download-and-installation) to know how to obtain and reference Essential Studio components in your solution; then refer [this](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfimageeditor) link to know about the assemblies required for adding SfImageEditor to your project.

I> After adding the reference, currently, an additional step is required for iOS projects. We need to call Init method in the `SfImageEditorRenderer` as shown in this [KB article.](http://www.syncfusion.com/support/kb/7772)

# Initialize the image editor

Import the SfImageEditor namespace as shown below in your resceptive page,

{% tabs %}

{% highlight XAML %}

    xmlns:imageeditor="clr-namespace:Syncfusion.SfImageEditor.XForms;assembly=Syncfusion.SfImageEditor.XForms"

{% endhighlight %}

{% highlight C# %}

    using Syncfusion.SfImageEditor.XForms;

{% endhighlight %}

{% endtabs %}

* Initialize an image editor as shown below,

{% tabs %}

{% highlight XAML %}

     <imageeditor:SfImageEditor>

      </imageeditor:SfImageEditor>

{% endhighlight %}

{% highlight C# %}

     SfImageEditor editor = new SfImageEditor();
     this.Content = editor;

{% endhighlight %}

{% endtabs %}

* Load an image to the image editor as bitmap object for Android.Since SfImageEditor supports bitmap images in Android. you can load the image to the control as a bitmap object only in Android.
In iOS you can load an image to the image editor as image.
  
  * Android
        
           SfImageEditor editor = new SfImageEditor();
           editor.Source = */Your Bitmap */;
           Content = editor;
  * iOS
  
           SfImageEditor editor = new SfImageEditor();
           editor.Source = */Your Image */;
           Content = editor;


If an image is not loaded to the image editor it will display the `Signature` control like white background view where we can draw path and add shapes as if we are doing on a simple canvas.

* Loading the image to the SfImageEditor, you can start to edit the image by using the built-in Toolbars.



![SfImageEditor](ImageEditor_images/gettingstarted.png)

