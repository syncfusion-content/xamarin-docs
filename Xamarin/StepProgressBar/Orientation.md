---
layout: post
title: Orientation in Syncfusion Xamarin.Forms StepProgressBar
description: Explaining about types of orientation in StepProgressBar.
platform: Xamarin
control: StepProgressBar
documentation: ug
---

# Orientation

The StepProgressBar control provides options to change the default orientation, so a multi-step process can be visualized in horizontal or vertical orientation.

## Horizontal 

By default, StepProgressBar step views are displayed horizontally. You can also define the orientation as demonstrated in the following code example.

{% tabs %}

{% highlight xaml %}

    <progressBar:SfStepProgressBar Orientation="Horizontal" />

{% endhighlight %}

{% highlight c# %}

SfStepProgressBar stepProgress = new SfStepProgressBar();
stepProgress.Orientation = StepOrientation.Horizontal;

{% endhighlight %}

{% endtabs %}

![StepProgressBar control has horizontal orientation](overview_images/horizontal.png)

## Vertical

To view the step progress bar control vertically, you can define the vertical orientation as demonstrated in the following code example.

{% tabs %}

{% highlight xaml %}

    <progressBar:SfStepProgressBar Orientation="Vertical" />

{% endhighlight %}

{% highlight c# %}

SfStepProgressBar stepProgress = new SfStepProgressBar();
stepProgress.Orientation = StepOrientation.Vertical;

{% endhighlight %}

{% endtabs %}

![StepProgressBar control has vertical orientation](overview_images/vertical.png)