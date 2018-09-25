---
layout: post
title: Supported input views
description: How to add supported input views in text input layout.
platform: xamarin
control: SfTextInputLayout
documentation: ug
---

# Supported input views

## Entry

To enter single line text input, you can add [`Entry`](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/text/entry).

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
inputLayout.HelperText = "Enter your name"
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

![](Supported-input-views/textInput_input_img1.PNG)

## Editor


To enter multi line text input, you can add [`Editor`](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/text/editor).


{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
   Hint="Notes">
   <Editor />
</inputLayout:SfTextInputLayout>  

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Notes"; 
inputLayout.InputView = new Editor(); 

{% endhighlight %}

{% endtabs %}

![](Supported-input-views/textInput_input_img2.PNG)

## Masked edit

To initialize masked edit control and launch in each platform refer [`getting started with masked edit`](https://help.syncfusion.com/xamarin/sfmaskededit/getting-started),

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
   Hint="Card number"
   HelperText="Required *">
   <maskededit:SfMaskedEdit
        Keyboard="Numeric"
        Mask="0000 0000 0000 0000" />
</inputLayout:SfTextInputLayout>  

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Card number"; 
inputLayout.HelperText = "Required *"
inputLayout.InputView = new SfMaskedEdit() { Keyboard = Keyboard.Numeric, Mask = "0000 0000 0000 0000" }; 

{% endhighlight %}

{% endtabs %}

![](Supported-input-views/textInput_input_img3.PNG)

## Numeric text box

To initialize numeric text box control and launch in each platform refer [`getting started with numeric text box`](https://help.syncfusion.com/xamarin/sfnumerictextbox/getting-started),

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
   Hint="Amount"
   HelperText="Required *">
   <numericBox:SfNumericTextBox 
      Value="123.45"
      FormatString="c" />
</inputLayout:SfTextInputLayout>  

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Amount"; 
inputLayout.HelperText = "Required *"
inputLayout.InputView = new SfNumericTextBox() { Value = 123.45, FormatString="c" }; 

{% endhighlight %}

{% endtabs %}


![](Supported-input-views/textInput_input_img4.PNG)




