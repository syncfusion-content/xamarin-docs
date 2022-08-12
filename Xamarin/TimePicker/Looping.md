---
layout: post
title: Enable Looping in Xamarin TimePicker control | Syncfusion
description: Learn here all about Enable Looping support in Syncfusion Xamarin TimePicker (SfTimePicker) control and more.
platform: Xamarin
control: SfTimePicker
documentation: ug
---

# Enable Looping in Xamarin TimePicker (SfTimePicker)

The Looping support is used to automatically navigate the first item to repeat the list of items after reached the last item. Each forward iteration is followed by a backward iteration in the time picker control. This can be achieved by using the [`EnableLooping`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_EnableLooping) property.

## EnableLooping

The looping support is achieved by setting the [`EnableLooping`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Pickers.PickerHelper.PickerBase.html#Syncfusion_XForms_Pickers_PickerHelper_PickerBase_EnableLooping) property to true.

{% tabs %}

{% highlight xaml %}

<ContentPage.Content>

<syncfusion:SfTimePicker

x:Name="timePicker" EnableLooping="True" />

</ContentPage.Content>

</ContentPage>

{% endhighlight %}

{% highlight c# %}

SfDatePicker datePicker = new SfDatePicker();

datePicker.EnableLooping = true;

{% endhighlight %}

{% endtabs %}

![Looping Image](images/Looping.png)
