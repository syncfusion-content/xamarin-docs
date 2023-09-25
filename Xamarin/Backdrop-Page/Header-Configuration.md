---
layout: post
title: Header Configuration with Syncfusion Backdrop Page
description: How to configure and customize the header in the Syncfusion backdrop page control in Xamarin.Forms platform.
platform: xamarin
control: SfBackdropPage
documentation: ug
---

# Header Configuration

Add backdrop page as a children of [`NavigationPage`](https://learn.microsoft.com/en-us/dotnet/api/xamarin.forms.navigationpage?view=xamarin-forms) in App.xaml.cs class. Also, [`BarBackgroundColor`](https://learn.microsoft.com/en-us/dotnet/api/xamarin.forms.navigationpage.barbackgroundcolor?view=xamarin-forms), [`BarTextColor`](https://learn.microsoft.com/en-us/dotnet/api/xamarin.forms.navigationpage.bartextcolor?view=xamarin-forms) and other properties of [`NavigationPage`](https://learn.microsoft.com/en-us/dotnet/api/xamarin.forms.navigationpage?view=xamarin-forms) can be set to customize the default appearance of header.
 
{% highlight C# %} 

// In App.xaml.cs 
#region Constructor

public App()
{ 
   … 
  MainPage = new NavigationPage(new BackdropSamplePage());
   … 
}

#endregion 

{% endhighlight %}

>**NOTE**
Page header for the backdrop will appear only when adding backdrop as a children of [`NavigationPage`](https://learn.microsoft.com/en-us/dotnet/api/xamarin.forms.navigationpage?view=xamarin-forms).
 
## Icon customization

The default icons in the navigation header can be customized using the following ways:

### Default icons in NavigationPage

When the backdrop page contained within the [NavigationPage](https://learn.microsoft.com/en-us/dotnet/api/xamarin.forms.navigationpage?view=xamarin-forms) , hamburger icon and close icon (X mark ) will be used by default.

![Hamburger icon](Header-Configuration-images/Hamburger.png)

### Default icons in MasterDetailsPage

When the backdrop page placed in the [MasterDetailPage](https://learn.microsoft.com/en-us/dotnet/api/xamarin.forms.masterdetailpage?view=xamarin-forms), down arrow icon and up arrow icon will be used by default.

![Arrow icon](Header-Configuration-images/Arrow.png)

### Custom icons

Customize the default icons in the navigation header by setting the [`OpenIconImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Backdrop.SfBackdropPage.html#Syncfusion_XForms_Backdrop_SfBackdropPage_OpenIconImageSource) and [`CloseIconImageSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Backdrop.SfBackdropPage.html#Syncfusion_XForms_Backdrop_SfBackdropPage_CloseIconImageSource) properties in [`SfBackdropPage`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Backdrop.SfBackdropPage.html). It accepts following inputs:
* FileImageSource
* UriImageSource
* FontImageSource
* StreamImageSource

>**NOTE**  UriImageSource will not work in iOS platform. 

{% tabs %} 

{% highlight xaml %} 

<?xml version="1.0" encoding="UTF-8"?>
<backdrop:SfBackdropPage
    xmlns="http://xamarin.com/schemas/2014/forms"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:backdrop="clr-namespace:Syncfusion.XForms.Backdrop;assembly=Syncfusion.SfBackdrop.XForms"
    x:Class="BackdropGettingStarted.BackdropSamplePage"
    OpenIconImageSource="open.png"
    CloseIconImageSource="close.png">
</backdrop:SfBackdropPage>

{% endhighlight %}

{% highlight C# %} 

using Syncfusion.XForms.Backdrop;	
namespace BackdropGettingStarted
{
    public partial class BackdropSamplePage : SfBackdropPage
    {
        public BackdropSamplePage()
        {
            InitializeComponent();
            this.OpenIconImageSource = "open.png";
            this.CloseIconImageSource = "close.png";
        }
    }
}

{% endhighlight %}

{% endtabs %}

![Open Custom icons](Header-Configuration-images/Settings.png)
 
## Icon text customization

You can customize the icon text in the navigation header by setting the [`OpenText`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Backdrop.SfBackdropPage.html#Syncfusion_XForms_Backdrop_SfBackdropPage_OpenText) and [`CloseText`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Backdrop.SfBackdropPage.html#Syncfusion_XForms_Backdrop_SfBackdropPage_CloseText) properties in [`SfBackdropPage`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Backdrop.SfBackdropPage.html).

{% tabs %} 

{% highlight xaml %} 

<?xml version="1.0" encoding="UTF-8"?>
<backdrop:SfBackdropPage
    xmlns="http://xamarin.com/schemas/2014/forms"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:backdrop="clr-namespace:Syncfusion.XForms.Backdrop;assembly=Syncfusion.SfBackdrop.XForms"
    x:Class="BackdropGettingStarted.BackdropSamplePage"
    OpenText="Show Menu"
    CloseText="Hide Menu">
</backdrop:SfBackdropPage>

{% endhighlight %}

{% highlight C# %} 

using Syncfusion.XForms.Backdrop;	
namespace BackdropGettingStarted
{
    public partial class BackdropSamplePage : SfBackdropPage
    {
        public BackdropSamplePage()
        {
            InitializeComponent();
            this.OpenText = "Show Menu";
            this.CloseText = "Hide Menu";
        }
    }
}

{% endhighlight %}

{% endtabs %}

![Open and Close icon text](Header-Configuration-images/OpenIconCloseIconText.png)
