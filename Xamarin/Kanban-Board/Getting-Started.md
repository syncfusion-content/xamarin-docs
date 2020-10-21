---
layout: post
title: Getting Started for Essential Syncfusion Xamarin.Forms Kanban
description: Getting Started for Essential Syncfusion Xamarin.Forms Kanban to get overview for working with this control
platform: xamarin
control: Kanban
documentation: ug
---

# Getting Started for Essential Syncfusion Xamarin.Forms Kanban

This section provides a quick overview for working with Essential Kanban for Xamarin.Forms. It is an efficient way to visualize the workflow at each stage along its path to completion.

## Adding SfKanban reference

You can add SfKanban reference in one of the following methods:

**Method 1: Adding SfKanban reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add kanban to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfKanban](https://www.nuget.org/packages/Syncfusion.Xamarin.SfKanban/), and then install it.

![Adding SfKanban reference from NuGet](SfKanban_images/Adding SfKanban reference.png)

N> Install the same version of kanban NuGet in all the projects.

**Method 2: Adding SfKanban reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfKanban control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfKanban assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location : {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.SfKanban.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfKanban.Android.dll<br/>Syncfusion.SfKanban.XForms.Android.dll<br/>Syncfusion.SfKanban.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfKanban.iOS.dll<br/>Syncfusion.SfKanban.XForms.iOS.dll<br/>Syncfusion.SfKanban.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfKanban.UWP.dll<br/>Syncfusion.SfKanban.XForms.UWP.dll<br/>Syncfusion.SfKanban.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>


N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Launching an application on each platform with kanban

To use the kanban inside an application, each platform application requires some additional configurations. The configurations vary from platform to platform and are discussed in the following sections:

N> If you are adding the references from toolbox, below steps are not needed.

### iOS

To launch the kanban in iOS, call the `SfKanbanRenderer.Init()` method in the FinishedLaunching overridden method of the AppDelegate class after the Xamarin.Forms framework has been initialized and before the `LoadApplication` method is called as demonstrated in the following code sample.

{% highlight C# %} 

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    global::Xamarin.Forms.Forms.Init();
    SfKanbanRenderer.Init();
    LoadApplication(new App());
    return base.FinishedLaunching(app, options);
} 

{% endhighlight %}


### Universal Windows Platform (UWP)

To deploy the kanban in `Release` mode, initialize the kanban assemblies in the App.xaml.cs file in the UWP project as demonstrated in the following code samples.

{% highlight C# %} 

// In App.xaml.cs 
protected override void OnLaunched(LaunchActivatedEventArgs e)
{ 
   … 
   if (rootFrame == null) 
   { 
      List<Assembly> assembliesToInclude = new List<Assembly>();
      assembliesToInclude.Add(typeof(SfKanbanRenderer).GetTypeInfo().Assembly);
      Xamarin.Forms.Forms.Init(e, assembliesToInclude);
   } 
   … 
}

{% endhighlight %}

### Android

Android platform does not require any additional configuration to render the kanban control.


## Initialize Kanban

Import ['SfKanban'](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html) namespace as shown below in your respective page,

{% tabs %}

{% highlight xaml %}

xmlns:kanban="clr-namespace:Syncfusion.SfKanban.XForms;assembly=Syncfusion.SfKanban.XForms"  

{% endhighlight %}
{% highlight C# %} 
using Syncfusion.SfKanban.XForms;

{% endhighlight %}

{% endtabs %}

Create an instance of ['SfKanban'](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html) control and set to Content property of a Page.

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban>
</kanban:SfKanban>

{% endhighlight %}

{% highlight C# %}

SfKanban kanban = new SfKanban();
this.Content = kanban;

{% endhighlight %}

{% endtabs %}

## Initialize view model

Create a ViewModel class with a collection property to hold a collection of [`KanbanModel`](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanModel.html) instances as shown below. Each [`KanbanModel`](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanModel.html) instance represent a card in Kanban control.

{% highlight C# %}

public class ViewModel
{
	public ObservableCollection<KanbanModel> Cards { get; set; }
	public ViewModel()
	{
		Cards = new ObservableCollection<KanbanModel>();
		Cards.Add(new KanbanModel()
		{
			ID = 1,
			Title = "iOS - 1002",
			ImageURL = "People_Circle1.png",
			Category = "Open",
			Description = "Analyze customer requirements",
			ColorKey = "Red",
			Tags = new string[] { "Incident", "Customer" }
		});
		Cards.Add(new KanbanModel()
		{
			ID = 6,
			Title = "Xamarin - 4576",
			ImageURL = "People_Circle2.png",
			Category = "Open",
			Description = "Show the retrieved data from the server in grid control",
			ColorKey = "Green",
			Tags = new string[] { "Story", "Customer" }
		});
		Cards.Add(new KanbanModel()
		{
			ID = 13,
			Title = "UWP - 13",
			ImageURL = "People_Circle3.png",
			Category = "In Progress",
			Description = "Add responsive support to application",
			ColorKey = "Brown",
			Tags = new string[] { "Story", "Customer" }
		});
		Cards.Add(new KanbanModel()
		{
			ID = 2543,
			Title = "People_Circle4.png",
			Category = "Code Review",
			ImageURL = "Image3.png",
			Description = "Check login page validation",
			ColorKey = "Brown",
			Tags = new string[] { "Story", "Customer" }
		});
	}
}

{% endhighlight %}

Set the `ViewModel` instance as the `BindingContext` of your Page; this is done to bind properties of `ViewModel` to [`SfKanban`](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html).

N> Add namespace of ViewModel class in your XAML page if you prefer to set BindingContext in XAML.

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
		xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
		x:Class="GettingStartedKanban.MainPage" 
		xmlns:kanban="clr-namespace:Syncfusion.SfKanban.XForms;assembly=Syncfusion.SfKanban.XForms"  
		xmlns:local="clr-namespace:GettingStartedKanban"> 
	<ContentPage.BindingContext>
		<local:ViewModel>
		</local:ViewModel>   
	</ContentPage.BindingContext>
</ContentPage>

{% endhighlight %}

{% highlight C# %}

this.BindingContext = new ViewModel();

{% endhighlight %}

{% endtabs %}

## Binding data to SfKanban

Bind the above data to [`SfKanban`](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html) using [`ItemsSource`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html#Syncfusion_SfKanban_XForms_SfKanban_ItemsSource) property.

{% tabs %}

{% highlight xaml %}

<kanban:SfKanban ItemsSource="{Binding Cards}">
</kanban:SfKanban>

{% endhighlight %}

{% highlight C# %}

kanban.SetBinding(SfKanban.ItemsSourceProperty, "Cards");

{% endhighlight %}

{% endtabs %}

## Defining columns

The columns are generated automatically based on the distinct values of ['KanbanModel.Category'](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanModel.html#Syncfusion_SfKanban_XForms_KanbanModel_Category) from ['ItemsSource'](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html#Syncfusion_SfKanban_XForms_SfKanban_ItemsSource). But, you can also define the columns by setting ['AutoGenerateColumns'](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html#Syncfusion_SfKanban_XForms_SfKanban_AutoGenerateColumns) property to false and adding ['KanbanColumn'](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanColumn.html) instance to ['Columns'](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html#Syncfusion_SfKanban_XForms_SfKanban_Columns) property of ['SfKanban'](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.SfKanban.html).
{% tabs %}

{% highlight xaml %}

<kanban:SfKanban x:Name="kanban" AutoGenerateColumns="False" HorizontalOptions="FillAndExpand" VerticalOptions="FillAndExpand" ItemsSource="{Binding Cards}">

	<kanban:SfKanban.Columns>

		<kanban:KanbanColumn x:Name="openColumn" Title="To Do"  >
		</kanban:KanbanColumn>

		<kanban:KanbanColumn x:Name="progressColumn" Title="In Progress">
		</kanban:KanbanColumn>

		<kanban:KanbanColumn x:Name="codeColumn" Title="Code Review" >
		</kanban:KanbanColumn>

		<kanban:KanbanColumn x:Name="doneColumn" Title="Done"  >
		</kanban:KanbanColumn> 

	</kanban:SfKanban.Columns>

</kanban:SfKanban> 

{% endhighlight %}

{% highlight C# %}

kanban.AutoGenerateColumns = false; 
kanban.SetBinding(SfKanban.ItemsSourceProperty, "Cards");

KanbanColumn openColumn = new KanbanColumn();
openColumn.Title = "Open";
kanban.Columns.Add(openColumn);

KanbanColumn progressColumn = new KanbanColumn();
progressColumn.Title = "In Progress";
kanban.Columns.Add(progressColumn);

KanbanColumn codeColumn = new KanbanColumn();
codeColumn.Title = "Code Review";
kanban.Columns.Add(codeColumn);

KanbanColumn doneColumn = new KanbanColumn();
doneColumn.Title = "Done";
kanban.Columns.Add(doneColumn);

{% endhighlight %}

{% endtabs %}

Define the categories of column using [`Categories`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanColumn.html#Syncfusion_SfKanban_XForms_KanbanColumn_Categories) property of [`KanbanColumn`](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfKanban.XForms.KanbanColumn.html) and cards will be added to the respective columns.

{% highlight C# %}

openColumn.Categories = new List<object>() { "Open" };
progressColumn.Categories = new List<object>() { "In Progress" };
codeColumn.Categories = new List<object>() { "Code Review" };
doneColumn.Categories = new List<object>() { "Done" };

{% endhighlight %}

This is how the final output will look like on iOS, Android and Windows devices. You can download the entire source code of this demo from [here](https://github.com/SyncfusionExamples/Getting-started-sample-in-kanban-in-Xamarin).

![Final output of SfKanban](SfKanban_images/SfKanban-gettingstartedImage.jpg)

## See also

[How to resolve SfKanban not rendering issue in iOS and UWP](https://www.syncfusion.com/kb/7171/how-to-resolve-sfkanban-not-rendering-issue-in-ios-and-uwp)

[How to make Syncfusion Xamarin.Forms SfKanban to work in UWP in release mode when .NET Native tool chain is enabled](https://www.syncfusion.com/kb/7170/how-to-make-syncfusion-xamarin-forms-sfkanban-to-work-in-uwp-in-release-mode-when-net)
