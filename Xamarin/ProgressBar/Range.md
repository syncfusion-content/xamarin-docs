---
layout: post
title: Range
platform: xamarin
control: ProgressBar
documentation: ug
---

# Defining range

Range represents the entire span of the progress bar, and it can be defined using the [`Minimum`](https://help.syncfusion.com/cr/cref_files/xamarin/sfprogressbar/Syncfusion.SfProgressBar.XForms~Syncfusion.XForms.ProgressBar.ProgressBarBase~Minimum.html) and [`Maximum`](https://help.syncfusion.com/cr/cref_files/xamarin/sfprogressbar/Syncfusion.SfProgressBar.XForms~Syncfusion.XForms.ProgressBar.ProgressBarBase~Maximum.html) properties. The default value of range is 0 to 100.

The following code example explains how to customize the range as factor value to the progress bar.

{% tabs %}  

{% highlight xaml %}

<!--Using linear progress bar-->

<progressBar:SfLinearProgressBar x:Name="LinearProgressBar" Minimum="0" Progress="0.5" Maximum="1"/>

<!--Using circular progress bar-->

<progressBar:SfCircularProgressBar x:Name="CircularProgressBar" Minimum="0" Progress="0.5" Maximum="1"/>

{% endhighlight %}

{% highlight c# %}

// Using linear progress bar.

this.LinearProgressBar.Minimum = 0;

this.LinearProgressBar.Maximum = 1;

this.LinearProgressBar.Progress = 0.5;

// Using circular progress bar.

this.CircularProgressBar.Minimum = 0;

this.CircularProgressBar.Maximum = 1;

this.CircularProgressBar.Progress = 0.5;

{% endhighlight %}

{% endtabs %} 

![](progress_images/range.png)
