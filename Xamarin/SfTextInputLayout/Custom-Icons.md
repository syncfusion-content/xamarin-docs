---
layout: post
title: Custom icons
description: How to add custom icons for leading and trailing view.
platform: xamarin
control: SfTextInputLayout
documentation: ug
---

# Adding custom icons

Any custom icons can be added to the text input layout control at the leading edge or the trailing edge of input view. The events and commands related to the custom icons should be handled at the application level.

Unicode or font icons for labels can be displayed as icons.

## Leading view

A label can be added as a leading icon for the input view and positioned either inside or outside of the container of input view by setting the `LeadingViewPosition` property. By default, it will be positioned outside.

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

![](Custom-Icons/textInput_icons_img1.png)
![](Custom-Icons/textInput_icons_img2.png)

## Trailing  view

A label can be added as a trailing icon for the input view and positioned either inside or outside of the container of input view by setting the `TrailingViewPosition` property. By default, it will be positioned inside.

% tabs %} 

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

![](Custom-Icons/textInput_icons_img3.png)
![](Custom-Icons/textInput_icons_img4.png)

