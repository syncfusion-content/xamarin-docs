---
layout: post
title: How to | SfTextInputLayout |Xamarin | Syncfusion
description: Explains the text input layout customization
platform: Xamarin
control: SfTextInputLayout
documentation: ug
--- 
# How to 

## Customize the thickness of stroke 

The border stroke width (for [Outlined](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.ContainerType.html)) and line thickness (for [Filled](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.ContainerType.html) and [None](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.ContainerType.html)) can be customized based on the focus state of the input view by setting the [FocusedStrokeWidth](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~FocusedStrokeWidthProperty.html) and [UnfocusedStrokeWidth](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~UnfocusedStrokeWidthProperty.html) properties.

{% tabs %}

{% highlight xaml %}

<inputLayout:SfTextInputLayout
            Hint="Name" 
            ContainerType="Outlined"
            HelperText="Enter your name"
	    FocusedStrokeWidth="4"
	    UnfocusedStrokeWidth="2">
            <Entry />
</inputLayout:SfTextInputLayout>
		
{% endhighlight %}

{% highlight c# %}

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.ContainerType = ContainerType.Outlined;
inputLayout.HelperText = "Enter your name"
inputLayout.FocusedStrokeWidth = 4;
inputLayout.UnfocusedStrokeWidth = 2;
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

![FocusedStrokeWidth img](How-to-images/FocusedStroke.png)

![UnfocusedStrokeWidth img](How-to-images/UnfocusedStroke.png)

## Customize the font for input view

You can customize the font for the input view (Entry, Editor, SfMaskedEdit, and SfNumericTextBox) inside SfTextInputLayout using the [FontSize](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.entry.fontsize?view=xamarin-forms), [FontAttributes](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.entry.fontattributes?view=xamarin-forms), and [FontFamily](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.entry.fontfamily?view=xamarin-forms) properties.

