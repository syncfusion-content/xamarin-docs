---
layout: post
title: Zooming and Panning
description: How to add ZoomPan behavior in Essential Xamarin.Forms Chart
platform: xamarin
control: Chart
documentation: ug
---

# Zooming and Panning

## Enable Zooming

Chart allows you to zoom in to view the data clearly. To enable this feature, you need to add an instance of [`ChartZoomPanBehavior`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior.html) to the [`ChartBehaviors`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior.html) collection property of [`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html).

Following properties are used to configure the zooming feature,

* [`EnableZooming`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~EnableZooming.html) – used to enable/disable the pinch zooming. Default value is true. 
* [`EnableDoubleTap`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~EnableDoubleTap.html) – when you enable this property, you can double tap on the chart to reset it to the original size or zoom in by one level.
* [`EnableSelectionZooming`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~EnableSelectionZooming.html) – when this property is set to true, you can double tap and drag to select a range on the chart to be zoomed in.
* [`EnablePanning`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~EnablePanning.html) – used to enable/disable the panning. Default value is true.
* [`MaximumZoomLevel`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~MaximumZoomLevel.html) - used to determine the maximum zoom level of the chart.
* [`SelectionRectStrokeWidth`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~SelectionRectStrokeWidth.html) - used to change the stoke width of selection rectangle 
* [`SelectionRectStrokeColor`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~SelectionRectStrokeColor.html) - used to change the stroke color of selection rectangle.  
* [`SelectionRectStrokeDashArray`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~SelectionRectStrokeDashArray.html) - used to change the stroke dashes of selection rectangle. 
* [`SelectionRectFillColor`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~SelectionRectFillColor.html) - used to change the stroke fill color of selection rectangle. 


Following code snippet illustrates how to enable zooming.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>

	<chart:SfChart.ChartBehaviors>
	
		<chart:ChartZoomPanBehavior/>
		
	</chart:SfChart.ChartBehaviors>
	
</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

ChartZoomPanBehavior zoomPanBehavior = new ChartZoomPanBehavior();

chart.ChartBehaviors.Add(zoomPanBehavior);

{% endhighlight %}

{% endtabs %}

Following code snippet illustrates how to enable the box selection zooming,

{% tabs %} 

{% highlight xaml %}

<chart:SfChart>

	<chart:SfChart.ChartBehaviors>

		<chart:ChartZoomPanBehavior EnableSelectionZooming="True"/>

	</chart:SfChart.ChartBehaviors>

</chart:SfChart>

{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();

ChartZoomPanBehavior zoomPanBehavior = new ChartZoomPanBehavior();

zoomPanBehavior.EnableSelectionZooming = true;

chart.ChartBehaviors.Add(zoomPanBehavior);

{% endhighlight %}

{% endtabs %}

Following screenshot shows the box selection on chart area,

![](zoompan_images/zoompan_img1.png)

Following screenshot shows the zoomed area,

![](zoompan_images/zoompan_img2.png)

## Zoom Mode

The [`ZoomMode`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~ZoomMode.html) property specifies whether chart should be allowed to scale along horizontal axis or vertical axis or along both axis. The default value of [`ZoomMode`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ZoomMode.html) is [`XY`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ZoomMode.html) (both axis).

Following code example illustrates how to restrict the chart to be zoomed only along horizontal axis,

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.ChartBehaviors>

	<chart:ChartZoomPanBehavior ZoomMode="X"/>

</chart:SfChart.ChartBehaviors>

{% endhighlight %}

{% highlight c# %}

ChartZoomPanBehavior zoomPanBehavior = new ChartZoomPanBehavior();

zoomPanBehavior.ZoomMode = ZoomMode.X;

{% endhighlight %}

{% endtabs %}

![](zoompan_images/zoompan_img3.png)

## Auto Interval On Zooming

[`EnableAutoIntervalOnZooming`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartAxis~EnableAutoIntervalOnZooming.html) property determines the update of axis internal based on the current visible range while zooming the chart. Default value of this property is true. If this property is false, the nice internal will not be calculated for new range after zoom in and actual interval will be sustained.

## Events

**ZoomStart**

The [`ZoomStart`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~ZoomStart_EV.html) event is triggered when the user starts zooming the chart through pinch gesture, and this is a cancelable event. The argument contains the following information.

* [`Axis`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomEventArgs~Axis.html) – the zoom start event will be triggered for all the axis in the Chart.
* [`CurrentZoomFactor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomEventArgs~CurrentZoomFactor.html) – used to get the new zoom factor of the corresponding axis.
* [`CurrentZoomPosition`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomEventArgs~CurrentZoomPosition.html) – used to get the new zoom position of the corresponding axis.
* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomStartEventArgs~Cancel.html) – used to set the value indicating whether the zooming should be canceled.

**ZoomDelta**

The [`ZoomDelta`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~ZoomDelta_EV.html) event is triggered while zooming, and this is a cancelable event. The argument contains the following information.

* [`Axis`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomEventArgs~Axis.html) – Instance of the axis whose range is changed because of zooming. This event is triggered for each axis in the chart.
* [`PreviousZoomFactor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomDeltaEventArgs~PreviousZoomFactor.html) – used to get the previous zoom factor of the axis.
* [`PreviousZoomPosition`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomDeltaEventArgs~PreviousZoomPosition.html) – used to get the previous zoom position of the axis.
* [`CurrentZoomFactor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomEventArgs~CurrentZoomFactor.html) – used to get the current zoom factor of the axis.
* [`CurrentZoomPosition`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomEventArgs~CurrentZoomPosition.html) – used to get the current zoom position of the axis.
* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomDeltaEventArgs~Cancel.html) – used to set the value indicating whether the zooming should be canceled.

**ZoomEnd**

The [`ZoomEnd`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~ZoomEnd_EV.html) event is triggered after the zooming is stopped. The argument contains the following information.

* [`Axis`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomEventArgs~Axis.html) – Instance of the axis whose range is changed because of zooming. This event is triggered for each axis in the chart.
* [`CurrentZoomFactor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomEventArgs~CurrentZoomFactor.html) – the axis zoom factor after zoom.
* [`CurrentZoomPosition`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomEventArgs~CurrentZoomPosition.html) - the axis zoom position after zoom.

**SelectionZoomStart**

The [`SelectionZoomStart`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~SelectionZoomStart_EV.html) event is triggered when the user starts the box selection zooming. The argument contains the following information.

* [`ZoomRect`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionZoomEventArgs~ZoomRect.html) – used to get the initial bounds of the box selection.

**SelectionZoomDelta**

The [`SelectionZoomDelta`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~SelectionZoomDelta_EV.html) event is triggered while selecting a region to be zoomed, and this is a cancelable event. The argument contains the following information.

* [`ZoomRect`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionZoomEventArgs~ZoomRect.html) – contains the bounds of the currently selected region.
* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionZoomDeltaEventArgs~Cancel.html) – used to set the value indicating whether the box selection zooming should be canceled.

**SelectionZoomEnd**

The [`SelectionZoomEnd`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~SelectionZoomEnd_EV.html) event is triggered after selection zooming ends. The argument contains the following information.

* [`ZoomRect`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionZoomEventArgs~ZoomRect.html) – used to get the final bounds of the zoomed region.

**Scroll**

The [`Scroll`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~Scroll_EV.html) event is triggered while panning, and this is a cancelable event. The argument contains the following information.

* [`Axis`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartScrollEventArgs~Axis.html) – Instance of the axis whose range is changed while panning. This event is triggered for each axis in the chart.
* [`ZoomPosition`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartScrollEventArgs~ZoomPosition.html) – the current zoom position of the axis.
* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartScrollEventArgs~Cancel.html) – used to set a value indicating whether the scrolling should be canceled.

**ResetZoom**

The [`ResetZoom`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart~ResetZoom_EV.html) event is triggered after the chart is reset on double tap. The argument contains the following information.

* [`Axis`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartResetZoomEventArgs~Axis.html) – Instance of the axis whose range is changed because of this event. This event is triggered for each axis in the chart.
* [`PreviousZoomFactor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartResetZoomEventArgs~PreviousZoomFactor.html) – used to get the previous zoom factor.
* [`PreviousZoomPosition`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartResetZoomEventArgs~PreviousZoomPosition.html) – used to get the previous zoom position.

## Methods

Zooming and panning can be performed programmatically with the following methods:

### ZoomIn

[`ZoomIn`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~ZoomIn.html) method is used to increase the magnification of the plot area to view the data clearly.

{% highlight c# %}

ChartZoomPanBehavior zoomPan = new ChartZoomPanBehavior();

zoomPan.ZoomIn();

{% endhighlight %}

### ZoomOut

[`ZoomOut`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~ZoomOut.html) is used to decrease the magnification of the plot area to reset the default view.

{% highlight c# %}

ChartZoomPanBehavior zoomPan = new ChartZoomPanBehavior();

zoomPan.ZoomOut();

{% endhighlight %}

### Zoom

**Zoom(factor)**

[`Zoom(factor)`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~Zoom(Single).html) method is used to change the zoom level by using zoom factor.

{% highlight c# %}

ChartZoomPanBehavior zoomPan = new ChartZoomPanBehavior();

zoomPan.Zoom(0.5f);

{% endhighlight %}

**Zoom(Rect)**

[`Zoom(Rect)`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~Zoom(Rect).html) method is used to zoom the chart for a given rectangle value. Create an instance of Rect by passing [`Top`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.Rect~Top.html), [`Left`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.Rect~Left.html), [`Bottom`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.Rect~Bottom.html), and [`Right`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.Rect~Right.html) positions and pass it to zoom method.

{% highlight c# %}

ChartZoomPanBehavior zoomPan = new ChartZoomPanBehavior();

zoomPan.Zoom(new Rect(10, 10, 200, 350));

{% endhighlight %}

**Zoom(chartAxis, cumulativeLevel, origin)**

[`Zoom(chartAxis, cumulativeLevel, origin)`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~Zoom(ChartAxis,Single,Single).html) method is used to change the zoom level of given axis to the specified level and origin.

{% highlight c# %}

ChartZoomPanBehavior zoomPan = new ChartZoomPanBehavior();

zoomPan.Zoom(axis, 0.5f, 0.5f);

{% endhighlight %}

### ZoomByRange

**ZoomByRange(chartAxis, start, end)**

[`ZoomByRange(chartAxis, start, end)`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~ZoomByRange(ChartAxis,Double,Double).html) method is used to zoom the given axis to the given range.

{% highlight c# %}

ChartZoomPanBehavior zoomPan = new ChartZoomPanBehavior();

zoomPan.ZoomByRange(axis, 20, 25);

{% endhighlight %}

**ZoomByRange(dateTimeAxis, start, end)**

[`ZoomByRange(dateTimeAxis, start, end)`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~ZoomByRange(DateTimeAxis,DateTime,DateTime).html) method is used to zoom the given axis to the given date time range.

{% highlight c# %}

ChartZoomPanBehavior zoomPan = new ChartZoomPanBehavior();

zoomPan.ZoomByRange(axis, new DateTime(2017,3,1), new DateTime(2017,5,1));

{% endhighlight %}

### ZoomToFactor(chartAxis,zoomPosition,zoomFactor)

[`ZoomToFactor`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~ZoomToFactor.html) method is used to change the zoom level by using zoom position and zoom factor. Zoom position value specifies the starting point of zooming, and zoom factor value specifies the level of zooming.

{% highlight c# %}

ChartZoomPanBehavior zoomPan = new ChartZoomPanBehavior();

zoomPan.ZoomToFactor(axis, 0.5f, 0.5f);

{% endhighlight %}


### Reset

[`Reset`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~Reset.html) method is used to return the plot area back to its original position after zooming.

{% highlight c# %}

ChartZoomPanBehavior zoomPan = new ChartZoomPanBehavior();

zoomPan.Reset();

{% endhighlight %}

### OnScaleStart(float manipulationX, float manipulationY, float scaleFactor)

[`OnScaleStart`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~OnScaleStart.html) method is called when the user started scaling the chart through pinch zooming. The argument contains the information about Manipulation and  scale factor.

{% highlight c# %}


{% endhighlight %}

### OnScaleDelta(float manipulationX, float manipulationY, float scaleFactor)

[`OnScaleDelta`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~OnScaleDelta.html) method is calling when the user scaling the chart through pinch zooming. The argument contains the information about Manipulation points and scale factor.

{% highlight c# %}

public class ChartZoomExt:ChartZoomPanBehavior
{

        protected override void OnScaleDelta(float manipulationX, float manipulationY, float scaleFactor)
        {
            base.OnScaleDelta(manipulationX, manipulationY, scaleFactor);
        }

}

{% endhighlight %}

### OnScaleEnd(float manipulationX, float manipulationY,float scaleFactor)

[`OnScaleEnd`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~OnScaleEnd.html) method is called after the  scaling ends. The argument contains the information about Manipulation points and scale factor.

{% highlight c# %}

public class ChartZoomExt:ChartZoomPanBehavior
{
        protected override void OnScaleEnd(float manipulationX, float manipulationY, float scaleFactor)
        {
            base.OnScaleEnd(manipulationX, manipulationY, scaleFactor);
        }
}

{% endhighlight %}

### OnScroll( float pointX, float pointY, float distanceX, float distanceY)

[`OnScroll`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~OnScroll.html) method is called when while panning and the arguments contains the following properties.

{% highlight c# %}

  protected override void OnScroll(float pointX, float pointY, float distanceX, float distanceY)
  {
            base.OnScroll(pointX, pointY, distanceX, distanceY);
  }

{% endhighlight %}

