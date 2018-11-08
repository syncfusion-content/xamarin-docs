---
layout: post
title: Custom icons
description: How to add custom icons for leading and trailing view.
platform: xamarin
control: SfTextInputLayout
documentation: ug
---

# Adding custom icons

Any custom icons can be added to the leading edge or the trailing edge of input view in the text input layout control. The events and commands related to the custom icons should be handled at the application level.

Unicode or font icons for the labels can be displayed as icons.

N> Refer to the following links to learn more about font icons:
* [How to create font icons using our metro studio and export as ttf?](https://help.syncfusion.com/metro-studio/export-icon-font)
* [How to set font family for the custom fonts in labels?](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/text/fonts#using-a-custom-font)

## Leading view

A label can be added as a leading icon for the input view by setting the [LeadingView](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~LeadingView.html) property. It can be positioned either inside or outside the container by setting the [LeadingViewPosition](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~LeadingViewPosition.html) property. By default, it is positioned [Outside](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.ViewPosition.html).

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Birth date"
    LeadingViewPosition="Inside" >
    <Entry />
    <inputLayout:SfTextInputLayout.LeadingView>
       <Label
           Text="&#x1F5D3;">     
       </Label>
    </inputLayout:SfTextInputLayout.LeadingView>
 </inputLayout:SfTextInputLayout> 

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Birth date";
inputLayout.LeadingViewPosition = ViewPosition.Inside;
inputLayout.LeadingView = new Label() { Text = "\U0001F5D3" };
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

![](Custom-Icons-images/textInput_icons_img1.png)
![](Custom-Icons-images/textInput_icons_img2.png)

N> The Leading icon and Trailing icon for the input view should only have the dimension of 24 x 24 dpi as per the [material design](https://material.io/design/iconography/system-icons.html#system-icon-metrics) specifications.

## Trailing  view

A label can be added as a trailing icon for the input view by setting the [TrailingView](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~TrailingView.html) property. It can be positioned either inside or outside  the container of input view by setting the [TrailingViewPosition](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~TrailingViewPosition.html) property. By default, it is positioned [Inside](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.ViewPosition.html).

{% tabs %}

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Birth date"
    TrailingViewPosition="Outside">
    <Entry  />
    <inputLayout:SfTextInputLayout.TrailingView>
      <Label
         Text="&#x1F5D3;">     
      </Label>
    </inputLayout:SfTextInputLayout.TrailingView>
 </inputLayout:SfTextInputLayout> 

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Birth date";
inputLayout.TrailingViewPosition = ViewPosition.Outside; 
inputLayout. TrailingView = new Label() { Text = "\U0001F5D3" };
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

![](Custom-Icons-images/textInput_icons_img3.png)
![](Custom-Icons-images/textInput_icons_img4.png)

