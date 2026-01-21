---
layout: post
title: Custom Icons in Xamarin Text Input Layout Control | Syncfusion
description: Learn about custom icon support in the Syncfusion Xamarin Text Input Layout (SfTextInputLayout) control.
platform: xamarin
control: SfTextInputLayout
documentation: ug
---

# Custom Icons in Xamarin Text Input Layout (SfTextInputLayout)

Custom icons can be added to either the leading edge or trailing edge of an input view in the text input layout control. Events and commands related to custom icons should be handled at the application level. Unicode or font icons for the labels can be displayed as icons.

> **Note:** Refer to the following resources to learn more about font icons:
> * [How to create font icons using our Metro Studio and export as TTF](https://help.syncfusion.com/metro-studio/export-icon-font)
> * [How to set font family for custom fonts in labels](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/text/fonts#using-a-custom-font)

## Leading View

A label can be added as a leading icon for the input view by setting the [LeadingView](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_LeadingView) property. It can be positioned either inside or outside the container by using the [LeadingViewPosition](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_LeadingViewPosition) property, with the default position being [Outside](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.ViewPosition.html).

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Birth date"
    LeadingViewPosition="Inside" >
    <Entry />
    <inputLayout:SfTextInputLayout.LeadingView>
       <Label
           Text="&#x1F5D3;">     
       </Label>
    </inputLayout:SfTextInputLayout.LeadingView>
 </inputLayout:SfTextInputLayout> 

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Birth date";
inputLayout.LeadingViewPosition = ViewPosition.Inside;
inputLayout.LeadingView = new Label() { Text = "\U0001F5D3" };
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

![Leading view inside position](Custom-Icons-images/textInput_icons_img1.png)
![Leading view outside position](Custom-Icons-images/textInput_icons_img2.png)

## Trailing View

A label can be added as a trailing icon for the input view by setting the [TrailingView](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_TrailingView) property. It can be positioned either inside or outside the container of the input view by setting the [TrailingViewPosition](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_TrailingViewPosition) property, with the default position being [Inside](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.ViewPosition.html).

{% tabs %}

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
    Hint="Birth date"
    TrailingViewPosition="Outside">
    <Entry  />
    <inputLayout:SfTextInputLayout.TrailingView>
      <Label
         Text="&#x1F5D3;">     
      </Label>
    </inputLayout:SfTextInputLayout.TrailingView>
 </inputLayout:SfTextInputLayout> 

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Birth date";
inputLayout.TrailingViewPosition = ViewPosition.Outside; 
inputLayout. TrailingView = new Label() { Text = "\U0001F5D3" };
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

![Trailing view inside position](Custom-Icons-images/textInput_icons_img3.png)
![Trailing view outside position](Custom-Icons-images/textInput_icons_img4.png)

## Leading and Trailing View Customization

The height and width of the leading and trailing view's direct child can be customized within the text input layout. The height of these views can be adjusted up to 48px, but there is no limit on width.

{% tabs %}

{% highlight xaml %} 

  <inputLayout:SfTextInputLayout Padding="15"
                                 Hint="Password" 
                                 TrailingViewPosition="Inside" 
                                 EnablePasswordVisibilityToggle="false">
   <Entry />
   <inputLayout:SfTextInputLayout.TrailingView>
      <border:SfBorder WidthRequest="130"
                       CornerRadius="20" 
                       HeightRequest="30"  
                       BackgroundColor="#00619e">
        <Label TextColor="White"
               VerticalTextAlignment="Center" 
               HorizontalTextAlignment="Center" 
               Text="Show password"/>
      </border:SfBorder>
   </inputLayout:SfTextInputLayout.TrailingView>
   </inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
var border = new SfBorder();
var label = new Label();
inputLayout.Hint = "Password";
inputLayout.EnablePasswordVisibilityToggle = false;
border.WidthRequest = 130;
border.HeightRequest = 30;
border.CornerRadius = 20;
border.BackgroundColor = Color.FromHex("#00619e");
label.TextColor= Color.White;
label.VerticalTextAlignment = TextAlignment.Center;
label.HorizontalTextAlignment = TextAlignment.Center;
label.Text = "Show password";
border.Content = label;
inputLayout.TrailingView = border;
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

![Customization](Custom-Icons-images/textInput_icons_img5.png)

## Leading and Trailing View Visibility Customization

The [`ShowLeadingView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_ShowLeadingView) and [`ShowTrailingView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_ShowTrailingView) properties in [`SfTextInputLayout`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html) can be used to control the visibility of the leading and trailing views respectively.

{% tabs %}

{% highlight xaml %} 

  <inputLayout:SfTextInputLayout
    Hint="Birth date"
    ContainerType="Outlined"
    ShowLeadingView="False"
    ShowTrailingView="False" >
    <Entry />
    <inputLayout:SfTextInputLayout.LeadingView>
       <Label
           Text="&#x1F5D3;">     
       </Label>
    </inputLayout:SfTextInputLayout.LeadingView>
    <inputLayout:SfTextInputLayout.TrailingView>
      <Label
         Text="&#x1F5D3;">     
      </Label>
    </inputLayout:SfTextInputLayout.TrailingView>
 </inputLayout:SfTextInputLayout> 

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Birth date";
inputLayout.LeadingView = new Label() { Text = "\U0001F5D3" };
inputLayout.TrailingView = new Label() { Text = "\U0001F5D3" };
inputLayout.InputView = new Entry();
inputLayout.ContainerType = ContainerType.Outlined;
inputLayout.ShowLeadingView = false;
inputLayout.ShowTrailingView = false;

{% endhighlight %}

{% endtabs %}

![Visibility customization](Custom-Icons-images/ShowLeadingView_ShowTrailingView.gif)

## See Also

[How to align leading and trailing views](http://www.syncfusion.com/support/kb/11046/how-to-vertically-center-align-icons-in-leading-and-trailing-views)
