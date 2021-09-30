---
layout: post
title: States and Colors in Xamarin Text Input Layout control | Syncfusion
description: Learn here all about States and Colors support in Syncfusion Xamarin Text Input Layout (SfTextInputLayout) control and more.
platform: xamarin
control: SfTextInputLayout
documentation: ug
---

# States and Colors in Xamarin Text Input Layout (SfTextInputLayout)

Based on the states, the colors will be applied to the hint labels and borders. So, when the input view is in focused state, the focused color will be applied; it is similar to other states also. The current hint color or active color can be obtained from the [CurrentActiveColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_CurrentActiveColor) property.

N> Since error is not a state, the error color will not be set to [CurrentActiveColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_CurrentActiveColor) when [HasError](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_HasError) property is set to `true`.

## Focused color
When the input view is focused, the [FocusedColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_FocusedColor) property value will be applied to the hint label and border. 

I> Cursor color of the input view will be same as the `Accent` color of the application in each platform.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="User name" 
    FocusedColor="#00AFA0"
    HelperText="Enter your name"
    <Entry Text="John" />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "User name";
inputLayout.FocusedColor = Color.FromHex("#00AFA0");
inputLayout.ErrorText = "User name available";
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![Focused color](States-And-Colors-images/textInput_colors_img1.png)

## Unfocused color
When the input view is unfocused, the [UnfocusedColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_UnfocusedColor) property value will be applied to the hint label and border. 

N> Thickness of the border will also vary between the focused and unfocused states.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="User name" 
    UnfocusedColor="Silver"
    HelperText="User name available">
    <Entry Text="John" />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "User name";
inputLayout.UnfocusedColor = Color.Silver;
inputLayout.ErrorText = "User name available";
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![Unfocused color](States-And-Colors-images/textInput_colors_img2.png)

## Error color
The error color can also be customized by setting the [ErrorColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_ErrorColor) property.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    ErrorColor="#B00020"
    ErrorText="Should not contain special characters"
    HasError="true">
    <Entry Text="John/" />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.ErrorColor = Color.FromHex("#B00020");
inputLayout.ErrorText = "Should not contain special characters";
inputLayout.HasError = true;
inputLayout.InputView = new Entry() { Text = "John/" }; 

{% endhighlight %}

{% endtabs %}

![Error color](States-And-Colors-images/textInput_colors_img3.png)

## Container color
The color of the container can be customized by setting the [ContainerBackgroundColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_ContainerBackgroundColor) property. It is applicable when the [ContainerType](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_ContainerType) property is set to [Filled](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.ContainerType.html) and [Outlined](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.ContainerType.html).

### Filled

The color of the container is customized when the [ContainerType](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_ContainerType) is [Filled](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.ContainerType.html).

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    FocusedColor="#0450C2"
    ContainerType="Filled"
    ContainerBackgroundColor="#E6EEF9">
    <Entry Text="John" />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.FocusedColor = Color.FromHex("#0450C2");
inputLayout.ContainerBackgroundColor = Color.FromHex("#E6EEF9");
inputLayout.ContainerType = ContainerType.Filled;
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![Filled](States-And-Colors-images/textInput_colors_img4.png)

### Outlined

The color of the container is customized when the [ContainerType](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_ContainerType) is [Outlined](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.ContainerType.html).

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    FocusedColor="#0450C2"
    ContainerType="Outlined"
    ContainerBackgroundColor="#E6EEF9">
    <Entry Text="John" />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.ContainerType = ContainerType.Outlined;
inputLayout.FocusedColor = Color.FromHex("#0450C2");
inputLayout.ContainerBackgroundColor = Color.FromHex("#E6EEF9");
inputLayout.InputView = new Entry() { Text = "John" }; 

{% endhighlight %}

{% endtabs %}

![outlined](States-And-Colors-images/textInput_colors_img6.png)

## Disabled state

The text input layout is disabled by setting the [IsEnabled](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_IsEnabled) property to `false`. The color of the container and other UI elements will also be changed to the disabled state, but its color cannot be customized.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Name" 
    IsEnabled="false">
    <Entry />
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name";
inputLayout.IsEnabled = false;
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

![Disabled state](States-And-Colors-images/textInput_colors_img5.PNG)

## Customizing the text color of label

You can customize the text color of the [`hint`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_Hint) label, counter label, [`helper`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_HelperText) label and [`error`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_ErrorText) label using the `Color` property of the [`LabelStyle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.LabelStyle.html).

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout 
    Hint="Name" ContainerType="Outlined" HelperText="Enter your name"
    ErrorText="Invalid text" ErrorColor="#B00020"
    ShowCharCount="true" CharMaxLength="3">
        
    <inputLayout:SfTextInputLayout.HintLabelStyle>
        <inputLayout:LabelStyle Color="Green"/>
    </inputLayout:SfTextInputLayout.HintLabelStyle>
    <inputLayout:SfTextInputLayout.HelperLabelStyle>
        <inputLayout:LabelStyle Color="Blue"/>
    </inputLayout:SfTextInputLayout.HelperLabelStyle>
    <inputLayout:SfTextInputLayout.CounterLabelStyle>
        <inputLayout:LabelStyle Color="Brown"/>
    </inputLayout:SfTextInputLayout.CounterLabelStyle>
    <inputLayout:SfTextInputLayout.ErrorLabelStyle>
        <inputLayout:LabelStyle Color="Maroon"/>
    </inputLayout:SfTextInputLayout.ErrorLabelStyle>
        
    <Entry Text="John" />
        
</inputLayout:SfTextInputLayout>  
 
{% endhighlight %}

{% highlight C# %} 

    SfTextInputLayout inputLayout = new SfTextInputLayout();
    inputLayout.Hint = "Name";
    inputLayout.ContainerType = ContainerType.Outlined;
    inputLayout.HelperText = "Enter your name";
    inputLayout.ErrorColor = Color.FromHex("#B00020");
    inputLayout.CharMaxLength = 3;
    inputLayout.ShowCharCount = true;
    inputLayout.ErrorText = "Invalid text";
    inputLayout.InputView = new Entry();

    inputLayout.HintLabelStyle = new LabelStyle() { Color = Color.Green };
    inputLayout.HelperLabelStyle = new LabelStyle() { Color = Color.Blue };
    inputLayout.CounterLabelStyle = new LabelStyle() { Color = Color.Brown };
    inputLayout.ErrorLabelStyle = new LabelStyle() { Color = Color.Maroon };
    this.Content = inputLayout;

{% endhighlight %}

{% endtabs %}

![Label text color](States-And-Colors-images/LabelTextColor.PNG)

## See also

[How to validate with required verification in SfTextInputLayout](https://www.syncfusion.com/kb/11788/how-to-validate-with-required-verification-in-text-input-layout-in-xamarin-forms)

[How to customize the properties of outline border colors, hint name, helper text, error text, and char count](https://www.syncfusion.com/kb/11659/how-to-customize-the-properties-of-outline-border-colors-hint-name-helper-text-error-text)

[How to change the cursor color in SfTextInputLayout](https://www.syncfusion.com/kb/11608/how-to-change-the-cursor-color-in-xamarin-forms-text-input-layout)

[How to customize the color of border and labels in SfTextInputLayout](https://www.syncfusion.com/kb/10466/how-to-customize-the-color-of-border-and-labels-in-sftextinputlayout)
