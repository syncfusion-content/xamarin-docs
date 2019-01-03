---
layout: post
title: Getting started in Syncfusion CheckBox for Xamarin.Forms platform
description: Learn how to customize the basic features of SfCheckBox
platform: Xamarin.Forms
control: SfCheckBox
documentation: ug 
keywords: button, SfCheckBox, CheckBox

---

# Getting Started
This section explains the steps required to configure the `SfCheckBox` control in a real-time scenario and provides a walk-through on some of the customization features available in `SfCheckBox` control.

## Add SfCheckBox reference
Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add checkbox to your project, open the NuGet package manager in Visual Studio, and search for "[syncfusion.xamarin.buttons](https://www.nuget.org/packages/Syncfusion.Xamarin.Buttons)", and then install it. 

![Xamarin.Forms CheckBox NuGet](Images/nuget.png)

N>Starting with v16.2.0.x, if you reference Syncfusion assemblies from trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to this [link](https://help.syncfusion.com/common/essential-studio/licensing/license-key) to know about registering Syncfusion license key in your Xamarin application to use our components.

After adding the assembly reference, an additional step is required for iOS and UWP projects. 

### Additional step for iOS
To launch `SfCheckBox` in iOS, call the `SfCheckBoxRenderer.Init()` in `FinishedLaunching` overridden method of `AppDelegate` class in iOS Project, as demonstrated in the following code example.

{% tabs %}
{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    global::Xamarin.Forms.Forms.Init();
    LoadApplication(new App());
    SfCheckBoxRenderer.Init();
    return base.FinishedLaunching(app, options);
}
{% endhighlight %}
{% endtabs %}

### Additional step for UWP
This step is required only if the application is deployed in Release mode with .NET native tool chain enabled. It is for resolving the known Framework issue “Custom controls not rendering in Release mode” in UWP platform. Initializing the `SfCheckBox` assembly at `OnLaunched` overridden method of the `App` class in UWP project is the suggested work around, as demonstrated in the following code example.

{% tabs %}
{% highlight c# %}
protected override void OnLaunched(LaunchActivatedEventArgs e)
{
    ..... 
    rootFrame.NavigationFailed += OnNavigationFailed;
    // Add `using System.Reflection;` 
    List<Assembly> assembliesToInclude = new List<Assembly>();
    //Now, add all the assemblies that your app uses 
    assembliesToInclude.Add(typeof(SfCheckBoxRenderer).GetTypeInfo().Assembly);
    // replaces Xamarin.Forms.Forms.Init(e);
    Xamarin.Forms.Forms.Init(e, assembliesToInclude);
    ..... 
}
{% endhighlight %}
{% endtabs %}

## Create a Simple SfCheckBox
The `SfCheckBox` control is configured entirely in C# code or by using XAML markup. The following steps explain how to create a `SfCheckBox` and configure its elements.

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

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
	     xmlns:syncfusion="clr-namespace:Syncfusion.XForms.Buttons;assembly=Syncfusion.Buttons.XForms"             
	     x:Class="GettingStarted.MainPage">
    <ContentPage.Content>
        <StackLayout>
              <syncfusion:SfCheckBox x:Name="checkBox"/>
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
            SfCheckBox checkBox = new SfCheckBox();
            stackLayout.Children.Add(checkbox);
            this.Content = stackLayout;
        }
    }
}
{% endhighlight %}
{% endtabs %}

## Setting caption
The check box caption can be defined using the `Text` property of `SfCheckBox`. This caption normally describes the meaning of the check box and it displays next to check box.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfCheckBox x:Name="checkBox" IsChecked="True" Text="CheckBox"/>
{% endhighlight %}
{% highlight c# %}
SfCheckBox checkBox = new SfCheckBox();
checkBox.IsChecked = true;
checkBox.Text = "CheckBox";
{% endhighlight %}
{% endtabs %}

![Xamarin.Forms CheckBox caption](Images/Caption.png) 

This demo can be downloaded from this [link](http://files2.syncfusion.com/Xamarin.Forms/Samples/CheckBox_GettingStarted.zip ).

## Change the check box state
The three visual states of `SfCheckBox` are: 

* Checked
* Unchecked
* Indeterminate

![Xamarin.Forms CheckBox states](Images/States.png) 

You can change the state of the check box using the `IsChecked` property of `SfCheckBox`. In checked state, a tick mark is added to the visualization of check box.

<table>
<tr>
<td>
<b>State</b>
</td>
<td>
<b>Property</b>
</td>
<td>
<b>Value</b>
</td>
</tr>
<tr>
<td>
checked
</td>
<td>
IsChecked
</td>
<td>
true
</td>
</tr>
<tr>
<td>
unchecked
</td>
<td>
IsChecked
</td>
<td>
false
</td>
</tr>
<tr>
<td>
indeterminate
</td>
<td>
IsChecked
</td>
<td>
null
</td>
</tr>
</table>

N>For the check box, to report the indeterminate state, set the `IsThreeState` property to true.

Check box can be used as a single or as a group. A single check box mostly used for a binary yes/no choice, such as "Remember me?", login scenario, or a terms of service agreement.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfCheckBox x:Name="checkBox" Text="I agree to the terms of services for this site" IsChecked="True"/> 
{% endhighlight %}
{% highlight c# %}
SfCheckBox checkBox = new SfCheckBox();
checkBox.Text = "I agree to the terms of services for this site";
checkBox.IsChecked = true;
{% endhighlight %}
{% endtabs %}

![Xamarin.Forms CheckBox tri-state](Images/Agree.png)

Multiple check boxes can be used as a group for multi-select scenarios in which a user chooses one or more items from the group of choices that are not mutually exclusive.

{% tabs %}
{% highlight xaml %}
<Label x:Name="label" Text="Pizza Toppings" />
<syncfusion:SfCheckBox x:Name="pepperoni" Text="Pepperoni"/>
<syncfusion:SfCheckBox x:Name="beef" Text="Beef" IsChecked="True"/>
<syncfusion:SfCheckBox x:Name="mushroom" Text="Mushrooms"/>
<syncfusion:SfCheckBox x:Name="onion" Text="Onions" IsChecked="True"/>
{% endhighlight %}
{% highlight c# %}
Label label = new Label();
label.Text = "Pizza Toppings";
SfCheckBox pepperoni= new SfCheckBox();
pepperoni.Text = "Pepperoni";
SfCheckBox beef= new SfCheckBox();
beef.Text = "Beef";
beef.IsChecked = true;
SfCheckBox mushroom = new SfCheckBox();
mushroom.Text = "Mushrooms";
SfCheckBox onion = new SfCheckBox();
onion.Text = "Pepperoni";
onion.IsChecked = true;
{% endhighlight %}
{% endtabs %}

![Xamarin.Forms CheckBox multi-selection](Images/StateChange.png)

This demo can be downloaded from this [link](http://files2.syncfusion.com/Xamarin.Forms/Samples/CheckBox_StateChanging.zip ).

## Indeterminate

The `SfCheckBox` allows an indeterminate state in addition to the checked and unchecked state. The indeterminate state of the check box is enabled by setting the `IsThreeState` property of the control to `True`.

N>When the `IsThreeState` property is set to `False` and `IsChecked` property is set to `null` then the check box will be in unchecked state.

The indeterminate state is used when a group of sub-choices has both checked and unchecked states. In the following example, the "Select all" checkbox has the `IsThreeState` property set to `true`. The "Select all" checkbox is checked if all child elements are checked, unchecked if all the child elements are unchecked, and indeterminate otherwise.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfCheckBox x:Name="selectAll" Text="Select All" IsChecked="{x:Null}" StateChanged="SelectAll_StateChanged"/>
<syncfusion:SfCheckBox x:Name="pepperoni" Text="Pepperoni" StateChanged="CheckBox_StateChanged"/>
<syncfusion:SfCheckBox x:Name="beef" Text="Beef" IsChecked="True" StateChanged="CheckBox_StateChanged"/>
<syncfusion:SfCheckBox x:Name="mushroom" Text="Mushrooms" StateChanged="CheckBox_StateChanged"/>
<syncfusion:SfCheckBox x:Name="onion" Text="Onions" IsChecked="True" StateChanged="CheckBox_StateChanged"/>
bool skip = false;

private void SelectAll_StateChanged(object sender, StateChangedEventArgs e)
{
    if (!skip)
    {
       skip = true;
       pepperoni.IsChecked = beef.IsChecked = mushroom.IsChecked = onion.IsChecked = e.IsChecked;
       skip = false;
    }
}

private void CheckBox_StateChanged(object sender, StateChangedEventArgs e)
{
    if (!skip)
    {
       skip = true;
       if (pepperoni.IsChecked.Value && beef.IsChecked.Value && mushroom.IsChecked.Value && onion.IsChecked.Value)
           selectAll.IsChecked = true;
       else if (!pepperoni.IsChecked.Value && !beef.IsChecked.Value && !mushroom.IsChecked.Value && !onion.IsChecked.Value)
	       selectAll.IsChecked = false;
       else
           selectAll.IsChecked = null;
       skip = false;
    }
}

{% endhighlight %}
{% highlight c# %}
bool skip = false;
SfCheckBox selectAll, pepperoni, beef, mushroom, onion;
selectAll = new SfCheckBox();
selectAll.StateChanged += SelectAll_StateChanged;
selectAll.Text = "Select All";
pepperoni = new SfCheckBox();
pepperoni.StateChanged += CheckBox_StateChanged;
pepperoni.Text = "Pepperoni";
beef = new SfCheckBox();
beef.StateChanged += CheckBox_StateChanged;
beef.Text = "Beef";
beef.IsChecked = true;
mushroom = new SfCheckBox();
mushroom.StateChanged += CheckBox_StateChanged;
mushroom.Text = "Mushrooms";
onion = new SfCheckBox();
onion.StateChanged += CheckBox_StateChanged;
onion.Text = "Onions";
onion.IsChecked = true;

private void SelectAll_StateChanged(object sender, StateChangedEventArgs e)
{
    if (!skip)
    {
       skip = true;
       pepperoni.IsChecked = beef.IsChecked = mushroom.IsChecked = onion.IsChecked = e.IsChecked;
       skip = false;
    }
}

private void CheckBox_StateChanged(object sender, StateChangedEventArgs e)
{
    if (!skip)
    {
       skip = true;
       if (pepperoni.IsChecked.Value && beef.IsChecked.Value && mushroom.IsChecked.Value && onion.IsChecked.Value)
           selectAll.IsChecked = true;
       else if (!pepperoni.IsChecked.Value && !beef.IsChecked.Value && !mushroom.IsChecked.Value && !onion.IsChecked.Value)
	       selectAll.IsChecked = false;
       else
           selectAll.IsChecked = null;
       skip = false;
    }
}
		
{% endhighlight %}
{% endtabs %}

![Xamarin.Forms CheckBox intermediate state](Images/Inter1.jpg) ![](Images/Inter2.jpg)

This demo can be downloaded from this [link](http://www.syncfusion.com/downloads/support/directtrac/general/ze/CheckBox_GettingStarted-1768275699.zip ).