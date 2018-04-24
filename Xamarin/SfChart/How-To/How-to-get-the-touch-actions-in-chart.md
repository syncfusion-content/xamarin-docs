---
layout: post
title: How to get the touch actions in chart 
description:  get the touch actions in chart
platform: xamarin
control: Chart
documentation: ug
---

ChartBehavior provides the below override methods to get the corresponding touch point while on touch actions and it can be possible by extending any of the Chart behavior class.

* [`OnTouchUp`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~OnTouchUp.html)

* [`OnTouchMove`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~OnTouchMove.html)

* [`OnTouchDown`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~OnTouchDown.html)

* [`DoubleTap`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior~DoubleTap.html)

Here, for example, you can get the user touch points using above methods by extending ChartTooltipBehavior. 

{% highlight c# %}

public class ChartTooltipBehaviorExt : ChartTooltipBehavior
{
        
        protected override void OnTouchUp(float pointX, float pointY)
        {
            //you can perform any operations 
        }

        protected override void OnTouchMove(float pointX, float pointY)
        {
            //you can perform any operations 
        }

        protected override void OnTouchDown(float pointX, float pointY)
        {
            //you can perform any operations 
        }

        protected override void DoubleTap(float pointX, float pointY)
        {
           //you can perform any operations 
        }
      
}

{% endhighlight  %}

