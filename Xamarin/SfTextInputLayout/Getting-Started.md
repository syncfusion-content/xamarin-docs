---
layout: post
title: Getting Started for Essential Xamarin.Forms Text Input Layout
description: How to create a text input layout and adds decorative elements.
platform: xamarin
control: SfTextInputLayout
documentation: ug
---

# Getting Started

This section explains the steps required to configure the text input layout control with floating label, leading and trailing icons, password visibility toggling icon, and assistive labels. This section covers only the minimal features needed to get started with the text input layout control.

## Adding text input layout reference

Syncfusion components for Xamarin.Forms are available in [nuget.org](https://www.nuget.org). To add the text input layout control to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.Core]((https://www.nuget.org/packages/Syncfusion.Xamarin.Core), and then install it.

![](Getting-Started_images/textInput_getting_img1.png)

To learn more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows).


N> Install the same version of the core NuGet in all the projects. The text input layout control will be available in core NuGet from v16.3.0.x onwards.

I> To start with v16.2.0.x, you have to include a license key in your project if you reference Syncfusion assemblies from the trial setup or NuGet feed. Please refer to this [documentation](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to learn about registering Syncfusion license key in your Xamarin applications and using our components.

## Launching an application on each platform with text input layout

To use the text input layout inside an application, each platform application requires some additional configurations. The configurations vary from platform to platform and are discussed in the following sections:

### iOS

To launch the text input layout in iOS, call the `SfTextInputLayoutRenderer.Init()` method in the FinishedLaunching overridden method of the AppDelegate class after the Xamarin.Forms framework has been initialized and before the `LoadApplication` method is called as demonstrated in the following code sample.


{% highlight C# %} 

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    global::Xamarin.Forms.Forms.Init();
    SfTextInputLayoutRenderer.Init();
    LoadApplication(new App());
    return base.FinishedLaunching(app, options);
} 

{% endhighlight %}


### Universal Windows Platform (UWP)

To deploy the text input layout in `Release` mode, initialize the core assemblies in the App.xaml.cs file in the UWP project as demonstrated in the following code samples.

{% highlight C# %} 

// In App.xaml.cs 
protected override void OnLaunched(LaunchActivatedEventArgs e)
{ 
   … 
   if (rootFrame == null) 
   { 
      List<Assembly> assembliesToInclude = new List<Assembly>();
      assembliesToInclude.Add(typeof(SfTextInputLayoutRenderer).GetTypeInfo().Assembly);
      Xamarin.Forms.Forms.Init(e, assembliesToInclude);
   } 
   … 
}

{% endhighlight %}

### Android

Android platform does not require any additional configuration to render the text input layout control.

## Initializing text input layout

Import the SfTextInputLayout namespace in respective page as demonstrated in the following code sample.

{% tabs %} 

{% highlight xaml %} 

xmlns:inputLayout="clr-namespace:Syncfusion.XForms.TextInputLayout;assembly=Syncfusion.Core.XForms"  

{% endhighlight %}

{% highlight C# %} 

using Syncfusion.XForms.TextInputLayout; 

{% endhighlight %}

{% endtabs %}

Add any input view control such as `Entry`, `Editor`, `SfNumericTextBox`, or `SfMaskedEdit`, and add hint label (floating label).

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout>
   <Entry />
</inputLayout:SfTextInputLayout>  

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

### Adding hint
Floating label for the text input layout can be added by setting `Hint` property.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
   Hint="Name">
   <Entry />
</inputLayout:SfTextInputLayout>  

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name"; 
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

Run the project, and check if you get following output to make sure that the project has been configured properly to add the text input layout control.

![](Getting-Started_images/textInput_getting_img2.png)
![](Getting-Started_images/textInput_getting_img3.png)

## Enabling password visibility toggle

The password visibility toggle is used to show or hide the visibility of characters in the input view added to the control. You can enable this toggle by setting the `EnablePasswordVisibilityToggle` property to true.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name"
    EnablePasswordVisibilityToggle="true">
    <Entry Text="John" />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.EnablePasswordVisibilityToggle = true;
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/textInput_getting_img4.png)
![](Getting-Started_images/textInput_getting_img5.png)