---
layout: post
title: Looping support for Syncfusion.Xamarin.Forms SfTimePicker
description: Enable Looping support in Syncfusion.Xamarin.Forms SfTimePicker control to repeat the list of items.
platform: Xamarin
control: SfTimePicker
documentation: ug
---

# Looping Support in SfTimePicker

The Looping support is used to automatically navigate the first item to repeat the list of items after reached the last item. Each forward iteration is followed by a backward iteration in the time picker control. This can be achieved by using the `EnableLooping` property.

## EnableLooping

The looping support is achieved by setting the `EnableLooping` property to true.

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
