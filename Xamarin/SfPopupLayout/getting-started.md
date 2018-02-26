---
layout: post
title: Getting started | SfPopupLayout | Xamarin | Syncfusion
description: Getting started with SfPullToRSfPopupLayoutefresh.
platform: xamarin
control: SfPopupLayout
documentation: ug
---

# Getting Started

This section provides a quick overview for working with SfPopupLayout for Xamarin.Forms.

## Assembly deployment

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Essential Studio Installed location}\Essential Studio\16.1.0.24\Xamarin\lib

Eg:  C:\Program Files (x86)\Syncfusion\Essential Studio\16.1.0.24\Xamarin\lib

N> Assemblies can be found in unzipped package location in Mac

### SfPopupLayout for Xamarin.Forms

The following assembly should be added as reference from the "lib" folder to use SfPopupLayout in the application.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>PCL</td>
<td>pcl\Syncfusion.SfPopupLayout.XForms.dll</td>
</tr>
<tr>
<td>Android renderer</td>
<td>android\Syncfusion.SfPopupLayout.XForms.dll<br/>android\Syncfusion.SfPopupLayout.XForms.Android.dll<br/></td>
</tr>
<tr>
<td>iOS renderer</td>
<td>ios-unified\Syncfusion.SfPopupLayout.XForms.dll<br/>ios-unified\Syncfusion.SfPopupLayout.XForms.iOS.dll<br/></td>
</tr>
<tr>
<td>UWP renderer</td>
<td>uwp\Syncfusion.SfPopupLayout.XForms.dll<br/>uwp\Syncfusion.SfPopupLayout.XForms.UWP.dll<br/></td>
</tr>
</table>

## NuGet installation

To install SfPopupLayout control in the application, configure the NuGet package of the Syncfusion components. Refer to the following KB to configure the NuGet package of the Syncfusion components:

[How to configure package source and install Syncfusion NuGet packages in an existing project?](https://www.syncfusion.com/kb/7441/how-to-configure-package-source-and-install-syncfusion-nuget-packages-in-an-existing-project)

### SfPopupLayout for Xamarin.Forms

The following NuGet package should be added to use SfPopupLayout control in the application:

<table>
<tr>
<th> Project </th>
<th> Required packages </th>
</tr>
<tr>
<td> Xamarin.Forms </td>
<td> Syncfusion.Xamarin.SfPopupLayout</td>
</tr>
</table>

Refer to the following screenshot in which the Syncfusion.Xamarin.SfPopupLayout package is highlighted:

![](GettingStarted_images/NuGetInstall.png)

## Launching the SfPopupLayout on each platform

To use SfPopupLayout inside an application, each platform application must initialize the SfPopupLayout renderer. This initialization step varies from platform to platform and is discussed in the following sections.

### Android

The Android launches the SfPopupLayout without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application.

### iOS

To launch the SfPopupLayout in iOS, you need to call the ` SfPopupLayoutRenderer.Init()` in the `FinishedLaunching` overridden method of the AppDelegate class after the Xamarin.Forms Framework initialization and before the LoadApplication is called, as demonstrated in the following code example:

{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    …
    global::Xamarin.Forms.Forms.Init ();
    SfPopupLayoutRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %} 

### Universal Windows Platform (UWP)

To launch the SfPopupLayout in UWP, you need to call the `SfPopupLayoutRenderer.Init()` in the `MainPage` constructor before the LoadApplication is called, as demonstrated in the following code example:

{% highlight c# %}
public MainPage()
{
    …
    SfPopupLayoutRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %}

### ReleaseMode issue in UWP platform

There is a known Framework issue in UWP platform. The custom controls will not render when deployed the application in `Release Mode`.

The above problem can be resolved by initializing the SfPopupLayout assemblies in `App.xaml.cs` in UWP project as like in below code snippet.

{% highlight c# %}
// In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)
{
    …

    rootFrame.NavigationFailed += OnNavigationFailed;
        
    // you'll need to add `using System.Reflection;`
    List<Assembly> assembliesToInclude = new List<Assembly>();

    //Now, add all the assemblies your app uses
    assembliesToInclude.Add(typeof(SfPopupLayoutRenderer).GetTypeInfo().Assembly);

    // replaces Xamarin.Forms.Forms.Init(e);        
    Xamarin.Forms.Forms.Init(e, assembliesToInclude);
        
    …     
}
{% endhighlight %}

## Create a sample with SfPopupLayout 

This section explains how to create a SfPopupLayout and configure it. 
 
You can download the entire source code of this demo for Xamarin.Forms from [here](http://files2.syncfusion.com/Xamarin.Forms/Samples/PullToRefresh_GettingStartedForms.zip).

## Creating the project

Create a new BlankApp (Xamarin.Forms.Portable) application in Xamarin Studio or Visual Studio for Xamarin.Forms. 

## Adding SfPopupLayout in Xamarin.Forms 

1. Add the required assembly references to the pcl and renderer projects as discussed in the [Assembly deployment](#assembly-deployment) section.
2. Import SfPopupLayout control namespace `Syncfusion.SfPopupLayout.XForms`.
3. Set the any `View` as `Content` of the `SfPopupLayout`.

#### Type A:

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
 <sfPopup:SfPopupLayout x:Name="popUpLayout">
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
     </StackLayout>
    </sfPopup:SfPopupLayout.Content>
  </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            popupLayout.Show();
        }
    }
}
{% endhighlight %}

#### Type B:

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0">
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
     </StackLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfPopupLayout popupLayout;

        public MainPage()
        {
            InitializeComponent();
            popupLayout = new SfPopupLayout();
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            popupLayout.Show(layout);
        }
    }
}
{% endhighlight %}

This is how the final output will look like on iOS, Android and Windows Phone devices.
![](GettingStarted_images/NuGetInstall.png)

### Adding a Label as the ContentView of the SfPopupLayout

Any view can be added as the popup content using the [SfPopupLayout.PopupView.ContentTemplate]() property to refresh it. Refer to the following code example in which a textview is added as a popup content:

#### Type A:

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
 <sfPopup:SfPopupLayout x:Name="popUpLayout">
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
     </StackLayout>
    </sfPopup:SfPopupLayout.Content>
  </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        DataTemplate templateView;
        Label popupContent;

        public MainPage()
        {
            InitializeComponent();
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
            templateView = new DataTemplate(() =>
            {
                popupContent = new Label();
                popupContent.Text = "This is the SfPopupLayout";
                popupContent.BackgroundColor = Color.LightSkyBlue;
                popupContent.HorizontalTextAlignment = TextAlignment.Center;
                return popupContent;
            });

            // Adding ContentTemplate of the SfPopupLayout
            popupLayout.PopupView.ContentTemplate = templateView;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            popupLayout.Show();
        }
    }
}
{% endhighlight %}

#### Type B:

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0">
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
     </StackLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfPopupLayout popupLayout;
        DataTemplate templateView;
        Label popupContent;

        public MainPage()
        {
            InitializeComponent();
            popupLayout = new SfPopupLayout();
            templateView = new DataTemplate(() =>
            {
                popupContent = new Label();
                popupContent.Text = "This is the SfPopupLayout";
                popupContent.BackgroundColor = Color.White;
                popupContent.HorizontalTextAlignment = TextAlignment.Center;
                return popupContent;
            });

            // Adding ContentTemplate of the SfPopupLayout
            popupLayout.PopupView.ContentTemplate = templateView;
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            popupLayout.Show(layout);
        }
    }
}
{% endhighlight %}

This is how the final output will look like on iOS, Android and Windows Phone devices.
![](GettingStarted_images/NuGetInstall.png)

### AppearanceMode

SfPopupLayout supports two types of [SfPopupLayout.PopupView.AppearanceMode](). By default, "AppearanceMode.OneButton" is set. You can change the appearance of the SfPopupLayout by using `SfPopupLayout.PopupView.AppearanceMode` property.
Two different appearance mode in SfPopupLayout as listed below.

<table>
<tr>
<th> Modes </th>
<th> Description </th>
</tr>
<tr>
<td> {{'[OneButton]()'| markdownify }} </td>
<td> Shows SfPopupLayout with OneButton in the FooterView. This is the default value.</td>
</tr>
<tr>
<td> {{'[TwoButton]()'| markdownify }} </td>
<td> Shows SfPopupLayout with TwoButtons in the FooterView.</td>
</tr>
</table>

#### OneButton

In the below code example we have set `SfPopupLayout.PopupView.AppearanceMode` property as `OneButton` which displays only AcceptButton in the FooterView.

##### Type A:

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
<sfPopup:SfPopupLayout x:Name="popUpLayout">
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
     </StackLayout>
    </sfPopup:SfPopupLayout.Content>
  </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
           
            // Setting the AppearanceMode as OneButton
            popupLayout.PopupView.AppearanceMode = AppearanceMode.OneButton;
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
             popupLayout.Show();
        }
    }
}
{% endhighlight %}

##### Type B:

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0">
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
     </StackLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfPopupLayout popupLayout;

        public MainPage()
        {
            InitializeComponent();
           
            popupLayout = new SfPopupLayout();

            // Setting the AppearanceMode as OneButton
            popupLayout.PopupView.AppearanceMode = AppearanceMode.OneButton;
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
             popupLayout.Show(layout);
        }
    }
}
{% endhighlight %}

If we run the above sample with `AppearanceMode` as `OneButton`, the output will appear on iOS, Android and Windows Phone devices as shown below.
![](GettingStarted_images/NuGetInstall.png)

#### TwoButton

In the below code example we have set `SfPopupLayout.PopupView.AppearanceMode` property as `TwoButton` which displays only AcceptButton in the FooterView.

##### Type A:

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
<sfPopup:SfPopupLayout x:Name="popUpLayout">
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
     </StackLayout>
    </sfPopup:SfPopupLayout.Content>
  </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
          
            //Setting the AppearanceMode as TwoButton
            popupLayout.PopupView.AppearanceMode = AppearanceMode.TwoButton;        
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
             popupLayout.Show();
        }
    }
}
{% endhighlight %}

##### Type B:

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0">
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
     </StackLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfPopupLayout popupLayout;

        public MainPage()
        {
            InitializeComponent();
           
            popupLayout = new SfPopupLayout();

            //Setting the AppearanceMode as TwoButton
            popupLayout.PopupView.AppearanceMode = AppearanceMode.TwoButton;
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
             popupLayout.Show(layout);
        }
    }
}
{% endhighlight %}

If we run the above sample with `AppearanceMode` as `TwoButton`, the output will appear on iOS, Android and Windows Phone devices as shown below.
![](GettingStarted_images/NuGetInstall.png)

### Showing SfPopupLayout at various position

SfPopupLayout allows you to show the Popup content at various position based on the requirement.

Following are the list of options available to show SfPopupLayout at various position.

<table>
<tr>
<th> Methods / Property </th>
<th> Description </th>
</tr>
<tr>
<td> {{'[SfPopupLayout.IsOpen]()'| markdownify }} </td>
<td> Shows SfPopupLayout at the center.</td>
</tr>
<tr>
<td> {{'[SfPopupLayout.Show()]()'| markdownify }} </td>
<td> It is similar to SfPopupLayout.IsOpen property.</td>
</tr>
<tr>
<td> {{'[popupLayout.Show(x-position, y-position)]()'| markdownify }} </td>
<td> Shows SfPopupLayout at the specified X and y position.</td>
</tr>
<tr>
<td> {{'[popupLayout.ShowAtTouchPoint()]()'| markdownify }} </td>
<td> Shows SfPopupLayout at the touch point.</td>
</tr>
<tr>
<td> {{'[popupLayout.ShowRelativeToView(View, RelativePosition)]()'| markdownify }} </td>
<td> Shows SfPopupLayout at the position relative to the specified view.</td>
</tr>
</table>

#### IsOpen Property

In the below code example we have open the SfPopupLayout by using `SfPopupLayout.IsOpen` property.

##### Type A:

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
<sfPopup:SfPopupLayout x:Name="popUpLayout">
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
     </StackLayout>
    </sfPopup:SfPopupLayout.Content>
  </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            // Shows SfPopupLayout at the center of the view.
            popupLayout.IsOpen = true;
        }
    }
}
{% endhighlight %}

N > SfPopupLayout.IsOpen property is not applicable for Type B.

If we run the above sample, the below output will appear on iOS device as shown below.
![](GettingStarted_images/NuGetInstall.png)

#### SfPopupLayout.Show()

In the below code example we have open the SfPopupLayout by using `SfPopupLayout.Show()`.

##### Type A:

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
<sfPopup:SfPopupLayout x:Name="popUpLayout">
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
     </StackLayout>
    </sfPopup:SfPopupLayout.Content>
  </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
           // Shows SfPopupLayout at the center of the view.
           popupLayout.Show();
        }
    }
}
{% endhighlight %}

##### Type B:

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0">
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
     </StackLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfPopupLayout popupLayout;

        public MainPage()
        {
            InitializeComponent();
            popupLayout = new SfPopupLayout();
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            // Shows SfPopupLayout at the center of the view.
            popupLayout.Show(layout);
        }
    }
}
{% endhighlight %}

If we run the above sample, the below output will appear on iOS device as shown below.
![](GettingStarted_images/NuGetInstall.png)

#### SfPopupLayout.Show(x-position, y-position)

In the below code example we have open the SfPopupLayout by using `SfPopupLayout.Show(x-position, y-position)`.

##### Type A:

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
<sfPopup:SfPopupLayout x:Name="popUpLayout">
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
     </StackLayout>
    </sfPopup:SfPopupLayout.Content>
  </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
           // Shows SfPopuplayout at x-position 100 and y position 100.
           popupLayout.Show(100, 100);
        }
    }
}
{% endhighlight %}

##### Type B:

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0">
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
     </StackLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfPopupLayout popupLayout;
        public MainPage()
        {
            InitializeComponent();
            popupLayout = new SfPopupLayout();
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
           // Shows SfPopuplayout at x-position 100 and y position 100.
           popupLayout.Show(100, 100, layout);
        }
    }
}
{% endhighlight %}

If we run the above sample, the below output will appear on iOS device as shown below.
![](GettingStarted_images/NuGetInstall.png)

#### SfPopupLayout.ShowAtTouchPoint()

In the below code example we have open the SfPopupLayout by using `SfPopupLayout.ShowAtTouchPoint()`.

##### Type A:

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
<sfPopup:SfPopupLayout x:Name="popUpLayout">
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
     </StackLayout>
    </sfPopup:SfPopupLayout.Content>
  </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            // Shows SfPopuplayout at the touch point.
            popupLayout.ShowAtTouchPoint();
        }
    }
}
{% endhighlight %}

N > SfPopupLayout.ShowAtTouchPoint() is not applicable for Type B.

If we run the above sample, the below output will appear on iOS device as shown below.
![](GettingStarted_images/NuGetInstall.png)

#### SfPopupLayout.ShowRelativeToView(View, RelativePosition)

In the below code example we have open the SfPopupLayout by using `SfPopupLayout.ShowRelativeToView(View, RelativePosition)`.

##### Type A:

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
<sfPopup:SfPopupLayout x:Name="popUpLayout">
   <sfPopup:SfPopupLayout.Content>
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
       <Label x:Name="label" IsVisible="true" Text="This is SfPopupLayout"/>
     </StackLayout>
    </sfPopup:SfPopupLayout.Content>
  </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
           // Shows SfPopupLayout at the bottom of the textview.
           popupLayout.ShowRelativeToView(textView, RelativePosition.AlignBottom);
        }
    }
}
{% endhighlight %}

##### Type B:

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage" 
             Padding="0,40,0,0">
     <StackLayout x:Name="layout">
       <Button x:Name="clickToShowPopup" Text="ClickToShowPopup" VerticalOptions="Start" HorizontalOptions="FillAndExpand" />
       <Label x:Name="label" IsVisible="true" Text="This is SfPopupLayout"/>
     </StackLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        SfPopupLayout popupLayout;
        public MainPage()
        {
            InitializeComponent();
            popupLayout = new SfPopupLayout();
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
        }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
           //Shows SfPopupLayout at the bottom of the textview.
           popupLayout.ShowRelativeToView(textView, RelativePosition.AlignBottom, layout);
        }
    }
}
{% endhighlight %}

This is how the final output will look like on iOS, Android and Windows Phone devices.
![](GettingStarted_images/NuGetInstall.png)

### AnimationMode

Built-in animations are available in SfPopupLayout, which is applied when the PopupView opens and closes in the screen.
SfPopupLayout has different animation modes as listed below.

<table>
<tr>
<th> Modes </th>
<th> Description </th>
</tr>
<tr>
<td> {{'[Zoom]()'| markdownify }} </td>
<td>  Zoom-out animation will be applied if the PopupView opens and zoom-in animation will be applied if the PopupView closes. This is the default AnimationMode</td>
</tr>
<tr>
<td> {{'[Fade]()'| markdownify }} </td>
<td>  Fade-out animation will be applied if the PopupView opens and Fade-in animation will be applied if the PopupView closes</td>
</tr>
<tr>
<td> {{'[SlideOnLeft]()'| markdownify }} </td>
<td>  PopupView will be animated from left-to-right, when it opens and it will be animated from right-to-left when the PopupView closes.</td>
</tr>
<tr>
<td> {{'[SlideOnTop]()'| markdownify }} </td>
<td>  PopupView will be animated from top-to-bottom, when it opens and it will be animated from bottom-to-top when the PopupView closes.</td>
</tr>
<tr>
<td> {{'[None]()'| markdownify }} </td>
<td>  Animation will not be applied.</td>
</tr>
</table>

N> Setting of AnimationMode is same for both TypeA and TypeB.

#### Zoom Animation

Zoom-out animation will be applied if the PopupView opens and Zoom-in animation will be applied if the PopupView closes.

{% highlight c# %}
//MainPage.cs

public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.PopupView.AnimationMode = AnimationMode.Zoom;
    ....
}
{% endhighlight %}

If we run the above sample with `AnimationMode` as `Zoom`, the output will look like on iOS, Android and Windows Phone devices as shown below.
![](GettingStarted_images/NuGetInstall.png)

#### Fade Animation

Fade-out animation will be applied if the PopupView opens and Fade-in animation will be applied if the PopupView closes

{% highlight c# %}
//MainPage.cs

public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.PopupView.AnimationMode = AnimationMode.Fade;
    ....
}
{% endhighlight %}

If we run the above sample with `AnimationMode` as `Fade`, the output will look like on iOS, Android and Windows Phone devices as shown below.
![](GettingStarted_images/NuGetInstall.png)

#### SlideOnLeft Animation

PopupView will be animated from left-to-right, when it opens and it will be animated from right-to-left when the PopupView closes.

{% highlight c# %}
//MainPage.cs

public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.PopupView.AnimationMode = AnimationMode.SlideOnLeft;
    ....
}
{% endhighlight %}

If we run the above sample with `AnimationMode` as `SlideOnLeft`, the output will look like on iOS, Android and Windows Phone devices as shown below.
![](GettingStarted_images/NuGetInstall.png)

#### SlideOnTop Animation

PopupView will be animated from top-to-bottom, when it opens and it will be animated from bottom-to-top when the PopupView closes.

{% highlight c# %}
//MainPage.cs

public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.PopupView.AnimationMode = AnimationMode.SlideOnTop;
    ....
}
{% endhighlight %}

If we run the above sample with `AnimationMode` as `SlideOnTop`, the output will look like on iOS, Android and Windows Phone devices as shown below.
![](GettingStarted_images/NuGetInstall.png)

#### None

Animation will not be applied.

{% highlight c# %}
//MainPage.cs

public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.PopupView.AnimationMode = AnimationMode.None;
    ....
}
{% endhighlight %}

If we run the above sample with `AnimationMode` as `None`, the output will look like on iOS, Android and Windows Phone devices as shown below.
![](GettingStarted_images/NuGetInstall.png)

### Sample link

You can download the source code of this sample [here]().