---
layout: post
title: States and Colors
description: How to customize the colors based on states.
platform: xamarin
control: SfTextInputLayout
documentation: ug
---

# States and Colors

Based on states, color will be applied to the hint label and the border. So when the input view is in focused state then focused color will be applied, similarly for other states also. Current hint color or active color can be obtained from `CurrentActiveColor` property.

N> As error is not a state, error color will not be set to `CurrentActiveColor`

## Focused color
When the input view gets focused then the `FocusedColor` property value will be applied to the hint label and the border. 

I> Cursor color of the input view will be based on the `Accent` color of the application in each platform.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    FocusedColor="Teal"
    <Entry Text="John" />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

inputLayout.Hint = "Name";
inputLayout.FocusedColor = Color.Teal;
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![](Supported-input-views/textInput_colors_img1.png)

## Unfocused color
When the input view gets unfocused then the `UnfocusedColor` property value will be applied to the hint label and the border. 

N> Thickness of the border will also varied in focused and unfocused state.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    UnfocusedColor="Purple">
    <Entry Text="John" />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

inputLayout.Hint = "Name";
inputLayout.UnfocusedColor = Color.Purple;
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![](Supported-input-views/textInput_colors_img2.png)

## Error color
Error color can also be customized by setting `ErrorColor` property.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    ErrorColor="Fuchsia"
    ErrorText="Invalid text"
    HasError="true">
    <Entry Text="John" />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

inputLayout.Hint = "Name";
inputLayout.ErrorColor = Color.Fuchsia;
inputLayout.ErrorText = "Invalid text";
inputLayout.HasError = true;
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![](Supported-input-views/textInput_colors_img3.png)

## Container Color
Color of the container can be customized by setting `ContainerBackgroundColor` property, it is applicable only When `ContainerType` property is set as `Filled`.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    FocusedColor="Teal"
    ContainerBackgroundColor="FloralWhite">
    <Entry Text="John" />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

inputLayout.Hint = "Name";
inputLayout.FocusedColor = Color.Teal;
inputLayout.ContainerBackgroundColor = Color.FloralWhite;
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![](Supported-input-views/textInput_colors_img4.png)

## Disabled state

When text input layout is disabled by setting `IsEnabled` property as `false`. Then color of the container and other UI elements will also be changed to disabled state and it's color can't be customized.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    IsEnabled="false">
    <Entry Text="John" />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

inputLayout.Hint = "Name";
inputLayout.IsEnabled = false;
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![](Supported-input-views/textInput_colors_img5.png)

