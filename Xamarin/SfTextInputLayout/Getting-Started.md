---
layout: post
title: Getting Started for Essential Xamarin.Forms Text Input Layout
description: How to create a text input layout and adds decorative elements.
platform: xamarin
control: SfTextInputLayout
documentation: ug
---

# Getting Started

This section explains the steps required to configure the text input layout control with floating label, icons, password toggle, and assistive labels. This section covers only the minimal features needeed to get started with the text input layout control.

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

To deploy the text input layout in `Release` mode, initialize the core assemblies in the App.xaml.cs file in the UWP project as demonstrated in the dollowing code samples.

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

The password visibility toggle is used to show or hide the visibility of characters in the text view added to the control. You can enable this toggle by setting the `EnablePasswordVisibilityToggle` property to true.

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

## Adding custom icons

Any custom icons can be added to the text input layout control at the leading edge or the trailing edge of input view. The events and commands related to the custom icons should be handled at the application level.

Unicode or font icons for labels can be displayed as icons.

### Leading view

A label can be added as a leading icon for the input view and positioned either inside or outside of the container of input view by setting the `LeadingViewPosition` property. By default, it will be positioned outside.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name"
    EnablePasswordVisibilityToggle="true"
    LeadingViewPosition="Inside" >
    <Entry Text="John" />
    <inputLayout:SfTextInputLayout.LeadingView>
       <Label
           Text="A">     
       </Label>
    </inputLayout:SfTextInputLayout.LeadingView>
 </inputLayout:SfTextInputLayout> 


{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.EnablePasswordVisibilityToggle = true;
inputLayout.LeadingViewPosition = ViewPosition.Inside;
inputLayout.LeadingView = new Label() { Text = "A" };
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/textInput_getting_img6.png)
![](Getting-Started_images/textInput_getting_img7.png)

### Trailing  view

A label can be added as a trailing icon for the input view and positioned either inside or outside of the container of input view by setting the `TrailingViewPosition` property. By default, it will be positioned inside.

% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name"
    EnablePasswordVisibilityToggle="true"
    TrailingViewPosition="Outside">
    <Entry Text="John" />
    <inputLayout:SfTextInputLayout.TrailingView>
      <Label
         Text="B">     
      </Label>
    </inputLayout:SfTextInputLayout.TrailingView>
 </inputLayout:SfTextInputLayout> 

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.EnablePasswordVisibilityToggle = true;
inputLayout.TrailingViewPosition = ViewPosition.Outside; 
inputLayout. TrailingView = new Label() { Text = "B" };
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/textInput_getting_img8.png)
![](Getting-Started_images/textInput_getting_img9.png)

## Adding assistive labels

Assistive labels provide additional information about text entered into the input view controls.

### Helper text

Helper text conveys additional guidance about the input field such as how it will be used. It can be set using the `HelperText` property.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
  Hint="Name"
  HelperText="Enter your name">
  <Entry Text="John" />
</inputLayout:SfTextInputLayout>   

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.HelperText = "Enter your name";
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

The visibility of the helper text can be disabled by setting the `ShowHelperText` property to false. By default, it is set to true.

![](Getting-Started_images/textInput_getting_img10.png)

### Error message

When the text input is not accepted, an error message will display instructions to fix it. Error messages will be displayed below the input line till entering the correct text. It can be set using the 
`ErrorText` property, but it will be displayed only when the `HasError` property is set to `true`.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    HelperText="Enter your name"
    ErrorText="Should not contains special characters"
    HasError="true">
    <Entry />
</inputLayout:SfTextInputLayout>  
 

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.HelperText = "Enter your name";
inputLayout.ErrorText = "Should not contains special characters";
inputLayout.HasError = true; 
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/textInput_getting_img11.png)

N> Error validations should be done in the application level.

### Character counter

Character counter is used when you need to limit the characters. Character limit can be set using the `CharMaxLength` property. The character counter can be enabled by setting the `ShowCharCount` property to true.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    ShowCharCount="true"
    CharMaxLength="10">
    <Entry Text="John" />
</inputLayout:SfTextInputLayout> 
  

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.CharMaxLength = 10;
inputLayout.ShowCharCount = true;
inputLayout.InputView = new Entry(){Text="John"}; 

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/textInput_getting_img12.png)

## Container type

Containers improve the discoverability of input view by creating a contrast between the input view and assistive elements.

### Filled

The background of the input view will be filled with container color, and its stroke (at the bottom edge) color and thickness will be changed based on its states. It can be enabled by setting the `ContainerType` property to `Filled`.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    ContainerType="Filled">
    <Entry Text="John" />
</inputLayout:SfTextInputLayout>  

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.ContainerType = ContainerType.Filled;
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/textInput_getting_img13.png)

### Outlined

When setting the `ContainerType` property to `Outlined`, the background of the container will be transparent, and the container will be covered with a rounded-corner border.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    ContainerType="Outlined">
    <Entry Text="John" />
</inputLayout:SfTextInputLayout>  
 

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.ContainerType = ContainerType.Outlined;
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/textInput_getting_img14.png)

## Customizing colors

The colors of the assistive elements can be customized by setting the following properties: `FocusedColor`, `UnfocusedColor`, `ErrorColor`, and `ContainerBackgroundColor`.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    FocusedColor="Teal"
    UnfocusedColor="Purple"
    ErrorColor="Fuchsia"
    ContainerBackgroundColor="FloralWhite"
    ErrorText="Invalid text"
    HasError="true">
    <Entry Text="John" />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

inputLayout.Hint = "Name";
inputLayout.FocusedColor = Color.Teal;
inputLayout.UnfocusedColor = Color.Purple;
inputLayout.ErrorColor = Color.Fuchsia;
inputLayout.ContainerBackgroundColor = Color.FloralWhite;
inputLayout.ErrorText = "Invalid text";
inputLayout.HasError = true;
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![](Getting-Started_images/textInput_getting_img15.png)
![](Getting-Started_images/textInput_getting_img16.png)
![](Getting-Started_images/textInput_getting_img17.png)

