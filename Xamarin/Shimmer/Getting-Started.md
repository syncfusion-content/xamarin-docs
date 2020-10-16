---
layout: post
title: Getting Started with Syncfusion Shimmer
description: How to add shimmer reference, launch an application on each platform with SfShimmer, initialize and load shimmer content.
platform: xamarin
control: SfShimmer
documentation: ug
---

# Getting Started with Xamarin Shimmer (SfShimmer)

This section explains the steps required to configure the shimmer.

## Adding SfShimmer reference

You can add SfShimmer reference using one of the following methods:

**Method 1: Adding SfShimmer reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfShimmer to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.Core](https://www.nuget.org/packages/Syncfusion.Xamarin.Core), and then install it.

![Add Packages](Getting-Started_images/Reference.png)

**Method 2: Adding SfShimmer reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfShimmer control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfShimmer assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location : {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you will have to include a license key in your projects. Refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to learn about registering Syncfusion license key in your Xamarin application to use our components.

## Launching an application on each platform with SfShimmer

To use the shimmer inside an application, each platform application requires some additional configurations. The configurations vary from platform to platform and are discussed in the following sections:

N> If you are adding the references from toolbox, the following steps are not needed.

### iOS

To launch the shimmer in iOS, call the `SfShimmerRenderer.Init()` method in the FinishedLaunching overridden method of the AppDelegate class after the Xamarin.Forms framework has been initialized and before the `LoadApplication` method is called as demonstrated in the following code sample.

{% highlight C# %} 

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    global::Xamarin.Forms.Forms.Init();
    SfShimmerRenderer.Init();
    LoadApplication(new App());
    return base.FinishedLaunching(app, options);
} 

{% endhighlight %}

### Universal Windows Platform (UWP)

To deploy the shimmer in `Release` mode, initialize the core assemblies in the App.xaml.cs file in the UWP project as demonstrated in the following code samples.

{% highlight C# %} 

// In App.xaml.cs 
protected override void OnLaunched(LaunchActivatedEventArgs e)
{ 
   … 
   if (rootFrame == null) 
   { 
      List<Assembly> assembliesToInclude = new List<Assembly>();
      assembliesToInclude.Add(typeof(Syncfusion.XForms.UWP.Shimmer.SfShimmerRenderer).GetTypeInfo().Assembly);
      Xamarin.Forms.Forms.Init(e, assembliesToInclude);
   } 
   … 
}

{% endhighlight %}

### Android

Android platform does not require any additional configuration to render the shimmer control.

## Initializing shimmer

Import the [`SfShimmer`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Shimmer.SfShimmer.html) control namespace in respective page as demonstrated in the following code sample.

{% tabs %} 

{% highlight xaml %} 

xmlns:shimmer="clr-namespace:Syncfusion.XForms.Shimmer;assembly=Syncfusion.Core.XForms"

{% endhighlight %}

{% highlight C# %} 

using Syncfusion.XForms.Shimmer; 

{% endhighlight %}

{% endtabs %}

Then initialize shimmer as shown below,

{% tabs %} 

{% highlight xaml %} 

<shimmer:SfShimmer x:Name="shimmer" VerticalOptions="Fill"
                           IsActive="{Binding IsActive}">
                        <shimmer:SfShimmer.Content>
                            <StackLayout>
                                <Label Text="Content is loaded!" HorizontalOptions="CenterAndExpand" VerticalOptions="CenterAndExpand"/>
                            </StackLayout>
                        </shimmer:SfShimmer.Content>
</shimmer:SfShimmer>

{% endhighlight %}

{% highlight C# %} 

SfShimmer shimmer = new SfShimmer();
shimmer.VerticalOptions = LayoutOptions.Fill;
shimmer.SetBinding(SfShimmer.IsActiveProperty, "IsActive");

var stackLayout = new StackLayout();

var label = new Label();
label.Text = "Content is loaded!";
label.HorizontalOptions = LayoutOptions.CenterAndExpand;
label.VerticalOptions = LayoutOptions.CenterAndExpand;

stackLayout.Children.Add(label);

shimmer.Content = stackLayout;

{% endhighlight %}

{% endtabs %}

![Shimmer with Persona type](Getting-Started_images/Persona.gif)

N> The SfShimmer has different shimmer types. The default shimmer type is `Persona`.

## Loading shimmer content

By disabling the [`IsActive`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Shimmer.SfShimmer.html#Syncfusion_XForms_Shimmer_SfShimmer_IsActive) property of [`SfShimmer`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Shimmer.SfShimmer.html), shimmer content is loaded.

{% tabs %} 

{% highlight xaml %} 

        <shimmer:SfShimmer x:Name="shimmer" VerticalOptions="FillAndExpand" IsActive ="false">
                <shimmer:SfShimmer.Content>
                     <StackLayout>
                        <Label Text="Content is loaded!"/>
                      </StackLayout>
                </shimmer:SfShimmer.Content>
        </shimmer:SfShimmer>

{% endhighlight %}

{% highlight C# %} 

            shimmer = new SfShimmer()
            {
                IsActive = false,
                VerticalOptions = LayoutOptions.FillAndExpand,
                Content = new Label
                {
                    Text = "Content is loaded!"
                }
            };
            this.Content = shimmer;

{% endhighlight %}

{% endtabs %}

## See also

[How to set the custom view in SfShimmer using style](https://www.syncfusion.com/kb/11851/how-to-set-the-custom-view-in-xamarin-forms-shimmer-using-style)
