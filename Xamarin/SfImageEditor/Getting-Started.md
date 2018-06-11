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


## Creating a simple ImageEditor sample

This section explains how to create a SfImageEditor and configure it. The SfImageEditor control can be configured entirely in C# code or by using XAML markup.

### Creating the project

Create a new [BlankApp application](https://developer.xamarin.com/guides/xamarin-forms/xaml/xaml-basics/getting_started_with_xaml/) (Xamarin.Forms.Portable) in Xamarin Studio or Visual Studio for Xamarin.Forms.

### Adding SfImageEditor in Xamarin.Forms 

1. Add the [required assembly](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfimageeditor) references to the pcl and renderer projects. 

2. Import SfImageEditor control namespace as `xmlns:syncfusion="clr-namespace:Syncfusion.SfImageEditor.XForms;assembly=Syncfusion.SfImageEditor.XForms` in XAML Page.

3. Set the SfImageEditor control as content to the ContentPage.

{% tabs %}

{% highlight xaml %}

            <?xml version="1.0" encoding="UTF-8"?>
            <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
                xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" x:Class="ImageEditor_GettingStarted.ImageEditor_GettingStartedPage"
                xmlns:imageeditor="clr-namespace:Syncfusion.SfImageEditor.XForms;assembly=Syncfusion.SfImageEditor.XForms">
                <ContentPage.Content>
                    <imageeditor:SfImageEditor />
                 </ContentPage.Content>
            </ContentPage> 

{% endhighlight %}

{% highlight c# %}

    using Syncfusion.SfImageEditor.XForms;
    using Xamarin.Forms;

    public class App : Application
        {
            public App()
            {
                MainPage = new ImageEditor_GettingStartedPage();
            }

        }
    Public class ImageEditor_GettingStartedPage : ContentPage
    {
        public ImageEditor_GettingStartedPage()
        {
            InitializeComponent();
            SfImageEditor editor = new SfImageEditor();
            this.Content = editor;
        }
    }
{% endhighlight %}
{% endtabs %}


## Load image to ImageEditor

SfImageEditor will get completed,once we load image to it.Add a image file to pcl project.The image file type can be jpeg or png.

Follow the following steps to add a image to pcl project

1. Right click on your pcl project. 
2. Select Add Files submenu from Add menu 
3. Dialog box will appear then choose and import the desired image to the pcl project.
4. Once the image is imported please ensure whether you have set EmbeddedResource as Build Action 

To load an image to SfImageEditor follow the below codes.We have loaded a image of type jpg and name as "image".

{% tabs %}

{% highlight xaml %}

    <?xml version="1.0" encoding="UTF-8"?>
      <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
            xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" x:Class="ImageEditor_GettingStarted.ImageEditor_GettingStartedPage"
            xmlns:imageeditor="clr-namespace:Syncfusion.SfImageEditor.XForms;assembly=Syncfusion.SfImageEditor.XForms">
            <ContentPage.Content>
                <imageeditor:SfImageEditor Source="{Binding Image}" />
             </ContentPage.Content>
      </ContentPage> 

{% endhighlight %}

{% highlight c# %}

    using Syncfusion.SfImageEditor.XForms;
    using Xamarin.Forms;

    public class App : Application
        {
            public App()
            {
                MainPage = new ImageEditor_GettingStartedPage();
            }

        }
    Public class ImageEditor_GettingStartedPage : ContentPage
    {
        public ImageEditor_GettingStartedPage()
        {
            InitializeComponent();
            BindingContext = new ImageModel();
            SfImageEditor editor = new SfImageEditor();
            this.Content = editor;
        }
    }

    class ImageModel
    {
        public ImageSource Image { get; set; }

        public ImageModel()
        {
            Image = ImageSource.FromResource("ImageEditor_GettingStarted.Image.jpg");
        }
    }

{% endhighlight %}
{% endtabs %}


* The following screenshot illustrates loading the image to the SfImageEditor, you can start to edit the image by using the built-in Toolbars.


![SfImageEditor](ImageEditor_images/Gettingstarted.png)

