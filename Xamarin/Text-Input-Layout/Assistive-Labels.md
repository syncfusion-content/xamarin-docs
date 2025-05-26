---
layout: post
title: Assistive Labels in Xamarin Text Input Layout Control | Syncfusion
description: Learn about assistive labels support in Syncfusion Xamarin Text Input Layout (SfTextInputLayout) control and more.
platform: Xamarin
control: SfTextInputLayout
documentation: ug
---

# Assistive Labels in Xamarin Text Input Layout (SfTextInputLayout)

Assistive labels provide additional information about the text entered in the input view controls.

## Helper Text

Helper text provides additional guidance about the input field, such as how it will be used. It can be set using the [HelperText](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_HelperText) property.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
  Hint="Name"
  HelperText="Enter your name">
  <Entry />
</inputLayout:SfTextInputLayout>   

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.HelperText = "Enter your name";
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

The visibility of the helper text can be disabled by setting the [ShowHelperText](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_ShowHelperText) property to false. By default, it is set to true.

![Helper label](Assistive-Labels-images/helper.PNG)

## Error Message

When the text input is not accepted, an error message will display instructions to correct it. Error messages remain below the input line until the correct text is entered. It can be set using the [ErrorText](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_ErrorText) property, but it will only be displayed when the [HasError](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_HasError) property is set to `true`.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Email" 
    HelperText="Enter your email address"
    ErrorText="Invalid email"
    HasError="true">
    <Entry />
</inputLayout:SfTextInputLayout>  
 

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Email";
inputLayout.HelperText = "Enter your email address";
inputLayout.ErrorText = "Invalid email";
inputLayout.HasError = true; 
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

![Error label](Assistive-Labels-images/error.gif)

> **Note:** Error validations should be handled at the application level.

## Character Counter

The character counter is used when you need to limit the number of characters. The character limit can be set using the [CharMaxLength](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_CharMaxLength) property. The character counter can be enabled by setting the [ShowCharCount](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_ShowCharCount) property to true.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Password" 
    ShowCharCount="true"
    CharMaxLength="8"
    HelperText="Enter 5 to 8 characters">
    <Entry />
</inputLayout:SfTextInputLayout> 
  

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Password";
inputLayout.CharMaxLength = 8;
inputLayout.ShowCharCount = true;
inputLayout.HelperText = "Enter 5 to 8 characters";
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

![Character counter label](Assistive-Labels-images/charcount.gif)

> **Note:** When the character count reaches the maximum character length, the error color is applied to the hint, border, and counter label.

## Reserve Spaces for Assistive Labels

The reserved spaces for assistive labels can be removed by setting the [ReserveSpaceForAssistiveLabels](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_ReserveSpaceForAssistiveLabelsProperty) property to false.

{% tabs %}

{% highlight xaml %}

<inputLayout:SfTextInputLayout 
            ContainerType="Outlined" 
            Hint="Name" 
            ReserveSpaceForAssistiveLabels="False">
            <Entry />
</inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight c# %}

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.ContainerType = ContainerType.Outlined;
inputLayout.ReserveSpaceForAssistiveLabels = false;
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

![Reserve space for assistive label](Assistive-Labels-images/ReserveSpaceAPI.png)

## See Also

- [How to remove the space at the bottom of SfTextInputLayout](https://support.syncfusion.com/kb/article/9557/how-to-remove-the-space-at-the-bottom-of-textinputlayout)

- [How to apply LineBreakMode for labels in SfTextInputLayout](https://support.syncfusion.com/kb/article/9518/how-to-apply-linebreakmode-for-labels-in-xamarin-text-input-layout)

- [How to customize the properties of outline border colors, hint name, helper text, error text, and char count](https://support.syncfusion.com/kb/article/10194/how-to-customize-the-properties-of-outline-border-colors-hint-name-helper-text-error-text)

- [How to customize the color of border and labels in SfTextInputLayout](https://support.syncfusion.com/kb/article/9248/how-to-customize-the-color-of-border-and-labels-in-sftextinputlayout)
