---
layout: post
title: Getting Started with Syncfusion ImageEditor control for Xamarin.Forms
description: Image editor has a built-in toolbar, which has options to edit the image with shapes, path, text, crop, and flip.
platform: xamarin.forms
control: SfImageEditor
documentation: ug
---

# Getting Started

This section explains the steps required to load an image to the image editor control.

## Adding SfImageEditor reference

You can add SfImageEditor reference using one of the following methods:

**Method 1: Adding SfImageEditor reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfImageEditor to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfImageEditor](https://www.nuget.org/packages/Syncfusion.Xamarin.SfImageEditor), and then install it.

![Adding SfImageEditor reference from NuGet](ImageEditor_images/Adding SfImageEditor reference.png)

N> Install the same version of SfImageEditor NuGet in all the projects.

**Method 2: Adding SfImageEditor reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfImageEditor control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfImageEditor assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.SfImageEditor.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfImageEditor.XForms.Android.dll<br/>Syncfusion.SfImageEditor.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfImageEditor.XForms.iOS.dll<br/>Syncfusion.SfImageEditor.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfImageEditor.UWP.dll<br/>Syncfusion.SfImageEditor.XForms.UWP.dll<br/>Syncfusion.SfImageEditor.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/></td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.

N> If you are adding the references from toolbox, this step is not needed.

## Launching the application in iOS

To launch the image editor in iOS, call the `SfImageEditorRenderer.Init()` method in the FinishedLaunching overridden method of the AppDelegate class after the Xamarin.Forms framework has been initialized and before the LoadApplication method is called as shown in the following code sample.

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

## Initializing image editor

1. Import SfImageEditor control namespace as `xmlns:syncfusion="clr-namespace:Syncfusion.SfImageEditor.XForms;assembly=Syncfusion.SfImageEditor.XForms` in XAML page.

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

* If image is not set to the `Source` property, the appearance of the image will be shown as white canvas. You can perform editing action using built-in toolbar.


## Loading an image to image editor

Refer to the following steps to add an image to the pcl project:

1. Right-click your pcl project. 
2. Select **Add Files** submenu from **Add** menu, and a dialog box will appear.
3. Choose and import the desired image to the pcl project.
4. After the image has been imported, ensure whether the image Build Action has been set to `EmbeddedResource`.

N> Image formats such as JPEG and PNG can be loaded to the image editor.

The following code shows adding an image to the image editor control with the format as "JPEG" and name as "image".

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

N> Refer to this [link](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/images?tabs=vswin#displaying-images) to know more about loading an image to the image editor source property in different formats.

* The following screenshot depicts loading an image to the image editor. You can edit the image using built-in toolbar.

![SfImageEditor](ImageEditor_images/Gettingstarted.png)

You can find the complete getting started sample from this [link.](http://www.syncfusion.com/downloads/support/directtrac/general/ze/IESample-621789615)