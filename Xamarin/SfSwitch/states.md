---
layout: post
title: States in Syncfusion SfSwitch Xamarin.Forms
description: Explaining about states in SfSwitch
platform: Xamarin
control: Switch
documentation: ug
---

# States

Switch allows you to configure the states as explained in the following sections.

## On

You can switch to on state by tapping the switch button or by setting a value as demonstrated in the following code example.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch IsOn="True" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch=new SfSwitch();

sfSwitch.IsOn=true;

{% endhighlight %}

{% endtabs %}

![switch control is displaying on state](images/on.png)

## Off

This is the default state. You can switch to off state by tapping the switch button or by defining as demonstrated in the following code example.

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfSwitch IsOn="False" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();

sfSwitch.IsOn = false;

{% endhighlight %}

{% endtabs %}

![switch control displaying off state](images/off.png)

## Indeterminate

The indeterminate state can be enabled when you need to display the work progress. The following code example demonstrates how to load the switch in indeterminate state by setting the IsOn property to null.

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

![switch conrol is displaying indeterminate state](images/intermediate.png)

N> By default, the switch control has only two states: on and off.

## Disabled On

You can switch to disabled on state by setting the `IsOn` property as true and `IsEnabled` property as false.

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

![switch control displaying disabled on state](images/disabled-on.png)

## Disabled Off

You can switch to disabled off state by setting the `IsOn` property as false and `IsEnabled` property as false.

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

![switch control displaying disabled off state](images/disabled-off.png)

## Disabled Indeterminate

The disabled indeterminate state can be enabled when you need to display the work progress .The below code example demonstrates loading the switch in disabled indeterminate state by setting `IsOn` property value as null and `IsEnabled` property as false.

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

![switch conrol displaying disabled indeterminate state](images/disabled-indeterminate.png)
