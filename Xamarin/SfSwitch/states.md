---
layout: post
title: States in Syncfusion SfSwitch Xamarin.Forms.
description: Explaining about states in SfSwitch.
platform: Xamarin
control: Switch
documentation: ug
---

## States

Switch allows you to configure the states as explained in the below sections.

### On

You can switch to on state by tapping the switch button or by setting the value as shown in the below code example.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSwitch IsOn="True" />

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch=new SfSwitch();

sfSwitch.IsOn=true;

{% endhighlight %}

{% endtabs %}

![switch control displaying on state](images/on.png)

### Off

This is the default state. You can switch to off state by tapping the switch button or by defining as shown in the below code example.

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

### Indeterminate

The indeterminate state can be enabled when you need to display the work progress .The below code example demonstrates loading the switch in indeterminate state by setting IsOn property value as null.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSwitch AllowIndeterminateState="True" IsOn="{x:Null}" />        

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();

sfSwitch.IsOn = null;

sfSwitch.AllowIndeterminateState = true;

{% endhighlight %}

{% endtabs %}

![switch conrol displaying indeterminate state](images/intermediate.png)

N> By default there will be only two states, on and off.

### Disabled On

You can switch to on state by tapping the switch button or by setting the value as shown in the below code example.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSwitch IsOn="True" IsEnabled="{False"}/>

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch=new SfSwitch();

sfSwitch.IsOn=true;

{% endhighlight %}

{% endtabs %}

![switch control displaying on state](images/on.png)

### Disbaled Off

You can switch to off state by tapping the switch button or by defining as shown in the below code example.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSwitch IsOn="False" IsEnabled="{False"//>

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();

sfSwitch.IsOn = false;

{% endhighlight %}

{% endtabs %}

![switch control displaying off state](images/off.png)

### Disabled Indeterminate

The indeterminate state can be enabled when you need to display the work progress .The below code example demonstrates loading the switch in indeterminate state by setting IsOn property value as null.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfSwitch AllowIndeterminateState="True" IsOn="{x:Null}"   IsEnabled="{False"/>        

{% endhighlight %}

{% highlight c# %}

SfSwitch sfSwitch = new SfSwitch();

sfSwitch.IsOn = null;

sfSwitch.AllowIndeterminateState = true;

{% endhighlight %}

{% endtabs %}

![switch conrol displaying indeterminate state](images/intermediate.png)
