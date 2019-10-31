---
layout: post
title: Right-to-left | TextInputLayout for Xamarin.Forms | Syncfusion
description: Describes how TextInputLayout works on right-to-left localization.
platform: xamarin
control: SfTextInputLayout
documentation: ug
---

# Right-to-Left

The TextInputLayout supports to change the flow of text to the right-to-left direction by setting the [FlowDirection](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.visualelement.flowdirection?view=xamarin-forms#Xamarin_Forms_VisualElement_FlowDirection) to `RightToLeft`.

N> A specific platform setup is required to enable the right-to-left localization. For platform settings, refer to this [documentation](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/app-fundamentals/localization/right-to-left#platform-setup).

{% tabs %}
{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:inputLayout="clr-namespace:Syncfusion.XForms.TextInputLayout;assembly=Syncfusion.Core.XForms"
             x:Class="TextInputLayout.MainPage">

    <StackLayout>
       <inputLayout:SfTextInputLayout
            x:Name="textinputlayout" 
            FlowDirection="RightToLeft"
            ContainerType="Outlined"
            Hint="اسم"  
            HelperText="أدخل أسمك" >
            <Entry />
        </inputLayout:SfTextInputLayout>
    </StackLayout>

</ContentPage>

{% endhighlight %}
{% highlight c# %}

textinputlayout.FlowDirection = FlowDirection.RightToLeft;
textinputlayout.ContainerType = ContainerType.Outlined;
textinputlayout.Hint = "اسم";
textinputlayout.HelperText = "أدخل أسمك";
textinputlayout.InputView = new Entry(); 

{% endhighlight %}
{% endtabs %}

![Xamarin Forms TextInputLayout with right to left](RTL-images/XamarinForms_TextInputLayout_RTL.png)

