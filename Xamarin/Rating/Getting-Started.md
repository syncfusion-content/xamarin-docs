---

layout: post
title: Getting Started with Syncfusion SfRating control for Xamarin.Forms
description: A quick tour to initial users of Syncfusion Rating control(Xamarin.Forms) on how to create a simple rating view, set number,value and precision of rating items.
platform: Xamarin
control: Rating
documentation: ug

---

# Getting Started with Xamarin Rating(SfRating)


This section explains how to configure a SfRating control in a real-time scenario and also provides a walk-through on some of the customization features available in SfRating control.

## Adding SfRating reference

You can add SfRating reference using one of the following methods:

**Method 1: Adding SfRating reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfRating to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfRating](https://www.nuget.org/packages/Syncfusion.Xamarin.SfRating), and then install it.

![Adding SfRating reference from nuget](images/Adding SfRating reference.png)

N> Install the same version of SfRating NuGet in all the projects.

**Method 2: Adding SfRating reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfRating control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfRating assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.SfRating.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfRating.Android.dll<br/>Syncfusion.SfRating.XForms.Android.dll<br/>Syncfusion.SfRating.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfRating.iOS.dll<br/>Syncfusion.SfRating.XForms.iOS.dll<br/>Syncfusion.SfRating.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfInput.UWP.dll<br/>Syncfusion.SfShared.UWP.dll<br/>Syncfusion.SfRating.XForms.UWP.dll<br/>Syncfusion.SfRating.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.

N> Currently an additional step is required for iOS project. You need to create an instance of the rating custom renderer. If you are adding the references from toolbox, this step is not needed.



### Additional step for iOS

To launch [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) in iOS, call `SfRatingRenderer.Init()` in the `FinishedLaunching` overridden method of the `AppDelegate` class in iOS Project as demonstrated in the following code example.

{% tabs %}
{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    global::Xamarin.Forms.Forms.Init();
    LoadApplication(new App());
    Syncfusion.SfRating.XForms.iOS.SfRatingRenderer.Init();
    return base.FinishedLaunching(app, options);
}
{% endhighlight %}
{% endtabs %}



### Additional step for UWP

This step is required only if the application is deployed in Release mode with .NET native tool chain enabled. It is needed for resolving the known Framework issue “Custom controls not rendering in Release mode” in UWP platform. Initializing the [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) assembly at the `OnLaunched` overridden method of the `App` class in UWP project is the suggested work around. The following code example demonstrates initializing the [`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) assembly.


{% tabs %}
{% highlight c# %}
protected override void OnLaunched(LaunchActivatedEventArgs e)
{
    ..... 
    rootFrame.NavigationFailed += OnNavigationFailed;
    // Add `using System.Reflection;` 
    List<Assembly> assembliesToInclude = new List<Assembly>();
	
    //Now, add all the assemblies that your app uses 
    assembliesToInclude.Add(typeof(SfRatingRenderer).GetTypeInfo().Assembly);
	
    // replaces Xamarin.Forms.Forms.Init(e);
    Xamarin.Forms.Forms.Init(e, assembliesToInclude);
    ..... 
}
{% endhighlight %}
{% endtabs %}

The SfRating control is configured entirely in C# code or by using XAML markup. The following steps explains how to create a SfRating and configure its elements.

## Adding namespace

Add the following namespace.

{% tabs %}

{% highlight xaml %}

	<xmlns:rating="clr-namespace:Syncfusion.SfRating.XForms;assembly=Syncfusion.SfRating.XForms"/>

{% endhighlight %}

{% highlight c# %}

	using Syncfusion.SfRating.XForms;

{% endhighlight %}

{% endtabs %}

## Initialize Rating

Now, add the SfRating control with a required optimal name using the included namespace.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" />
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainPage()
{
    InitializeComponent();
    rating = new SfRating();
    this.Content = rating;
} 

{% endhighlight %}

{% endtabs %}

## Set Number of Rating Items

The number of rating items to be displayed can be customized in the SfRating control. Users can create a rating application with 5 items as follows. The `ItemCount` property is used to define the number of rating items.

N> The default value of ItemCount is 5.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating ItemCount="5" />
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainPage()
{
    InitializeComponent();
    rating = new SfRating();
    rating.ItemCount = 5;
}

{% endhighlight %}

{% endtabs %}

## Set Value

The display value can be set in the SfRating control, which is selected among the items. The following code example shows the display value of 3 with 5 rating items. The `Value` property is used to set display value.

N> The default value of this property is 0.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating Value="3" />
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainPage()
{
    InitializeComponent();
    rating = new SfRating();
    rating.Value = 3;
}

{% endhighlight %}

{% endtabs %}

## Precision

The SfRating control provides an option to rate the items in full, half, and exact values. This can be set using the `Precision` property. By default, the precision mode is `Standard`.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating Precision="Standard" />
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainPage()
{
    InitializeComponent();
    rating = new SfRating();
    rating.Precision = Precision.Standard;
}

{% endhighlight%}

{% endtabs %}

![SfRating Getting Started ](images/gettingstarted.png)

The complete Getting Started sample is available in this [documentation](http://www.syncfusion.com/downloads/support/directtrac/general/ze/SfRating_GettingStarted419194381.zip).
