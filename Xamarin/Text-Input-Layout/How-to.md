---
layout: post
title: How to Customize SfTextInputLayout in Xamarin | Syncfusion
description: Learn how to customize the text input layout in Xamarin using SfTextInputLayout.
platform: Xamarin
control: SfTextInputLayout
documentation: ug
--- 

# How to Customize SfTextInputLayout
## Customize the Thickness of the Stroke

The border stroke width for [Outlined](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.ContainerType.html) and line thickness for [Filled](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.ContainerType.html) or [None](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.ContainerType.html) container types can be customized. This customization is based on the focus state of the input view by setting the [FocusedStrokeWidth](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_FocusedStrokeWidthProperty) and [UnfocusedStrokeWidth](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_UnfocusedStrokeWidthProperty) properties.

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

![Focused Stroke Width](How-to-images/FocusedStroke.png)

![Unfocused Stroke Width](How-to-images/UnfocusedStroke.png)

## Customize the Font for Input View

You can customize the font for the input view inside SfTextInputLayout using the following control properties:

- [Entry](https://learn.microsoft.com/en-us/dotnet/api/xamarin.forms.entry?view=xamarin-forms#properties)
- [Editor](https://learn.microsoft.com/en-us/dotnet/api/xamarin.forms.editor?view=xamarin-forms#properties)
- [SfMaskedEdit](https://help.syncfusion.com/xamarin/sfmaskededit/visual-customization#setting-appearance-of-text)
- [SfNumericTextBox](https://help.syncfusion.com/xamarin/sfnumerictextbox/font-settings)
- [SfAutoComplete](https://help.syncfusion.com/xamarin/sfautocomplete/customizing-autocomplete)
- [SfComboBox](https://help.syncfusion.com/xamarin/sfcombobox/customizing-combobox)
