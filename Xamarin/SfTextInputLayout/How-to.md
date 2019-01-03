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

![FocusedStrokeWidth img](How-to-images/FocusedStroke.png)

![UnfocusedStrokeWidth img](How-to-images/UnfocusedStroke.jpg)

>**NOTE**
It is applicable for the bottom line and outline border when setting the container type as filled and outlined respectively.

## Customize the corner radius of the outline border 

When setting the [OutlineCornerRadius](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~OutlineCornerRadiusProperty.html) property as double value, the corner radius of the container will be changed.

{% tabs %}

{% highlight xaml %}

<inputLayout:SfTextInputLayout
            Hint="Name" 
            ContainerType="Outlined"
	        OutlineCornerRadius="8"/> 
			
{% endhighlight %}

{% highlight c# %}

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.ContainerType = ContainerType.Outlined;
inputLayout.OutlineCornerRadius = 8;

{% endhighlight %}

{% endtabs %}

![OutlineCornerRadius img](How-to-images/OutlinedCornerRadius.jpg)

>**NOTE**
It is applicable for the outline border when setting the container type as outlined.

## Customize the reserve spaces for assistive labels

The reserved spaces for assistive labels can be removed by setting the [ReserveSpaceForAssistiveLabels](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~ReserveSpaceForAssistiveLabelsProperty.html) to false.

{% tabs %}

{% highlight xaml %}

<inputLayout:SfTextInputLayout
            Hint="Name" 
	        HelperText="Enter your name"
            ContainerType="Outlined"
	        ReserveSpaceForAssistiveLabels="False"/>
 
{% endhighlight %}

{% highlight c# %}

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.HelperText = "Enter your name";
inputLayout.ContainerType = ContainerType.Outlined;
inputLayout.ReserveSpaceForAssistiveLabels = false;

{% endhighlight %}

{% endtabs %}



