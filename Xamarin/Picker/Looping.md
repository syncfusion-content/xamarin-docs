---
layout: post
title: Looping in Xamarin Picker control | Syncfusion
description: Learn here all about Looping support in Syncfusion Xamarin Picker (SfPicker) control, its elements and more.
platform: Xamarin
control: Picker
documentation: ug
---

# Looping in Xamarin Picker (SfPicker)

The Looping support is used to automatically navigate the first item to repeat the list of items after reached the last item. Each forward iteration is followed by a backward iteration in the picker control. This can be achieved by [`EnableLooping`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPicker.XForms.SfPicker.html#Syncfusion_SfPicker_XForms_SfPicker_EnableLooping) property.

## EnableLooping

The looping support is achieved by setting the [`EnableLooping`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPicker.XForms.SfPicker.html#Syncfusion_SfPicker_XForms_SfPicker_EnableLooping) property to true.

{% tabs %}

{% highlight xaml %}

<ContentPage.BindingContext>

<local:ColorInfo />

</ContentPage.BindingContext>

<ContentPage.Content>

<syncfusion:SfPicker

x:Name="picker"

HeaderText="Select a Color"

EnableLooping="True"

ItemsSource="{Binding Colors}" />

</ContentPage.Content>

</ContentPage>

{% endhighlight %}

{% highlight c# %}

SfPicker picker = new SfPicker();

ColorInfo info = new ColorInfo();

picker.ItemsSource = info.Colors;

// Enable Looping in carousel control
picker.EnableLooping = true;

{% endhighlight %}

{% endtabs %}

![Looping Image](images/Looping.png)

You can find the complete Looping sample from this [link.](https://github.com/SyncfusionExamples/xamarin-sfpicker-examples/tree/master/Samples/Looping)

## How to restrict Looping in a particular column of the picker

The looping support can be restricted in a particular column of the picker by setting the [`EnableLooping`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPicker.XForms.SfPicker.html#Syncfusion_SfPicker_XForms_SfPicker_EnableLooping) of ColumnLoaded event argument to false.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPicker 
    x:Name="picker" 
    OnColumnLoaded="Picker_OnColumnLoaded"/>

{% endhighlight %}

{% highlight c# %}

private void Picker_OnColumnLoaded(object sender, Syncfusion.SfPicker.XForms.ColumnLoadedEventArgs e)
        {
          //restrict an Looping in Column 1
           if(e.Column == 1)
            {
                e.EnableLooping = false;
            }
        }

{% endhighlight %}

{% endtabs %}

![ColumnEnableLooping Image](images/ColumnEnableLooping.png)

You can find the sample from this [link.](https://github.com/SyncfusionExamples/xamarin-sfpicker-examples/tree/master/Samples/ColumnAutoReverse)

N> You can refer to our [Xamarin Picker](https://www.syncfusion.com/xamarin-ui-controls/xamarin-picker) feature tour page for its groundbreaking feature representations. You can also explore our [Xamarin.Forms Picker example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/Picker) to knows the functionalities of each feature.