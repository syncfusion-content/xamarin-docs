---
layout: post
title: Adding Multiple trackball in Syncfusion SfChart
description: Adding Multiple trackball in SfChart
platform: xamarin
control: Chart
documentation: ug
---

## Adding Multiple trackball in SfChart

[`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html) allows the user to activate multiple trackballs in chart area by adding two instances of trackball behavior to chart and by using the Show method. Each trackball will be interacting separately by using [`HitTest`]() method which returns the nearest trackball that contains the touch point and the touch override methods of trackball behavior, but these Multiple trackballs having effect only when the [`ActivationMode`] is set as [`None`]. 

The following code sample demonstrates this:

{% highlight xaml %}

<chart:SfChart.ChartBehaviors>
       <local:TrackballBehaviorExt ActivationMode="None" x:Name="TrackballBehavior1" />
       <local:TrackballBehaviorExt ActivationMode="None" x:Name="TrackballBehavior2" />
</chart:SfChart.ChartBehaviors>

{% endhighlight %}

{% highlight c# %}

TrackballBehavior1.Show(pointX, pointY);
TrackballBehavior2.Show(pointX, pointY);

{% endhighlight %}

{% highlight c# %}

public class TrackballBehaviorExt : ChartTrackballBehavior
{
    bool isActivate = false;
                
    protected override void OnTouchDown(float pointX, float pointY)
    {
        if (HitTest(pointX, pointY))
        {
            isActivate = true;
            base.OnTouchDown(pointX, pointY);
        }
    }

    protected override void OnTouchMove(float pointX, float pointY)
    {
        if (isActivate)
        {
            Show(pointX, pointY);
            base.OnTouchMove(pointX, pointY);
        }
    }

    protected override void OnTouchUp(float pointX, float pointY)
    {
        isActivate = false;
    }
}

{% endhighlight %}