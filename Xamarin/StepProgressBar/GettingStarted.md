---
layout: post
title: Getting Started for Syncfusion Xamarin.Forms StepProgressBar
description: A quick tour to initial users on Syncfusion StepProgressBar control for Xamarin.Forms platform.
platform: xamarin
control: StepProgressBar
documentation: ug
---

# Getting Started

This section explains the steps required to work with the StepProgressBar control for Xamarin.Forms.

## Adding SfStepProgressBar reference

You can add SfStepProgressBar reference using one of the following methods:

**Method 1: Adding SfStepProgressBar reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfStepProgressBar to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfProgressBar](https://www.nuget.org/packages/Syncfusion.Xamarin.SfProgressBar), and then install it.

![Adding SfStepProgressBar reference from NuGet](overview_images/Adding SfStepProgressBar reference.png)

N> Install the same version of SfProgressBar NuGet in all the projects.

**Method 2: Adding SfStepProgressBar reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the StepProgressBar control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfStepProgressBar assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from the NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.SfProgressBar.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfProgressBar.XForms.Android.dll<br/>Syncfusion.SfProgressBar.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfProgressBar.XForms.iOS.dll<br/>Syncfusion.SfProgressBar.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfProgressBar.XForms.UWP.dll<br/>Syncfusion.SfProgressBar.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To learn more about obtaining Syncfusion components, refer to [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Refer the [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to learn about registering Syncfusion license key in your Xamarin application to use Syncfusion components.

## Launching the application on each platform with StepProgressBar

To use the StepProgressBar in an application, each platform requires some additional configurations. The configurations vary from platform to platform and is discussed in the following sections:

N> If you are adding the references from toolbox, this step is not required.

### iOS

To launch the StepProgressBar in iOS, call the 'SfLinearProgressBarRenderer.Init()' and 'SfBorderRenderer.Init()' in the FinishedLaunching overridden method of the AppDelegate class after the Xamarin.Forms framework has been initialized and before the LoadApplication is called as demonstrated in the following code sample.

{% highlight C# %} 

public override bool FinishedLaunching(UIApplication app, NSDictionary options) 
{ 
    … 
    global::Xamarin.Forms.Forms.Init();

    // Add the below line for using SfLinearProgressBar.
    Syncfusion.XForms.iOS.ProgressBar.SfLinearProgressBarRenderer.Init();

    // Add the below line for using SfBorder.
    Syncfusion.XForms.iOS.Border.SfBorderRenderer.Init();

    LoadApplication(new App()); 
    …
}

{% endhighlight %}

### Universal Windows Platform (UWP)

To launch the StepProgressBar in UWP, initialize the progress bar assemblies in App.xaml.cs in UWP project as demonstrated in the following code samples. This is required to deploy the application with progress bar in `Release` mode in UWP platform.

{% highlight C# %} 

// In App.xaml.cs 
protected override void OnLaunched(LaunchActivatedEventArgs e)
{ 
   … 
   if (rootFrame == null) 
   { 
      List<Assembly> assembliesToInclude = new List<Assembly>();

      // Add the below line for using SfLinearProgressBar.
      assembliesToInclude.Add(typeof(Syncfusion.XForms.UWP.ProgressBar.SfLinearProgressRenderer).GetTypeInfo().Assembly);

      // Add the below line for using SfBorder.
      assembliesToInclude.Add(typeof(Syncfusion.XForms.UWP.Border.SfBorderRenderer).GetTypeInfo().Assembly);

      Xamarin.Forms.Forms.Init(e, assembliesToInclude); 
   } 
… 
}


{% endhighlight %}

### Android

The Android platform does not require any additional configuration to render the StepProgressBar.


## Initializing the StepProgressBar

Import the progress bar namespace as demonstrated in the following code sample in your respective page.

{% tabs %} 

{% highlight xaml %} 
xmlns:progressBar="clr-namespace:Syncfusion.XForms.ProgressBar;assembly=Syncfusion.SfProgressBar.XForms"

{% endhighlight %}

{% highlight C# %} 

using Syncfusion.XForms.ProgressBar;

{% endhighlight %}

{% endtabs %} 

Then, initialize the SfStepProgressBar as shown in the following code:

{% tabs %} 

{% highlight xaml %} 

<Grid>
    <progressBar:SfStepProgressBar HorizontalOptions="Center" VerticalOptions="Center">
        <progressBar:StepView PrimaryText="Step 1" />
        <progressBar:StepView PrimaryText="Step 2" />
        <progressBar:StepView PrimaryText="Step 3" />
		<progressBar:StepView PrimaryText="Step 4" Status="InProgress" />
        <progressBar:StepView PrimaryText="Step 5" />
    </progressBar:SfStepProgressBar>        
</Grid>

{% endhighlight %}

{% highlight C# %} 

public MainPage()
{
    InitializeComponent();

    Grid mainGrid = new Grid();

    // Create StepProgressBar control
    SfStepProgressBar stepProgressBar = new SfStepProgressBar();
    stepProgressBar.VerticalOptions = LayoutOptions.Center;
    stepProgressBar.HorizontalOptions = LayoutOptions.Center;

    stepProgressBar.Children.Add(new StepView() { PrimaryText = "Step 1" });
    stepProgressBar.Children.Add(new StepView() { PrimaryText = "Step 2" });
    stepProgressBar.Children.Add(new StepView() { PrimaryText = "Step 3" });
	stepProgressBar.Children.Add(new StepView() { PrimaryText = "Step 4", Status = StepStatus.InProgress });
    stepProgressBar.Children.Add(new StepView() { PrimaryText = "Step 5" });

    mainGrid.Children.Add(stepProgressBar);
    this.Content = mainGrid;

}

{% endhighlight %}

{% endtabs %} 

The complete Getting Started sample is available in this [link](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStarted1163813960).