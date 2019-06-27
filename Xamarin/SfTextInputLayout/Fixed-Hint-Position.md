---
layout: post
title: Syncfusion text input layout hint position
description: It describes that the hint position for text input layout can be fixed always at the top by setting the IsHintAlwaysFloated property.
platform: xamarin
control: SfTextInputLayout
documentation: ug
---

# Fixed hint position

Hint label for the text input layout can be fixed always at the top position. This helps the user to make the hint label floating even if the input view are not focused. It can be enabled by setting the `IsHintAlwaysFloated`.

>**NOTE**
The default value of `IsHintAlwaysFloated` is `false`.

## Filled

The hint label position of the input view will be set always at the top for the [Filled](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.ContainerType.html) container type. 

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

The hint label position of the input view will be set always at the top for the [Outlined](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.ContainerType.html) container type.

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

The hint label position of the input view will be set always at the top for the [None](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.ContainerType.html) container type.

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


