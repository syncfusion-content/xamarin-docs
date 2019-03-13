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
 
## Icon Customization

Default icons in the navigation header can be customized by using the following ways,

### Default icons in Navigation Page

When the backdrop page is created as single Page, the revealing and concealing back layer icon are hamburger and close icon in default.

![Hamburger icon](Header-Configuration-images/Hamburger.png)

![Close icon](Header-Configuration-images/Close.png)

### Default icons in MasterDetailsPage

When the backdrop page is created under the masterdetailspage, the revealing and concealing back layer icon are Down arrow and Up arrow icon in default.

![Down Arrow icon](Header-Configuration-images/DownArrrow.png)

![Up Arrow icon](Header-Configuration-images/UpArrow.png)

### Custom icons

You can customize the open icon and close icon in the navigation header by setting the OpenIcon and CloseIcon property in SfBackdropPage.

{% tabs %} 

{% highlight xaml %} 

<?xml version="1.0" encoding="UTF-8"?>
<backdrop:SfBackdropPage
    xmlns="http://xamarin.com/schemas/2014/forms"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:backdrop="clr-namespace:Syncfusion.XForms.Backdrop;assembly=Syncfusion.SfBackdrop.XForms"
    x:Class="BackdropGettingStarted.BackdropSamplePage"
    OpenIcon="open.png"
    CloseIcon="close.png"
    Title="Menu">
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
	    this.Title = "Menu";
        }
    }
}

{% endhighlight %}

{% endtabs %}

 ![Custom icons](Header-Configuration-images/IconsCustomization.png)
 
