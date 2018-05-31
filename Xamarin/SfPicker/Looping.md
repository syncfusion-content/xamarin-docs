---
layout: post
title: Demonstrate Looping support using SfPicker of Syncfusion Picker control for Xamarin.Forms
description: Looping support of SfPicker control
platform: Xamarin
control: Picker
documentation: ug
---

# Looping

The Looping support is used to automatically navigate the first item to repeat the list of items after reached the last item. Each forward iteration is followed by a backward iteration in the picker control. This can be achieved by `EnableLooping` property.

## EnableLooping

The looping support is achieved by setting the `EnableLooping` property to true.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPicker 
    x:Name="picker" 
    EnableLooping="True"/>

{% endhighlight %}

{% highlight c# %}

SfPicker picker = new SfPicker();
// Enable Looping in carousel control
picker.EnableLooping = true;

{% endhighlight %}

{% endtabs %}

# How to restrict Looping in a particular column of the picker

The looping support can be restricted in a particular column of the picker by setting the `EnableLooping` of ColumnLoaded event argument to false.

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