---
layout: post
title: How to | SfTextInputLayout |Xamarin | Syncfusion
description: Explains the text input layout customization
platform: Xamarin
control: SfTextInputLayout
documentation: ug
--- 
# How to 

## Customize the thickness of the stroke 

When the input view is focused, the [FocusedStrokeWidth](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~FocusedStrokeWidthProperty.html) property value will be applied to the thickness of the stroke.

When the input view is Unfocused, the [UnfocusedStrokeWidth](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~UnfocusedStrokeWidthProperty.html) property value will be applied to the thickness of the stroke.

{% tabs %}

{% highlight xaml %}

<inputLayout:SfTextInputLayout
    Hint="Name" 
    ContainerType="Outlined"
	FocusedStrokeWidth="4"
	UnfocusedStrokeWidth="2">
    <Entry Text="John" />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight c# %}

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.ContainerType = ContainerType.Outlined;
inputLayout.FocusedStrokeWidth = 4;
inputLayout.UnfocusedStrokeWidth = 2;
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

>**NOTE**
It is applicable for the bottom line and outline border when setting the container type as filled and outlined respectively.

