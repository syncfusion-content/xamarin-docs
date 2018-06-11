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

## Adding Image Editor Reference

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add image editor to your project, open the NuGet package manager in Visual Studio, and search for [Syncfusion.Xamarin.SfImageEditor](https://www.nuget.org/packages/Syncfusion.Xamarin.SfImageEditor/), and then install it. 

![SfImageEditor](ImageEditor_images/Nugetref.png)

To know more about obtaining our components, refer to these links: [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows). Also, if you prefer to manually refer the assemblies instead of NuGet, refer to this [link](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfimageeditor) to know about the dependent assemblies for image editor. 

N>Install the same version of the image editor NUGET in all the projects.

## Launching the application in iOS with image editor

To use the image editor inside iOS application, it requires some additional configurations as like below,

### iOS

To launch the image editor in iOS, call the SfImageEditorRenderer() method in the FinishedLaunching overridden method of the AppDelegate class after the Xamarin.Forms framework initialization and before the LoadApplication method is called as demonstrated in the following code sample:

{% highlight C# %} 

 public override bool FinishedLaunching(UIApplication app, NSDictionary options) 

 { 
     … 

     global::Xamarin.Forms.Forms.Init();

     Syncfusion.SfImageEditor.XForms.iOS.SfImageEditorRenderer();

     LoadApplication(new App()); 
     …
 }

{% endhighlight %}


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

