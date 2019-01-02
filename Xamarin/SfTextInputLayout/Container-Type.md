---
layout: post
title: Container Type
description: How to change the container of text input layout.
platform: xamarin
control: SfTextInputLayout
documentation: ug
---

# Container type

Containers improve the discoverability of input view by creating a contrast between the input view and assistive elements.

## Filled

The background of the input view will be filled with container color, and its stroke (at the bottom edge) color and thickness will be changed based on its states. It can be enabled by setting the [ContainerType](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~ContainerType.html) property to [Filled](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.ContainerType.html).

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    ContainerType="Filled">
    <Entry Text="John" />
</inputLayout:SfTextInputLayout>  

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.ContainerType = ContainerType.Filled;
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![](Container-Type-images/textInput_container_img1.png)

## Outlined

When setting the [ContainerType](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~ContainerType.html) property to [Outlined](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.ContainerType.html), the background of the container will be transparent, and the container will be covered with a rounded-corner border.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    ContainerType="Outlined">
    <Entry Text="John" />
</inputLayout:SfTextInputLayout>  
 

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.ContainerType = ContainerType.Outlined;
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![](Container-Type-images/textInput_container_img2.png)

More information to customize the thickness of the stroke for text input layout is in this link.

## None

When setting the [ContainerType](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~ContainerType.html) property to [None](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.ContainerType.html), the container will have empty background and enough spacing.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    ContainerType="None">
    <Entry Text="John" />
</inputLayout:SfTextInputLayout>  
 

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.ContainerType = ContainerType.None;
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![](Container-Type-images/textInput_None_Type.png)


