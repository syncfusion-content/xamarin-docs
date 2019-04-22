---
layout: post
title: Get the touch position in Syncfusion SfChart
description: Get the touch position in SfChart
platform: xamarin
control: Chart
documentation: ug
---

# Get the touch position in chart

ChartBehavior provides the following override methods to get the x and y positions when touch the [`Chart`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~Chart.html).

* [`OnTouchUp`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~OnTouchUp.html) - Called when touch up on the chart area with respective x and y position.
* [`OnTouchMove`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~OnTouchMove.html) - Called when touch move on the chart area with respective x and y position.
* [`OnTouchDown`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~OnTouchDown.html) -  Called when touch down on the chart area with respective x and y position.
* [`DoubleTap`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~DoubleTap.html) - Called when double tap on the chart area with respective x and y position.


{% highlight c# %}

public class ChartTooltipBehaviorExt : ChartTooltipBehavior
{
        
        protected override void OnTouchUp(float pointX, float pointY)
        {
               base.OnTouchUp(pointX, pointY);
        }

        protected override void OnTouchMove(float pointX, float pointY)
        {
               base.OnTouchMove(pointX, pointY);
        }

        protected override void OnTouchDown(float pointX, float pointY)
        {
               base.OnTouchDown(pointX, pointY);
        }

        protected override void DoubleTap(float pointX, float pointY)
        {
               base.DoubleTap(pointX, pointY);
        }
      
}

{% endhighlight  %}