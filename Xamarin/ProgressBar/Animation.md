---
layout: post
title: Animation
platform: xamarin
control: ProgressBar
documentation: ug
---

# Animation

The progress bar provides animation support to visualize the progress value changes in an interactive way. 

The following properties are used to define the duration of animation for the specific states:

* [`AnimationDuration`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.ProgressBarBase.html#Syncfusion_XForms_ProgressBar_ProgressBarBase_AnimationDuration): Represents animation duration of the determinate state’s progress indicator.
* [`SecondaryAnimationDuration`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.SfLinearProgressBar.html#Syncfusion_XForms_ProgressBar_SfLinearProgressBar_SecondaryAnimationDuration): Represents animation duration of the determinate state’s secondary progress indicator.
* [`IndeterminateAnimationDuration`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.ProgressBarBase.html#Syncfusion_XForms_ProgressBar_ProgressBarBase_IndeterminateAnimationDuration): Represents animation duration of the indeterminate state’s indicator.

## Easing effects

The [`EasingEffect`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.ProgressBarBase.html#Syncfusion_XForms_ProgressBar_ProgressBarBase_EasingEffect) property allows you specify the transfer function that controls animation speed when they run. 

The following code sample demonstrates the [`CubicInOut`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.EasingEffects.html) easing function of the linear progress bar.

{% tabs %} 

{% highlight xaml %}
<progressBar:SfLinearProgressBar Progress="75" EasingEffect="CubicInOut">

</progressBar:SfLinearProgressBar>

{% endhighlight %}

{% highlight c# %}

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();

linearProgressBar.Progress = 75;

linearProgressBar.EasingEffect = EasingEffects.CubicInOut;

{% endhighlight %}

{% endtabs %} 

The [`SetProgress()`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.ProgressBarBase.html#Syncfusion_XForms_ProgressBar_ProgressBarBase_SetProgress_System_Double_System_Int32_Xamarin_Forms_Easing_) method in the progress bar is used to set progress value along with animation duration and easing effect applicable for the specific method call.

{% highlight c# %}

void SetProgress(double progress, int animationDuration, Easing easingEffect)

{% endhighlight %}

N> The animationDuration and easingEffect parameters will not affect the configuration of the [`AnimationDuration`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.ProgressBarBase.html#Syncfusion_XForms_ProgressBar_ProgressBarBase_AnimationDuration) and [`EasingEffect`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.ProgressBarBase.html#Syncfusion_XForms_ProgressBar_ProgressBarBase_EasingEffect) properties.

## Indeterminate Easing Effects

The [`IndeterminateEasingEffect`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.ProgressBarBase.html#Syncfusion_XForms_ProgressBar_ProgressBarBase_IndeterminateEasingEffect) property allows you to specify a transfer function for indeterminate state, which controls animation speed when they run.

The following code sample demonstrates the [`BounceIn`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ProgressBar.IndeterminateEasingEffects.html) easing function of the linear progress bar.

{% tabs %} 

{% highlight xaml %}
<progressBar:SfLinearProgressBar IsIndeterminate="True" IndeterminateEasingEffect="BounceIn">

</progressBar:SfLinearProgressBar>

{% endhighlight %}

{% highlight c# %}

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();

linearProgressBar.IsIndeterminate = true;

linearProgressBar.IndeterminateEasingEffect = IndeterminateEasingEffects.BounceIn;

{% endhighlight %}

{% endtabs %} 