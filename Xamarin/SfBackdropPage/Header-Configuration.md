---
layout: post
title: Header Configuration with Syncfusion Backdrop Page
description: How to configure a header in backdrop page.
platform: xamarin
control: SfBackdropPage
documentation: ug
---

# Header Configuration

Add backdrop page as a children of [`NavigationPage`](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.navigationpage?view=xamarin-forms) in App.xaml.cs class. Also, [`BarBackgroundColor`](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.navigationpage.barbackgroundcolor?view=xamarin-forms), [`BarTextColor`](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.navigationpage.bartextcolor?view=xamarin-forms) and other properties of [`NavigationPage`](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.navigationpage?view=xamarin-forms) can be set to customize the default appearance of header.
 
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
Page header for the backdrop will appear only when adding backdrop as a children of [`NavigationPage`](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.navigationpage?view=xamarin-forms).
 
## Icon customization

The default icons in the navigation header can be customized using the following ways:

### Default icons in NavigationPage

When the backdrop page contained within the [NavigationPage](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.navigationpage?view=xamarin-forms) , hamburger icon and close icon (X mark ) will be used by default.

![Hamburger icon](Header-Configuration-images/Hamburger.png)

### Default icons in MasterDetailsPage

When the backdrop page placed in the [MasterDetailPage](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.masterdetailpage?view=xamarin-forms), down arrow icon and up arrow icon will be used by default.

![Arrow icon](Header-Configuration-images/Arrow.png)

### Custom icons

You can customize the default icons in the navigation header by setting the OpenIcon and CloseIcon properties in SfBackdropPage.

{% tabs %} 

{% highlight xaml %} 

<?xml version="1.0" encoding="UTF-8"?>
<backdrop:SfBackdropPage
    xmlns="http://xamarin.com/schemas/2014/forms"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:backdrop="clr-namespace:Syncfusion.XForms.Backdrop;assembly=Syncfusion.SfBackdrop.XForms"
    x:Class="BackdropGettingStarted.BackdropSamplePage"
    OpenIcon="open.png"
    CloseIcon="close.png">
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
            this.OpenIcon = "open.png";
            this.CloseIcon = "close.png";
        }
    }
}

{% endhighlight %}

{% endtabs %}

 ![Open Custom icons](Header-Configuration-images/Settings.png)
 
