---
layout: post
title: Getting Started for Essential Xamarin.Forms SfImageEditor
description: This section explains the steps required to load an image to the image editor. Image editor has a built-in toolbar, which has options to edit the image with shapes, path, text, crop, and flip.
platform: xamarin.forms
control: SfImageEditor
documentation: ug
---
# Getting Started

This section explains the steps required to load an image to the image editor. Image editor has a built-in toolbar, which has options to edit the image with shapes, path, text, crop, and flip.

## Reference Essential Studio components in your solution

After the Essential Studio for Xamarin has been installed, you can find all the required assemblies in the installation folders.

{Syncfusion Installed location}\Essential Studio\15.2.0.40\lib

N> Assemblies are available in unzipped package location in Mac.

Refer this [article](https://help.syncfusion.com/xamarin/introduction/download-and-installation) to know how to obtain, and reference Essential Studio components in your solution. Then refer [this](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfimageeditor) link to know about the assemblies required for adding SfImageEditor to your project.

I> After the reference has been added, an additional step is required for iOS projects. You should call Init method in the `SfImageEditorRenderer` as shown in this [KB article](http://www.syncfusion.com/support/kb/7772).

# Initialize the image editor

Import the SfImageEditor namespace as shown below in your respective page.

{% tabs %}

{% highlight XAML %}

    xmlns:imageeditor="clr-namespace:Syncfusion.SfImageEditor.XForms;assembly=Syncfusion.SfImageEditor.XForms"

{% endhighlight %}

{% highlight C# %}

    using Syncfusion.SfImageEditor.XForms;

{% endhighlight %}

{% endtabs %}

* Initialize the image editor as shown below.

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

* Load an image to the image editor as bitmap object for Android. Because, SfImageEditor supports bitmap images in Android. You can load the image to the control as a bitmap object only in Android.
In iOS and UWP, you can load the image to the image editor as image.
  
  * Android
        
           SfImageEditor editor = new SfImageEditor();
           editor.Source = */Your Bitmap */;
           Content = editor;
  * iOS
  
           SfImageEditor editor = new SfImageEditor();
           editor.Source = */Your Image */;
           Content = editor;

  * UWP

           SfImageEditor editor = new SfImageEditor();
           editor.Source = */Your Image */;
           Content = editor;

* The following screenshot illustrates loading the image to the SfImageEditor, you can start to edit the image by using the built-in Toolbars.



![SfImageEditor](ImageEditor_images/Gettingstarted.png)

