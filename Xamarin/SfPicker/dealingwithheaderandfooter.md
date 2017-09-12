---
layout: post
title: Dealing with Header and Footer of Syncfusion Picker control for Xamarin.Forms
description: Dealing with Header and Footer of Picker control
platform: Xamarin
control: Picker
documentation: ug
---

# Dealing with Header and Footer

This section explains about the header and footer customization of SfPicker.

## Enable or Disable Header 

SfPicker allows enabling or disabling the header section by setting `SfPicker.ShowHeader` property to True or False. Default value of `SfPicker.ShowHeader` property is True.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPicker

x:Name="sfpicker" ShowColumnHeader="False"

HeaderText="Select a Date" />

{% endhighlight %}

{% highlight c# %}

picker.ShowHeader = false;

{% endhighlight %}
{% endtabs %}

## Set Custom Header 

SfPicker allows providing custom text to Header of SfPicker by setting `SfPicker.HeaderText` property. Default value of `SfPicker.HeaderText` property is Null.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPicker

x:Name="sfpicker"

HeaderText="Select a Date" />

{% endhighlight %}

{% highlight c# %}

picker.HeaderText = "Select a Date";

{% endhighlight %}
{% endtabs %}

## Header Customization

SfPicker allows customizing Background, TextColor and Fonts.

### Background

Header background color can be customized  by setting `SfPicker.HeaderBackgroundColor` property of SfPicker.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPicker

x:Name="picker"

HeaderBackgroundColor="SkyBlue"

HeaderText="Select a Date" />

{% endhighlight %}

{% highlight c# %}

picker.HeaderBackgroundColor = Color.SkyBlue;

{% endhighlight %}
{% endtabs %}

### Text Color 

Header text color can be customized by setting `SfPicker.HeaderTextColor` property of SfPicker.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPicker

x:Name="picker"

HeaderTextColor="Red"

HeaderText="Select a Date" />

{% endhighlight %}

{% highlight c# %}

picker.HeaderTextColor = Color.Red; 

{% endhighlight %}
{% endtabs %}

### Font 

This section explains about the customization of Header text of Font.

#### 	FontFamily

Header text FontFamily can be customized by setting `SfPicker.HeaderFontFamily` property of SfPicker.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPicker

x:Name="picker"

HeaderFontFamily="Arial"

HeaderText="Select a Date" />

{% endhighlight %}

{% highlight c# %}

picker.HeaderFontFamily = "Arial";

{% endhighlight %}
{% endtabs %}

#### 	FontSize

Header text FontSize can be customized by setting `SfPicker.HeaderFontSize` property of SfPicker.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPicker

x:Name="picker"

HeaderFontSize="18"

HeaderText="Select a Date" /> 

{% endhighlight %}

{% highlight c# %}

picker.HeaderFontSize = 18;

{% endhighlight %}
{% endtabs %}   

#### 	FontAttribute

Header text FontAttribute can be customized by setting `SfPicker.HeaderFontAttribute` property of SfPicker.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPicker

x:Name="picker"

HeaderFontAttribute="Italic"

HeaderText="Select a Date" />

{% endhighlight %}

{% highlight c# %}

picker.HeaderFontAttribute = FontAttributes.Italic;

{% endhighlight %}
{% endtabs %}

## Enable or Disable Footer 

SfPicker allows enabling or disabling the footer section by setting `SfPicker.ShowFooter` property to True or False. Default value of `SfPicker.ShowFooter` property is False.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPicker

x:Name="sfpicker" ShowFooter="True"

/>

{% endhighlight %}

{% highlight c# %}

picker.ShowFooter = true;

{% endhighlight %}
{% endtabs %}

## Set Custom Footer

SfPicker allows providing custom view to Footer of SfPicker by setting `SfPicker.FooterView` property. Default value of `SfPicker.FooterView` property is Null.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPicker x:Name="sfpicker" ShowFooter="True">

<syncfusion:SfPicker.FooterView>

<Grid>

<Label Text="Cancel" TextColor="Red" />

</Grid>

</syncfusion:SfPicker.FooterView>

</syncfusion:SfPicker>

{% endhighlight %}

{% highlight c# %}

picker.ShowFooter = true;

Grid gridlayout = new Grid();

gridlayout.Children.Add(new Button() { Text = "Ok", TextColor = Color.Red });

picker.FooterView = gridlayout;

{% endhighlight %}
{% endtabs %}

## Perform validation with default validation Button

SfPicker allows performing validation based on Ok or Cancel button by hooking `SfPicker.OkButtonClicked` and `SfPicker.CancelButtonClicked`. In this event from the `SelectionChangedEvent` Argument current selected items can be obtained.


{% tabs %}
{% highlight xaml %}

<syncfusion:SfPicker

x:Name="sfpicker"

CancelButtonClicked="sfpicker_CancelButtonClicked"

OkButtonClicked="sfpicker_OkButtonClicked"

ShowFooter="True" />

{% endhighlight %}

{% highlight c# %}

picker.OkButtonClicked += sfpicker_OkButtonClicked;

picker.CancelButtonClicked += sfpicker_CancelButtonClicked;

{% endhighlight %}
{% endtabs %}
