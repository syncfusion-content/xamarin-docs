---
layout: post
title: Getting Started with Syncfusion NumericTextBox for Xamarin.Forms
description: A quick tour to initial users on Syncfusion NumericTextBox control for Xamarin.Forms platform
platform: Xamarin
control: NumericTextBox
documentation: ug
---

# Getting Started

This section explains you the steps to configure a SfNumericTextBox control in a real-time scenario and also provides a walk-through on some of the customization features available in SfNumericTextBox control.

## Adding SfNumericTextBox reference

You can add SfNumericTextBox reference using one of the following methods:

**Method 1: Adding SfNumericTextBox reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfNumericTextBox to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfNumericTextBox](https://www.nuget.org/packages/Syncfusion.Xamarin.SfNumericTextBox), and then install it.

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

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Launching the SfNumericTextBox on each platform

To use SfNumericTextBox inside an application, each platform application must initialize the SfNumericTextBox renderer. This initialization step varies from platform to platform and is discussed in the following sections.

### Android and  UWP

The Android and UWP launches the SfNumericTextBox without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application

N> If you are adding the references from toolbox, this step is not needed.

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


## Create a Simple SfNumericTextBox 

The SfNumericTextBox control is configured entirely in C# code or by using XAML markup. The following steps explain on how to create a SfNumericTextBox and configure its elements,

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight xaml %}

	xmlns:syncfusion="clr-namespace:Syncfusion.SfNumericTextBox.XForms;assembly=Syncfusion.SfNumericTextBox.XForms"

{% endhighlight %}

{% highlight C# %}

	using Syncfusion.SfNumericTextBox.XForms;

{% endhighlight %}

{% endtabs %}

* Now add the SfNumericTextBox control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" xmlns:local="clr-namespace:GettingStarted" 
		xmlns:syncfusion="clr-namespace:Syncfusion.SfNumericTextBox.XForms;assembly=Syncfusion.SfNumericTextBox.XForms"
		x:Class="GettingStarted.NumericControlPage">
  <ContentPage.Content>
     <syncfusion:SfNumericTextBox x:Name="numericTextBox" />	
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

## Display Customization

### Setting and Reading Value

`Value` property is used to set and read the value presented by the SfNumericTextBox. 

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" Value="123.45" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.Value = 123.45;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Xamarin.Forms Numeric TextBox with value](images/value.png)

### Parsing the Value

Value of the SfNumericTextBox gets parsed based on `ParserMode` property. ParsingMode is of type Parsers which is enum of Double and Decimal. Hence we have option to display the value in double or decimal. 

Following code shows the Decimal parsing mode which can be set through `ParserMode` property.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" Value="123.45" ParserMode="Decimal" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.ParserMode=Parsers.Decimal;
numericTextBox.Value = 123.45;
this.Content = numericTextBox;
	
{% endhighlight %}

{% endtabs %}

![NumericTextBox with parsed value image](images/value.png)

N> DefaultValue for ParserMode is Double.
 
### Formatting the Value

The `FormatString` property determines the format specifier by which the display text has to be formatted.

{% tabs %}

{% highlight xaml %}


	<syncfusion:SfNumericTextBox x:Name="numericTextBox" Value="100" FormatString="c" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.FormatString = "c";
numericTextBox.Value = 100;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

N> The control displays the formatted text on lost focus. Default Value of `FormatString` is "n".

![Xamarin.Forms Numeric TextBox with formatted value](images/formatstring.png)

### Colors

SfNumericTextBox can be set to use a custom background,text and border colors via the following bindable properties:

* `TextColor` - sets the color of the NumericTextBox's value.

* `BackgroundColor` - sets the background color of NumericTextBox's frame.

* `BorderColor` - sets the border custom color of NumericTextBox

* `WatermarkColor` - sets the watermark custom color of NumericTextBox's watermark Text.

#### TextColor

To set the TextColor color in XAML as well as in C#:

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" Value="123" TextColor="Green" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.TextColor = Color.Green;
numericTextBox.Value = 123;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Xamarin.Forms Numeric TextBox with text color customization](images/textcolor.png)

#### BackgroundColor

To set the BackgroundColor color in XAML as well as in C#:

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" Value="123" BackgroundColor="Maroon" TextColor="White"/>
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.BackgroundColor = Color.Maroon;
numericTextBox.TextColor = Color.White;
numericTextBox.Value = 123;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Xamarin.Forms Numeric TextBox with background color customization](images/backgroundcolor.png)

#### BorderColor

To set the BorderColor color in XAML as well as in C#:

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" Value="123" BorderColor="Red" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.BorderColor = Color.Red;
numericTextBox.Value = 123;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Xamarin.Forms Numeric TextBox with border color customization](images/bordercolor.png)

#### WatermarkColor

To set the WatermarkColor color in XAML as well as in C#:

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox  x:Name="numericTextBox" AllowNull="true" Value="123" WatermarkColor="Blue" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.WatermarkColor = Color.Blue;
numericTextBox.Value = 123;
numericTextBox.AllowNull=true;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Xamarin.Forms Numeric TextBox with watermark color customization](images/watermarkcolor.png)

### Font Settings

NumericTextBox has the following two font-related properties that display the value's text:
We can customize the font style of NumericTextBox by using the following properties.

* `FontSize` : set the font size for NumericTextBox’s text. Default value is 20.

* `FontAttributes` : set the style of NumericTextBox’s text. We can give three types of style on it.It is specifying style information like Italic and Bold (using the FontAttributes enumeration in C#)

1. Bold- The font is bold
2. Italic – The font is Italic
3. None – The font is unmodified.

N> Default value is None.

* `TextAlignment` : set the style of NumericTextBox’s text. We can give three types of style on it.It is specifying style information like Start,End and Center (using the TextAlignment enumeration in C#)

N> Default value is Start.

To set the font size and attributes in XAML as well as in C#:

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" FontSize="25" FontAttributes="Bold" Value="123" TextAlignment="Center" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.FontSize = 27;
numericTextBox.Value = 123;
numericTextBox.TextAlignment=TextAlignment.Center;
numericTextBox.FontAttributes = FontAttributes.Bold;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Xamarin.Forms Numeric TextBox with custom font attributes](images/textformat.png)

You can find the complete getting started sample from this [link.](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStarted1977385538.zip)