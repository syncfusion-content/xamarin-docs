---
layout: post
title: States in Xamarin Switch Control | Syncfusion
description: Discover the various states supported by the Syncfusion Xamarin Switch (SfSwitch) control, including its elements and features.
platform: Xamarin
control: Switch
documentation: ug
---

# States in Xamarin Switch (SfSwitch)

The SfSwitch control allows you to configure the states as explained in the following sections.

## On State

To switch to the "On" state, tap the switch button or configure the value as shown in the following code examples.
{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch IsOn="True" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch=new SfSwitch();

sfSwitch.IsOn=true;

{% endhighlight %}

{% endtabs %}

![Switch control is displaying on state](images/on.png)

## Off State

The "Off" state is the default state. Tap the switch button or define the state as shown in these code examples.
{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch IsOn="False" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();

sfSwitch.IsOn = false;

{% endhighlight %}

{% endtabs %}

![Switch control displaying off state](images/off.png)

## Indeterminate State

The indeterminate state is useful for indicating ongoing work progress. Use the following code example to load the switch in the indeterminate state by setting the [`IsOn`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html#Syncfusion_XForms_Buttons_SfSwitch_IsOn) property to null.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch IsOn="{x:Null}" AllowIndeterminateState="True" />    

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();

sfSwitch.IsOn = null;

sfSwitch.AllowIndeterminateState = true;

{% endhighlight %}

{% endtabs %}

![Switch control is displaying indeterminate state](images/intermediate.png)

> **Note:** By default, the switch control supports only two states: on and off.

## Disabled On State

Set the [`IsOn`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html#Syncfusion_XForms_Buttons_SfSwitch_IsOn) property to true and the `IsEnabled` property to false to switch to the disabled on state.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch IsOn="True" IsEnabled="False" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();
sfSwitch.IsOn = true;
sfSwitch.IsEnabled = false;

{% endhighlight %}

{% endtabs %}

![Switch control displaying disabled on state](images/disabled-on.png)

## Disabled Off State

Switch to the disabled off state by setting the [`IsOn`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html#Syncfusion_XForms_Buttons_SfSwitch_IsOn) property to false and the `IsEnabled` property to false.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch IsOn="False" IsEnabled="False" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();
sfSwitch.IsOn = false;
sfSwitch.IsEnabled = false;

{% endhighlight %}

{% endtabs %}

![Switch control displaying disabled off state](images/disabled-off.png)

## Disabled Indeterminate State

Enable the disabled indeterminate state to display ongoing work progress. Load the switch in the disabled indeterminate state by setting the [`IsOn`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSwitch.html#Syncfusion_XForms_Buttons_SfSwitch_IsOn) property to null and the `IsEnabled` property to false, as shown below.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch AllowIndeterminateState="True" IsOn="{x:Null}" IsEnabled="False"/>      

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();
sfSwitch.AllowIndeterminateState = true;
sfSwitch.IsOn = null;          
sfSwitch.IsEnabled = false;

{% endhighlight %}

{% endtabs %}

![Switch control displaying disabled indeterminate state](images/disabled-indeterminate.png)
