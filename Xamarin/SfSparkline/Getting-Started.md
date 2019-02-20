---
layout: post
title: Getting Started for Essential Syncfusion.Xamarin.Forms Sparkline
description: How to create a sparkline, initialize view model, paopulate data in sparkline.
platform: xamarin
control: Sparkline
documentation: ug
---

# Getting Started

This section explains you the steps required to populate the Sparkline with data. 

## Adding SfSparkline reference

You can add SfSparkline reference using one of the following methods:

**Method 1: Adding SfSparkline reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfSparkline to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfSparkline](https://www.nuget.org/packages/Syncfusion.Xamarin.SfSparkline), and then install it.

![Adding SfSparkline reference from NuGet](Getting-Started-image/Adding SfSparkline reference.png)

N> Install the same version of SfSparkline NuGet in all the projects.

**Method 2: Adding SfSparkline reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfSparkline control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfSparkline assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.SfSparkline.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfSparkline.Android.dll<br/>Syncfusion.SfSparkline.XForms.Android.dll<br/>Syncfusion.SfSparkline.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfSparkline.iOS.dll<br/>Syncfusion.SfSparkline.XForms.iOS.dll<br/>Syncfusion.SfSparkline.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfSparkline.UWP.dll<br/>Syncfusion.SfSparkline.XForms.UWP.dll<br/>Syncfusion.SfSparkline.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.

N> After adding the reference, an additional step is required for iOS and UWP projects. You need to call Init method in the `SfSparklineRenderer` as shown in this [KB article](https://www.syncfusion.com/kb/7713). If you are adding the references from toolbox, this step is not needed.

N> For UWP alone, one more additional step is required if the project is built in release mode with .NET Native tool chain enabled. You can refer the [KB article](https://www.syncfusion.com/kb/7167) for more details.

## Initialize view model

Now, let us define a simple data model that represents a data point in [`SfSparkline`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfLineSparkline.html).

{% highlight c# %}
public class Model   
{   
    public double Performance { get; set; }
}
{% endhighlight %} 

Next, create a view model class and initialize a list of `Model` objects as shown below,

{% highlight c# %}
public class ViewModel  
{
      public List<Model> Data { get; set; }      

      public ViewModel()       
      {
            Data = new List<Model>()
            {
                new Model { Performance = 3000 },
                new Model { Performance = 5000 },
                new Model { Performance = -3000 },
                new Model { Performance = -4000 },
                new Model { Performance = 2000 },
                new Model { Performance = 3000 }
            }; 
       }
 }
{% endhighlight %} 

Set the `ViewModel` instance as the `BindingContext` of your Page; this is done to bind properties of `ViewModel` to [`SfSparkline`.](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfLineSparkline.html)
 
N> Add namespace of `ViewModel` class in your XAML page if you prefer to set `BindingContext` in XAML.

{% tabs %} 

{% highlight xaml %} 
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"

             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"

             x:Class=" SparklineDemo.MainPage"

             xmlns:sparkline="clr-namespace:Syncfusion.SfSparkline.XForms;assembly=Syncfusion.SfSparkline.XForms" 

             xmlns:local="clr-namespace:SparklineDemo">    

	<ContentPage.BindingContext>       

		<local:ViewModel></local:ViewModel>  

	</ContentPage.BindingContext>
 
</ContentPage>
{% endhighlight %}

{% highlight C# %} 
this.BindingContext = new ViewModel();
{% endhighlight %}

{% endtabs %} 

## Populate Sparkline with data

Import the [`SfSparkline`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfLineSparkline.html) namespace as shown below in your respective page,

{% tabs %}   

{% highlight xaml %}
xmlns:sparkline="clr-namespace:Syncfusion.SfSparkline.XForms;assembly=Syncfusion.SfSparkline.XForms"
{% endhighlight %}

{% highlight C# %}
using Syncfusion.SfSparkline.XForms;
{% endhighlight %}

{% endtabs %} 

Bind the Data property of the above `ViewModel` to the [`SfSparkline.ItemsSource`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfSparklineBase~ItemsSource.html) property as shown below.

N> You need to set [`YBindingPath`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfSparklineBase~YBindingPath.html) property, so that [`SfSparkline`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSparkline.XForms~Syncfusion.SfSparkline.XForms.SfLineSparkline.html) would fetch values from the respective property in the data model to plot the Sparkline.

{% tabs %}   

{% highlight xaml %}
<sparkline:SfLineSparkline ItemsSource="{Binding Data}" YBindingPath="Performance"> 

</sparkline:SfLineSparkline >
{% endhighlight %}

{% highlight C# %}
SfLineSparkline lineSparkline = new SfLineSparkline(); 

lineSparkline.YBindingPath = "Performance";

lineSparkline.SetBinding(SfSparklineBase.ItemsSourceProperty, "Data");
{% endhighlight %}

{% endtabs %} 

![Xamarin forms Sparkline getting started](Getting-Started-image/LineSparkline.png)

You can find the complete getting started sample from this [link.](http://www.syncfusion.com/downloads/support/directtrac/general/ze/SparkLineSample295325469)
