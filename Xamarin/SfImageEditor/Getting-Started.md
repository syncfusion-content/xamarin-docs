---
layout: post
title: Getting Started for Essential Xamarin.Forms SfImageEditor
description: This section explains the steps required to load an image to the image editor. Image editor has a built-in toolbar, which has options to edit the image with shapes, path, text, crop, and flip.
platform: xamarin.forms
control: SfImageEditor
documentation: ug
---
# Getting Started

This section explains the steps required to load an image to the image editor.

## Adding Image Editor Reference

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add image editor to your project, open the NuGet package manager in Visual Studio, and search for [Syncfusion.Xamarin.SfImageEditor](https://www.nuget.org/packages/Syncfusion.Xamarin.SfImageEditor/), and then install it. 

![SfImageEditor](ImageEditor_images/Nugetref.png)

To know more about obtaining our components, refer to these links: [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows). Also, if you prefer to manually refer the assemblies instead of NuGet, refer to this [link](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfimageeditor) to know about the dependent assemblies for image editor. 

N>Install the same version of the image editor NUGET in all the projects.

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Launching the application in iOS with image editor

To use the image editor inside iOS application, it requires some additional configurations such as,

To launch the image editor in iOS, call the `SfImageEditorRenderer.Init()` method in the FinishedLaunching overridden method of the AppDelegate class after the Xamarin.Forms framework initialization and before the LoadApplication method is called as demonstrated in the following code sample:

{% highlight C# %} 

 public override bool FinishedLaunching(UIApplication app, NSDictionary options) 

 { 
     … 

     global::Xamarin.Forms.Forms.Init();

     Syncfusion.SfImageEditor.XForms.iOS.SfImageEditorRenderer.Init();

     LoadApplication(new App()); 
     …
 }

{% endhighlight %}

Initialize the ImageEditor

1. Import SfImageEditor control namespace as `xmlns:syncfusion="clr-namespace:Syncfusion.SfImageEditor.XForms;assembly=Syncfusion.SfImageEditor.XForms` in XAML Page.

2. Set the SfImageEditor control as content to the ContentPage.

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

* If image is not set to `Source` property, then the image appearance will be like white canvas and still you can perform editing action with the help of built-in toolbar menu option.


## Load an image to ImageEditor

Refer to the following steps to add an image to the pcl project,

1. Right click on your pcl project. 
2. Select Add Files submenu from Add menu 
3. Dialog box will appear then choose and import the desired image to the pcl project.
4. Once the image is imported please ensure whether you have set image Build Action as `EmbeddedResource`.

>N The loaded image can be of any type like jpeg, png, etc..

To load an image to SfImageEditor follow the below code snippet. We have loaded an image of type jpg and name as "image".

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

N> Refer to this [link](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/images?tabs=vswin#displaying-images) to know more about how to load an image to image editor source property in different format.


* The following screenshot illustrates loaded image of SfImageEditor and you can start to edit the image by using built-in Toolbar menu items.

![SfImageEditor](ImageEditor_images/Gettingstarted.png)