---
layout: post
title: Grouping for Syncfusion.Xamarin.Forms SfRadioButton
description: Learn how to group the radio buttons inside the SfRadioGroup with its GroupKey support and its orientation customization
platform: Xamarin.Forms
control: SfRadioButton
documentation: ug 
keywords: button, SfRadioButton, RadioButton, SfRadioGroup, GroupKey

---

# Grouping support in SfRadioGroup

## Group Key

The [`GroupKey`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfRadioButton.html#Syncfusion_XForms_Buttons_SfRadioButton_GroupKey) in [`SfRadioButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfRadioButton.html) allows you to group a set of radio buttons present inside any layout. By grouping in this way, you can select only one radio button that comes under same [`GroupKey`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfRadioButton.html#Syncfusion_XForms_Buttons_SfRadioButton_GroupKey) at a time.

* [`CheckedItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfRadioGroupKey.html#Syncfusion_XForms_Buttons_SfRadioGroupKey_CheckedItem) - Gets the current checked item from radio group.

{% tabs %}
{% highlight xaml %}

<ContentPage.Resources>
    <syncfusion:SfRadioGroupKey x:Key="carBrand" />
</ContentPage.Resources>

<FlexLayout Wrap="Wrap" AlignItems="Start" AlignContent="Start">
    <syncfusion:SfRadioButton Text="Honda" GroupKey="{StaticResource carBrand}"/>
    <syncfusion:SfRadioButton Text="Hyundai" GroupKey="{StaticResource carBrand}"/>
    <syncfusion:SfRadioButton Text="Volkswagen" GroupKey="{StaticResource carBrand}"/>
    <syncfusion:SfRadioButton Text="Toyota" GroupKey="{StaticResource carBrand}"/>
    <syncfusion:SfRadioButton Text="Volvo" GroupKey="{StaticResource carBrand}"/>
</FlexLayout>

{% endhighlight %}
{% highlight c# %}

SfRadioGroupKey carBrand = new SfRadioGroupKey();

SfRadioButton honda = new SfRadioButton(){Text = "Honda", GroupKey = carBrand};
SfRadioButton hyundai = new SfRadioButton(){Text = "Hyundai", GroupKey = carBrand};
SfRadioButton volkswagen = new SfRadioButton(){Text = "Volkswagen", GroupKey = carBrand};
SfRadioButton toyota = new SfRadioButton(){Text = "Toyota", GroupKey = carBrand};
SfRadioButton volvo = new SfRadioButton(){Text = "Volvo", GroupKey = carBrand};

FlexLayout flexLayout = new FlexLayout()
{
    Wrap = FlexWrap.Wrap,
    AlignContent = FlexAlignContent.Start,
    AlignItems = FlexAlignItems.Start
};
flexLayout.Children.Add(honda);
flexLayout.Children.Add(hyundai);
flexLayout.Children.Add(volkswagen);
flexLayout.Children.Add(toyota);
flexLayout.Children.Add(volvo);

{% endhighlight %}
{% endtabs %}

![GroupKey support for SfRadioButton](Images/GroupKey.png)

### CheckedChanged event

The [`CheckedChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfRadioGroupKey.html) event of [`SfRadioGroupKey`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfRadioGroupKey.html) occurs when a checked item is changed. The argument contains the following information:

* [`PreviousItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.CheckedChangedEventArgs.html#Syncfusion_XForms_Buttons_CheckedChangedEventArgs_PreviousItem) – Gets the previously checked radio button from group.
* [`CurrentItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.CheckedChangedEventArgs.html#Syncfusion_XForms_Buttons_CheckedChangedEventArgs_CurrentItem) – Gets the currently checked radio button from group.

## SfRadioGroup

[`SfRadioGroup`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfRadioGroup.html) is a container that contains a set of radio buttons. When you select a radio button in a radio group, all other items will be deselected automatically. At a time, you can select only one radio button from the same radio group. It also contains the [`CheckedChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfRadioGroup.html) event and the [`CheckedItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfRadioGroup.html#Syncfusion_XForms_Buttons_SfRadioGroup_CheckedItem) property.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfRadioGroup>
    <syncfusion:SfRadioButton Text="Net banking" />
    <syncfusion:SfRadioButton Text="Debit card" />
    <syncfusion:SfRadioButton Text="Credit card" />
</syncfusion:SfRadioGroup>

{% endhighlight %}
{% highlight c# %}

SfRadioGroup radioGroup = new SfRadioGroup();
SfRadioButton netBanking = new SfRadioButton() {Text = "Net banking"};
SfRadioButton debitCard = new SfRadioButton() {Text = "Debit card"};
SfRadioButton creditCard = new SfRadioButton() {Text = "Credit card"};

radioGroup.Children.Add(netBanking);
radioGroup.Children.Add(debitCard);
radioGroup.Children.Add(creditCard);

{% endhighlight %}
{% endtabs %}

![RadioGroup Image](Images/RadioGroup.png)

### Orientation in SfRadioGroup

`SfRadioGroup` supports horizontal and vertical orientations. By default, SfRadioGroup is rendered with vertical orientation. You can the change the orientation by using the `Orientation` property.

{% tabs %}
{% highlight xaml %}

<SyncfusionButton:SfRadioGroup Orientation="Horizontal">
    <SyncfusionButton:SfRadioButton Text="Net banking" />
    <SyncfusionButton:SfRadioButton Text="Debit card" />
    <SyncfusionButton:SfRadioButton Text="Credit card" />
</SyncfusionButton:SfRadioGroup>

{% endhighlight %}
{% highlight c# %}

SfRadioGroup radioGroup = new SfRadioGroup(){Orientation = StackOrientation.Horizontal};
SfRadioButton netBanking = new SfRadioButton() {Text = "Net banking"};
SfRadioButton debitCard = new SfRadioButton() {Text = "Debit card"};
SfRadioButton creditCard = new SfRadioButton() {Text = "Credit card"};

radioGroup.Children.Add(netBanking);
radioGroup.Children.Add(debitCard);
radioGroup.Children.Add(creditCard);

{% endhighlight %}
{% endtabs %}

![RadioGroup horizontal orientation](Images/Orientation.png)

## See also

[How to get the selected Xamarin.Forms radio button (SfRadioButton)](https://www.syncfusion.com/kb/10914/how-to-get-the-selected-xamarin-forms-radiobutton)