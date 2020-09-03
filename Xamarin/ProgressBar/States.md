---
layout: post
title: States
description: States.
platform: xamarin
control: ProgressBar
documentation: ug
---

# States

You can configure the states of the progress bar control depending on the usage.

## Determinate

This is the default state. You can use it when the progress estimation is known.

## Indeterminate

By enabling the [`IsIndeterminate`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.ProgressBarBase.html#Syncfusion_XForms_ProgressBar_ProgressBarBase_IsIndeterminate) property, the state of the progress bar can be changed to indeterminate when the progress cannot be estimated or is not being calculated. It can be combined with determinate mode to know that the application is estimating progress before the actual progress starts.

{% tabs %} 

{% highlight xaml %} 

<!--Using linear progress bar-->

<progressBar:SfLinearProgressBar IsIndeterminate="True"/>

<!--Using circular progress bar-->

<progressBar:SfCircularProgressBar IsIndeterminate="True"/>

{% endhighlight %}

{% highlight c# %}

// Using linear progress bar. 

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar { IsIndeterminate = true};

// Using circular progress bar.

SfCircularProgressBar circularProgressBar = new SfCircularProgressBar { IsIndeterminate = true };

{% endhighlight %}

{% endtabs %} 

## Buffer

The secondary task’s progress can be defined using the [`SecondaryProgress`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.SfLinearProgressBar.html#Syncfusion_XForms_ProgressBar_SfLinearProgressBar_SecondaryProgress) property as demonstrated in the following code sample.

{% tabs %} 

{% highlight xaml %} 

<progressBar:SfLinearProgressBar x:Name="LinearProgressBar" Progress="25" SecondaryProgress="75"/>

{% endhighlight %}

{% highlight c# %}

this.LinearProgressBar.Progress = 75;

this.LinearProgressBar.SecondaryProgress = 25;

{% endhighlight %}

{% endtabs %} 

![](overview_images/Buffer.png)
