---
layout: post
title: Custom Font
description: How to customize the font family, font size, and font attributes for hint, error, helper text, and the counter label.
platform: xamarin
control: SfTextInputLayout
documentation: ug
---

# Font Customization

Font can be customized by using the complex property of [hint](https://help.syncfusion.com/cr/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~HintProperty.html), [error text](https://help.syncfusion.com/cr/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~ErrorTextProperty.html), [helper text](https://help.syncfusion.com/cr/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~HelperTextProperty.html) and [counter label](https://help.syncfusion.com/cr/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~CharMaxLengthProperty.html).

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name"
ContainerType="Outlined"
HelperText="Enter your name">
    <Entry />
	<inputLayout:SfTextInputLayout.HintLabelStyle>
	<inputLayout:LabelStyle FontFamily="Times New Roman" FontSize="16"/>
	</inputLayout:SfTextInputLayout.HintLabelStyle>
	<inputLayout:SfTextInputLayout.HelperLabelStyle>
	    <inputLayout:LabelStyle FontFamily="Times New Roman" FontSize="12"/>
	</inputLayout:SfTextInputLayout.HelperLabelStyle>
 </inputLayout:SfTextInputLayout> 

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.ContainerType = ContainerType.Outlined;
inputLayout.HelperText = "Enter your name";
inputLayout.HintLabelStyle = new LabelStyle() {FontFamily= "Times New Roman", FontSize=16};
inputLayout.HelperLabelStyle = new LabelStyle() { FontFamily = "Times New Roman", FontSize = 12 };
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

![Font customization](Custom-Font-images/fontCustomization.png)


