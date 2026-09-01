---
layout: post
title: Fixed Hint Position in Xamarin Text Input Layout Control | Syncfusion
description: Learn about fixing the hint position in the Syncfusion Xamarin Text Input Layout (SfTextInputLayout) control.
platform: xamarin
control: SfTextInputLayout
documentation: ug
---

# Fixed Hint Position in Xamarin Text Input Layout (SfTextInputLayout)

The hint label for the text input layout is permanently positioned at the top. This ensures that the hint label floats even when the input view is not focused. You can enable this feature by setting the `IsHintAlwaysFloated` property.

> **Note:** The default value of `IsHintAlwaysFloated` is `false`.

## Filled

The hint label position is consistently set at the top when using the [Filled](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.ContainerType.html) container type.

{% tabs %} 

{% highlight xaml %} 

 <inputLayout:SfTextInputLayout 
    Hint="Name"
    IsHintAlwaysFloated="true" 
    ContainerType="Filled"
    HelperText="Enter your name">
    <Entry />
</inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.IsHintAlwaysFloated = true;
inputLayout.ContainerType = ContainerType.Filled;
inputLayout.HelperText= "Enter your name";
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

![Filled type](Hint-Position-images/HintPosition_filled.jpg)

## Outlined

The hint label position is consistently set at the top for the [Outlined](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.ContainerType.html) container type.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout 
    Hint="Name"
    IsHintAlwaysFloated="true" 
    ContainerType="Outlined"
    HelperText="Enter your name">
    <Entry />
</inputLayout:SfTextInputLayout>
 
{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.IsHintAlwaysFloated = true;
inputLayout.ContainerType = ContainerType.Outlined;
inputLayout.HelperText= "Enter your name";
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

![Outlined type](Hint-Position-images/HintPosition_outlined.jpg)

## None

The hint label position is consistently set at the top for the [None](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.ContainerType.html) container type.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout 
    Hint="Name"
    IsHintAlwaysFloated="true" 
    ContainerType="None"
    HelperText="Enter your name">
    <Entry />
</inputLayout:SfTextInputLayout> 
 

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.IsHintAlwaysFloated = true;
inputLayout.ContainerType = ContainerType.None;
inputLayout.HelperText= "Enter your name";
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

![None type](Hint-Position-images/HintPosition_none.jpg)

## See Also

- [How to customize the properties of outline border colors, hint name, helper text, error text, and char count](https://www.syncfusion.com/kb/11659/how-to-customize-the-properties-of-outline-border-colors-hint-name-helper-text-error-text)

- [How to customize the color of border and labels in SfTextInputLayout](https://www.syncfusion.com/kb/10466/how-to-customize-the-color-of-border-and-labels-in-sftextinputlayout)
