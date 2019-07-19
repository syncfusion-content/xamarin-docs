---
layout: post
title: Grouping for Syncfusion.Xamarin.Forms SfRadioButton
description: Learn how to group the SfRadioButton
platform: Xamarin.Forms
control: SfRadioButton
documentation: ug 
keywords: button, SfRadioButton, RadioButton, SfRadioGroup, GroupKey

---

# Grouping

## Group Key

The [`GroupKey`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfRadioButton~GroupKey.html) in [`SfRadioButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfRadioButton.html) allows you to group a set of radio buttons present inside any layout. By grouping in this way, you can select only one radio button that comes under same [`GroupKey`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfRadioButton~GroupKey.html) at a time.

* [`CheckedItem`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfRadioGroup~CheckedItem.html) - Gets the current checked item from radio group.

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

SfRadioButton honda = new SfRadioButton();
honda.Text = "Honda";
honda.GroupKey = carBrand;
SfRadioButton hyundai = new SfRadioButton();
hyundai.Text = "Hyundai";
hyundai.GroupKey = carBrand;
SfRadioButton volkswagen = new SfRadioButton();
volkswagen.Text = "Volkswagen";
volkswagen.GroupKey = carBrand;
SfRadioButton toyota = new SfRadioButton();
toyota.Text = "Toyota";
toyota.GroupKey = carBrand;
SfRadioButton volvo = new SfRadioButton();
volvo.Text = "Volvo";
volvo.GroupKey = carBrand;

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

The [`CheckedChanged`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfRadioGroupKey~CheckedChanged_EV.html) event of [`SfRadioGroupKey`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfRadioGroupKey.html) occurs when a checked item is changed. The argument contains the following information:

* [`PreviousItem`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.CheckedChangedEventArgs~PreviousItem.html) – Gets the previously checked radio button from group.
* [`CurrentItem`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.CheckedChangedEventArgs~CurrentItem.html) – Gets the currently checked radio button from group.

## SfRadioGroup

[`SfRadioGroup`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfRadioGroup.html) is a container that contains a set of radio buttons. When you select a radio button in a radio group, all other items will be deselected automatically. At a time, you can select only one radio button from the same radio group. It also contains the [`CheckedChanged`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfRadioGroupKey~CheckedChanged_EV.html) event and the [`CheckedItem`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfRadioGroup~CheckedItem.html) property.

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
SfRadioButton netBanking = new SfRadioButton();
netBanking.Text = "Net banking";
SfRadioButton debitCard = new SfRadioButton();
debitCard.Text = "Debit card";
SfRadioButton creditCard = new SfRadioButton();
creditCard.Text = "Credit card";

radioGroup.Children.Add(netBanking);
radioGroup.Children.Add(debitCard);
radioGroup.Children.Add(creditCard);

{% endhighlight %}
{% endtabs %}

![RadioGroup Image](Images/RadioGroup.png)
