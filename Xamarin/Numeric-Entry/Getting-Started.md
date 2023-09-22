---
layout: post
title: Getting Started with Xamarin Numeric Entry control | Syncfusion
description: Learn here about getting started with Syncfusion Xamarin Numeric Entry (SfNumericTextBox) control, its elements and more.
platform: xamarin
control: SfNumericTextBox
documentation: ug
---

# Getting Started with Xamarin Numeric Entry (SfNumericTextBox)

This section explains you the steps to configure a SfNumericTextBox control in a real-time scenario and also provides a walk-through on some of the customization features available in SfNumericTextBox control.

## Assembly deployment

After installing [Essential Studio for Xamarin](https://www.syncfusion.com/downloads/xamarin), you can find all the required assemblies in the installation folders, {Syncfusion Essential Studio Installed location} \Essential Studio\\{Version #}\Xamarin\lib.

E.g.: C:\Program Files (x86) \Syncfusion\Essential Studio\19.1.0.54\Xamarin\lib

N> Assemblies can be found in unzipped package location(Documents/Syncfusion/{Version #}/Xamarin/lib) in Mac.

## Adding SfNumericTextBox reference

You can add SfNumericTextBox reference using one of the following methods:

**Method 1: Adding SfNumericTextBox reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org). To add SfNumericTextBox to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfNumericTextBox](https://www.nuget.org/packages/Syncfusion.Xamarin.SfNumericTextBox), and then install it.

![Adding SfNumericTextBox reference from NuGet](images/Adding SfNumericTextBox reference.png)

N> Install the same version of SfNumericTextBox NuGet in all the projects.

**Method 2: Adding SfNumericTextBox reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfNumericTextBox control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfNumericTextBox assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.SfNumericTextBox.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfNumericTextBox.Android.dll<br/>Syncfusion.SfNumericTextBox.XForms.Android.dll<br/>Syncfusion.SfNumericTextBox.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfNumericTextBox.iOS.dll<br/>Syncfusion.SfNumericTextBox.XForms.iOS.dll<br/>Syncfusion.SfNumericTextBox.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfInput.UWP.dll<br/>Syncfusion.SfShared.UWP.dll<br/>Syncfusion.SfNumericTextBox.XForms.UWP.dll<br/>Syncfusion.SfNumericTextBox.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/installation/mac-installer/how-to-download) and [Windows](https://help.syncfusion.com/xamarin/installation/web-installer/how-to-download).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/overview) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Launching the SfNumericTextBox on each platform

To use SfNumericTextBox inside an application, each platform application must initialize the SfNumericTextBox renderer. This initialization step varies from platform to platform and is discussed in the following sections.

N> If you are adding the references from toolbox, below steps are not needed.

### Android and  UWP

The Android and UWP launches the SfNumericTextBox without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application

### iOS

To launch SfNumericTextBox in iOS, need to create an instance of SfNumericTextBoxRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below.


{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
	global::Xamarin.Forms.Forms.Init();

	new SfNumericTextBoxRenderer();

	LoadApplication(new App());

	return base.FinishedLaunching(app, options);
}

{% endhighlight %}


### ReleaseMode issue in UWP platform

There is a known Framework issue in UWP platform. The custom controls will not render when deployed the application in Release Mode.

The above problem can be resolved by initializing the SfNumericTextBox assemblies in Main.xaml.cs in UWP project as like in below code snippet.


{% highlight C# %}

// In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)
{
…

	rootFrame.NavigationFailed += OnNavigationFailed;
		
	// you'll need to add `using System.Reflection;`
	List<Assembly> assembliesToInclude = new List<Assembly>();

	//Now, add all the assemblies your app uses
	assembliesToInclude.Add(typeof(SfNumericTextBoxRenderer).GetTypeInfo().Assembly);

	// replaces Xamarin.Forms.Forms.Init(e);        
	Xamarin.Forms.Forms.Init(e, assembliesToInclude);
		
…     

{% endhighlight %}


## Create a simple SfNumericTextBox 

The [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) control is configured entirely in C# code or by using XAML markup. 

The following steps explain how to create a [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) and configure its elements,

* Adding namespace for the added assemblies. 

{% capture codesnippet1 %}

{% tabs %}

{% highlight xaml %}

	xmlns:syncfusion="clr-namespace:Syncfusion.SfNumericTextBox.XForms;assembly=Syncfusion.SfNumericTextBox.XForms"

{% endhighlight %}

{% highlight C# %}

	using Syncfusion.SfNumericTextBox.XForms;

{% endhighlight %}

{% endtabs %}

{% endcapture %}

{{ codesnippet1 | UnOrderList_Indent_Level_1 }} 

* Now, add the [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) control with a required optimal name by using the included namespace.

{% capture codesnippet2 %}

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" xmlns:local="clr-namespace:GettingStarted" 
		xmlns:syncfusion="clr-namespace:Syncfusion.SfNumericTextBox.XForms;assembly=Syncfusion.SfNumericTextBox.XForms"
		x:Class="GettingStarted.NumericControlPage">
  <ContentPage.Content>
     <syncfusion:SfNumericTextBox />	
	</ContentPage.Content>
	
</ContentPage>

{% endhighlight %}

{% highlight C# %}


using Syncfusion.SfNumericTextBox.XForms;
using Xamarin.Forms;

namespace GettingStarted
{
public partial class NumericControlPage : ContentPage
    {
        public NumericControlPage()
        {
            InitializeComponent();

            SfNumericTextBox numericTextBox = new SfNumericTextBox();
            this.Content = numericTextBox;
        }
    }
}

{% endhighlight %}

{% endtabs %}

{% endcapture %}

{{ codesnippet2 | UnOrderList_Indent_Level_1 }} 

![Xamarin.Forms Numeric TextBox](images/numericTextBox.PNG)

## Set the value in SfNumericTextBox

[`Value`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_Value) property is used to set and read the value presented by the [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html). 

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox Value="123.45" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.Value = 123.45;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Xamarin.Forms Numeric TextBox with value](images/value.png)

You can find the complete getting started sample from this [link.](https://github.com/SyncfusionExamples/Getting-Started-Xamarin-Textbox)

## See also

[How to disable the clear button in SfNumericTextBox](https://support.syncfusion.com/kb/article/10319/how-to-disable-the-clear-button-in-numeric-textbox-in-xamarin-forms)

[How to change the SfNumericTextBox style using its visual states](https://support.syncfusion.com/kb/article/10286/how-to-change-the-xamarin-forms-numeric-textbox-style-using-its-visual-states)

[How to define and apply a common style for SfNumericTextBox](https://support.syncfusion.com/kb/article/10232/how-to-define-and-apply-a-common-style-for-sfnumerictextbox-in-xamarin-forms)

[How to resolve the issue with decimal point and minus key on Samsung devices in SfNumericTextBox](https://support.syncfusion.com/kb/article/8944/how-to-resolve-the-issue-with-decimal-point-and-minus-key-on-samsung-devices-in) 

[How to create SfNumericTextBox sample in Xamarin.Forms.Android platform](https://support.syncfusion.com/kb/article/6863/how-to-create-numerictextbox-sample-in-xamarin-forms-android-platform)

[How to create a SfNumericTextBox control sample using Xaml](https://support.syncfusion.com/kb/article/6861/how-to-create-a-numerictextbox-control-sample-using-xaml)

[How to create SfNumericTextBox sample in Xamarin.Forms.UWP platform](https://support.syncfusion.com/kb/article/6842/how-to-create-numerictextbox-sample-in-xamarinforms-platform)

[How to create SfNumericTextBox sample in Xamarin.Forms.iOS platform](https://support.syncfusion.com/kb/article/6844/how-to-create-numerictextbox-sample-in-xamarin-forms-ios-platform)

[How to bind the values of SfNumericTextBox with an Entry control in Xamarin.Forms](https://support.syncfusion.com/kb/article/6847/how-to-bind-the-values-of-numerictextbox-with-an-entry-control-in-xamarin-forms)

[How to bind two SfNumericTextBox in Xamarin.Forms](https://support.syncfusion.com/kb/article/6853/how-to-bind-two-numerictextboxes-in-xamarin-forms)

[What are the assemblies needed for SfNumericTextBox and how to add reference](https://support.syncfusion.com/kb/article/6854/what-are-the-assemblies-needed-for-numerictextbox-and-how-to-add-reference)

[How to bind value in SfNumericTextBox](https://support.syncfusion.com/kb/article/6304/how-to-bind-value-in-xamarin-forms-numerictextbox)
