---
layout: post
title: Zooming and Panning
description: How to add ZoomPan behavior in Essential Xamarin.Forms chart
platform: xamarin
control: Chart
documentation: ug
---

# Zooming and Panning

## Enable zooming

Chart allows you to zoom in to view the data clearly. To enable this feature, add an instance of [`ChartZoomPanBehavior`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior.html) to the [`ChartBehaviors`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior.html) collection property of [`SfChart`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html).

The following properties are used to configure the zooming feature:

* [`EnableZooming`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~EnableZooming.html)—Used to enable/disable the pinch zooming. The default value of this property is true. 
* [`EnableDoubleTap`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~EnableDoubleTap.html)—When you enable this property, you can double tap the chart to reset it to the original size or zoom in by one level.
* [`EnableSelectionZooming`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~EnableSelectionZooming.html)—When this property is set to true, you can double tap and drag to select a range on the chart to be zoomed in.
* [`EnablePanning`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~EnablePanning.html)—Used to enable/disable the panning. The default value of this property is true.

The following code snippet illustrates how to enable zooming.

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

The following code snippet illustrates how to enable the box selection zooming.

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

The following screenshot illustrates the box selection on chart area.

![](zoompan_images/zoompan_img1.png)

The following screenshot illustrates the zoomed area.

![](zoompan_images/zoompan_img2.png)

## Zoom mode

The [`ZoomMode`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~ZoomModeProperty.html) property specifies whether the chart should be allowed to scale along horizontal axis, vertical axis, or both axes. The default value of this property is [`XY`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ZoomMode.html) (both axes).

The following code example illustrates how to restrict the chart to be zoomed only along horizontal axis,

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

## Events

**ZoomStart**

This event is triggered when you start zooming the chart through pinch gesture, and this is a cancelable event. This event contains the following informations:

* [`Axis`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomEventArgs~Axis.html)—The ZoomStart event will be triggered for all the axes in a chart.
* [`CurrentZoomFactor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomEventArgs~CurrentZoomFactor.html)—Used to get the new zoom factor of the corresponding axis.
* [`CurrentZoomPosition`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomEventArgs~CurrentZoomPosition.html)—Used to get the new zoom position of the corresponding axis.
* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomStartEventArgs~Cancel.html)—Used to set the value, which indicates whether the zooming should be canceled.

**ZoomDelta**

This event is triggered while zooming, and this is a cancelable event. This event contains the following informations:

* [`Axis`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomEventArgs~Axis.html)—Instance of an axis whose range is changed because of zooming. This event is triggered for every axis in a chart.
* [`PreviousZoomFactor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomDeltaEventArgs~PreviousZoomFactor.html)—Used to get the previous zoom factor of the axis.
* [`PreviousZoomPosition`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomDeltaEventArgs~PreviousZoomPosition.html)—Used to get the previous zoom position of the axis.
* [`CurrentZoomFactor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomEventArgs~CurrentZoomFactor.html)—Used to get the current zoom factor of the axis.
* [`CurrentZoomPosition`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomEventArgs~CurrentZoomPosition.html)—Used to get the current zoom position of the axis.
* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomDeltaEventArgs~Cancel.html)—Used to set the value, which indicates whether the zooming should be canceled.

**ZoomEnd**

This event is triggered after the zooming has been stopped. This event contains the following informations:

* [`Axis`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomEventArgs~Axis.html)—Instance of an axis whose range is changed because of zooming. This event is triggered for every axis in a chart.
* [`CurrentZoomFactor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomEventArgs~CurrentZoomFactor.html)—The axis zoom factor after zoom.
* [`CurrentZoomPosition`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomEventArgs~CurrentZoomPosition.html)—The axis zoom position after zoom.

**SelectionZoomStart**

This event is triggered when the you start the box selection zooming. This event contains the following information:

* [`ZoomRect`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.Rect.html)—Used to get the initial bounds of the box selection.

**SelectionZoomDelta**

This event is triggered while selecting a region to be zoomed, and this is a cancelable event. This event contains the following information.

* [`ZoomRect`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.Rect.html)—Contains the bounds of the currently selected region.
* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSelectionZoomDeltaEventArgs~Cancel.html)—Used to set the value, which indicates whether the box selection zooming should be canceled.

**SelectionZoomEnd**

This event is triggered after selection zooming ends. This event contains the following information:

* [`ZoomRect`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.Rect.html)—Used to get the final bounds of the zoomed region.

**Scroll**

This event is triggered while panning, and this is a cancelable event. This event contains the following informations:

* [`Axis`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartScrollEventArgs~Axis.html)—Instance of an axis whose range is changed while panning. This event is triggered for every axis in a chart.
* [`ZoomPosition`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartScrollEventArgs~ZoomPosition.html)—The current zoom position of an axis.
* [`Cancel`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartScrollEventArgs~Cancel.html)—Used to set a value, which indicates whether the scrolling should be canceled.

**ResetZoom**

This event is triggered after the chart is reset by double tapping. This event contains the following informations:

* [`Axis`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartResetZoomEventArgs~Axis.html)—Instance of an axis whose range is changed because of this event. This event is triggered for every axis in a chart.
* [`PreviousZoomFactor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartResetZoomEventArgs~PreviousZoomFactor.html)—Used to get the previous zoom factor.
* [`PreviousZoomPosition`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartResetZoomEventArgs~PreviousZoomPosition.html)—Used to get the previous zoom position.

## Methods

Zooming and panning can be performed programmatically with the following methods:

### ZoomIn

The [`ZoomIn`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~ZoomIn.html) method is used to increase the magnification of the plot area to view the data clearly.

{% highlight c# %}

ChartZoomPanBehavior zoomPan = new ChartZoomPanBehavior();

zoomPan.ZoomIn();

{% endhighlight %}

### ZoomOut

The [`ZoomOut`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~ZoomOut.html) method is used to decrease the magnification of the plot area to reset the default view.

{% highlight c# %}

ChartZoomPanBehavior zoomPan = new ChartZoomPanBehavior();

zoomPan.ZoomOut();

{% endhighlight %}

### Zoom

**Zoom(factor)**

This method is used to change the zoom level by using zoom factor.

{% highlight c# %}

ChartZoomPanBehavior zoomPan = new ChartZoomPanBehavior();

zoomPan.Zoom(0.5f);

{% endhighlight %}

**Zoom(Rect)**

This method is used to zoom the chart for a given rectangle value.

{% highlight c# %}

ChartZoomPanBehavior zoomPan = new ChartZoomPanBehavior();

zoomPan.Zoom(new Rect(10, 10, 200, 350));

{% endhighlight %}

**Zoom(chartAxis, cumulativeLevel, origin)**

This method is used to change the zoom level of given axis to the specified level and origin.

{% highlight c# %}

ChartZoomPanBehavior zoomPan = new ChartZoomPanBehavior();

zoomPan.Zoom(axis, 0.5f, 0.5f);

{% endhighlight %}

### ZoomByRange

**ZoomByRange(chartAxis, start, end)**

This method is used to zoom the given axis to the given range.

{% highlight c# %}

ChartZoomPanBehavior zoomPan = new ChartZoomPanBehavior();

zoomPan.ZoomByRange(axis, 20, 25);

{% endhighlight %}

**ZoomByRange(dateTimeAxis, start, end)**

This method is used to zoom the given axis to the given date-time range.

{% highlight c# %}

ChartZoomPanBehavior zoomPan = new ChartZoomPanBehavior();

zoomPan.ZoomByRange(axis, new DateTime(2017,3,1), new DateTime(2017,5,1));

{% endhighlight %}

### ZoomToFactor(chartAxis,zoomPosition,zoomFactor)

The [`ZoomToFactor`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~ZoomToFactor.html) method is used to change the zoom level by using zoom position and zoom factor. The zoom position value specifies the starting point of zooming, and zoom factor value specifies the level of zooming.

{% highlight c# %}

ChartZoomPanBehavior zoomPan = new ChartZoomPanBehavior();

zoomPan.ZoomToFactor(axis, 0.5f, 0.5f);

{% endhighlight %}


### Reset

The [`Reset`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartZoomPanBehavior~Reset.html) method is used to return the plot area back to its original position after zooming.

{% highlight c# %}

ChartZoomPanBehavior zoomPan = new ChartZoomPanBehavior();

zoomPan.Reset();

{% endhighlight %}

