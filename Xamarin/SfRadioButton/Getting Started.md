---
layout: post
title: Getting started in SfRadioButton for Xamarin.Forms platform
description: Learn how to customize the basic features of SfRadioButton
platform: Xamarin.Forms
control: SfRadioButton
documentation: ug 
keywords: button, SfRadioButton, RadioButton

---

# Getting Started
This section explains you the steps required to configure a `SfRadioButton` control in a real-time scenario and provides a walk-through on some of the customization features available in `SfRadioButton` control.

## Add SfRadioButton reference
Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add maskededit to your project, open the NuGet package manager in Visual Studio, and search for "[syncfusion.xamarin.buttons](https://www.nuget.org/packages/Syncfusion.Xamarin.Buttons)", and then install it. 

![](Images/nuget.png) 

N>Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin application to use our components.

After adding the assembly reference, an additional step is required for iOS and UWP projects. 

### Additional step for iOS
To launch `SfRadioButton` in iOS, call the `SfRadioButtonRenderer.Init()` in `FinishedLaunching` overridden method of `AppDelegate` class in iOS Project, as demonstrated in the following code example.

{% tabs %}
{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    global::Xamarin.Forms.Forms.Init();
    LoadApplication(new App());
    SfRadioButtonRenderer.Init();
    return base.FinishedLaunching(app, options);
}
{% endhighlight %}
{% endtabs %}

### Additional step for UWP
This step is required only if the application is deployed in Release mode with .NET native tool chain enabled and it is for resolving the known Framework issue “Custom controls not rendering in Release mode” in UWP platform. Initializing the `SfRadioButton` assembly at `OnLaunched` overridden method of the `App` class in UWP project is the suggested work around, as demonstrated in the following code example.

{% tabs %}
{% highlight c# %}
protected override void OnLaunched(LaunchActivatedEventArgs e)
{
    ..... 
    rootFrame.NavigationFailed += OnNavigationFailed;
    // you'll need to add `using System.Reflection;` 
    List<Assembly> assembliesToInclude = new List<Assembly>();
    //Now, add all the assemblies your app uses 
    assembliesToInclude.Add(typeof(SfRadioButtonRenderer).GetTypeInfo().Assembly);
    // replaces Xamarin.Forms.Forms.Init(e);
    Xamarin.Forms.Forms.Init(e, assembliesToInclude);
    ..... 
}
{% endhighlight %}
{% endtabs %}

## Create a Simple SfRadioButton
The `SfRadioButton` control is configured entirely in C# code or by using XAML markup. The following steps explain how to create a `SfRadioButton` and configure its elements.

### Add namespace for referred assemblies

{% tabs %}
{% highlight xaml %}
xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"
{% endhighlight %}
{% highlight c# %}
using Syncfusion.XForms.Buttons;
{% endhighlight %}
{% endtabs %}

### Refer SfCheckBox control with declared suffix name for Namespace

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8">
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
	     xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms" 
	     x:Class="GettingStarted.MainPage">
<ContentPage.Content>
  <StackLayout>
     <syncfusion:SfRadioButton x:Name="radioButton"/>        
</StackLayout>
</ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}
using Syncfusion.XForms.Buttons;
using Xamarin.Forms;
namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout();
            SfRadioButton radioButton = new SfRadioButton();
            stackLayout.Children.Add(radioButton);
            this.Content = stackLayout;
        }
    }
}
{% endhighlight %}
{% endtabs %}

##Setting caption

The radio button caption can be defined using `Text` property of `SfRadioButton`. This caption normally describes the meaning of the radio button and it displays next to radio button.
 
{% tabs %}
{% highlight xaml %}
<syncfusion:SfRadioButton x:Name="radioButton" Text="RadioButton"/>
{% endhighlight %}
{% highlight c# %}
SfRadioButton radioButton = new SfRadioButton();
radioButton.Text = "RadioButton";
{% endhighlight %}
{% endtabs %}

![](Images/Caption.png)

This demo can be downloaded from this [link](http://files2.syncfusion.com/Xamarin.Android/Samples/MaskedEdit_VisualCustomize.zip).

## Change the radio button state

The `SfRadioButton` contains two different states visually, they are:

* Checked
* Unchecked

You can change the state of the radio button using `IsChecked` property of `SfRadioButton`. In the checked state an inner circle will be added to the visualization of radio button.
The radio buttons are used when there is a list of two or more options or group that are mutually exclusive and the user must select exactly one choice, such as “Select Gender” or “Choose the best option!”.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfRadioGroup x:Name="radioGroup">
     <syncfusion:SfRadioButton x:Name="male" Text="Male" IsChecked="True"/>
     <syncfusion:SfRadioButton x:Name="female" Text="Female"/>
</syncfusion:SfRadioGroup>
{% endhighlight %}
{% highlight c# %}
SfRadioGroup radioGroup = new SfRadioGroup();
SfRadioButton male = new SfRadioButton();
male.IsChecked = true;
male.Text = "Male";
SfRadioButton female = new SfRadioButton();
female.Text = "Female";
radioGroup.Children.Add(male);
radioGroup.Children.Add(female);
{% endhighlight %}
{% endtabs %}

N>`SfRadioButtons` are mutually exclusive among them when they are defined within `SfRadioGroup`.

![](Images/StateChage.png)

This demo can be downloaded from this [link](http://files2.syncfusion.com/Xamarin.Android/Samples/MaskedEdit_VisualCustomize.zip).
