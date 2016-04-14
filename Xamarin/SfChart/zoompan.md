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

Chart allows you to zoom in to view the data clearly. To enable this feature, you need to add an instance of `ChartZoomPanBehavior` to the `ChartBehaviors` collection property of `SfChart`.

Following properties are used to configure the zooming feature,

* `EnableZooming` – used to enable/disable the pinch zooming. Default value is true. 
* `EnableDoubleTap` – when you enable this property, you can double tap on the chart to reset it to the original size or zoom in by one level.
* `EnableSelectionZooming` – when this property is set to true, you can double tap and drag to select a range on the chart to be zoomed in.
* `EnablePanning` – used to enable/disable the panning. Default value is true.

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

The `ZoomMode` property specifies whether chart should be allowed to scale along horizontal axis or vertical axis or along both axis. The default value of `ZoomMode` is `XY` (both axis).

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

## Events

**ZoomStart**

This event is triggered when the user starts zooming the chart through pinch gesture, and this is a cancelable event. The argument contains the following information.

* `Axis` – the zoom start event will be triggered for all the axis in the Chart.
* `CurrentZoomFactor` – used to get the new zoom factor of the corresponding axis.
* `CurrentZoomPosition`– used to get the new zoom position of the corresponding axis.
* `Cancel` – used to set the value indicating whether the zooming should be canceled.

**ZoomDelta**

This event is triggered while zooming, and this is a cancelable event. The argument contains the following information.

* `Axis` – Instance of the axis whose range is changed because of zooming. This event is triggered for each axis in the chart.
* `PreviousZoomFactor` – used to get the previous zoom factor of the axis.
* `PreviousZoomPosition` – used to get the previous zoom position of the axis.
* `CurrentZoomFactor` – used to get the current zoom factor of the axis.
* `CurrentZoomPosition` – used to get the current zoom position of the axis.
* `Cancel` – used to set the value indicating whether the zooming should be canceled.

**ZoomEnd**

This event is triggered after the zooming is stopped. The argument contains the following information.

* `Axis` – Instance of the axis whose range is changed because of zooming. This event is triggered for each axis in the chart.
* `CurrentZoomFactor` – the axis zoom factor after zoom.
* `CurrentZoomPosition` - the axis zoom position after zoom.

**SelectionZoomStart**

This event is triggered when the user starts the box selection zooming. The argument contains the following information.

* `ZoomRect` – used to get the initial bounds of the box selection.

**SelectionZoomDelta**

This event is triggered while selecting a region to be zoomed, and this is a cancelable event. The argument contains the following information.

* `ZoomRect` – contains the bounds of the currently selected region.
* `Cancel` – used to set the value indicating whether the box selection zooming should be canceled.

**SelectionZoomEnd**

This event is triggered after selection zooming ends. The argument contains the following information.

* `ZoomRect` – used to get the final bounds of the zoomed region.

**Scroll**

This event is triggered while panning, and this is a cancelable event. The argument contains the following information.

* `Axis` – Instance of the axis whose range is changed while panning. This event is triggered for each axis in the chart.
* `ZoomPosition` – the current zoom position of the axis.
* `Cancel` – used to set a value indicating whether the scrolling should be canceled.

**ResetZoom**

This event is triggered after the chart is reset on double tap. The argument contains the following information.

* `Axis` – Instance of the axis whose range is changed because of this event. This event is triggered for each axis in the chart.
* `PreviousZoomFactor` – used to get the previous zoom factor.
* `PreviousZoomPosition` – used to get the previous zoom position.