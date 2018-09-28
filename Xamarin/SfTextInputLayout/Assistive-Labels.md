---
layout: post
title: Assitive Labels
description: How to add assistive labels like helper text, error label, character counter to the text input layout.
platform: xamarin
control: SfTextInputLayout
documentation: ug
---

# Adding assistive labels

Assistive labels provide additional information about text entered in the input view controls.

## Helper text

Helper text conveys additional guidance about the input field such as how it will be used. It can be set using the [HelperText](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~HelperText.html) property.

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

The visibility of the helper text can be disabled by setting the [ShowHelperText](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~ShowHelperText.html) property to false. By default, it is set to true.

![](Assistive-Labels/helper.PNG)

## Error message

When the text input is not accepted, an error message will display instructions to fix it. Error messages will be displayed below the input line till entering the correct text. It can be set using the [ErrorText](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~ErrorText.html) property, but it will be displayed only when the [HasError](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~HasError.html) property is set to `true`.

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

![](Assistive-Labels/error.gif)

N> Error validations should be done in the application level.

## Character counter

Character counter is used when you need to limit the characters. Character limit can be set using the [CharMaxLength](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~CharMaxLength.html) property. The character counter can be enabled by setting the [ShowCharCount](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~ShowCharCount.html) property to true.

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

![](Assistive-Labels/charcount.gif)

N> When character count reaches the maximum character length, the error color will be applied to hint, border, and counter label.

