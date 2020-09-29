---
layout: post
title:  Working with magnification in PDF Viewer Xamarin.Forms | Syncfusion
description: The PDF Viewer Xamarin.Forms allows the users to magnify the PDF documents in multiple ways like setting maximum, minimum and custom zoom percentage.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Working with magnification

Magnification of the PDF document can be done in multiple ways and the different ways are explained below. By default, the PdfViewer supports panning and Ctrl+ mouse scroll (in XForms.UWP) to manipulate the magnification of the document.

## Set custom zoom percentage

The users can set custom magnification factor between 100 and 300 to magnify the document displayed. The following code explains this,

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewerControl" InputFileStream="{Binding PdfDocumentStream}" ZoomPercentage="150" />

{% endhighlight %}

{% highlight c# %}

pdfViewerControl.ZoomPercentage = 150;

{% endhighlight %}
{% endtabs %}

## Get custom zoom factor

The following code explains accessing zoom factor in which the document is displayed in the viewer.

{% tabs %}
{% highlight xaml %}

<Entry Keyboard="Numeric" FontSize="18" x:Name="zoomPercentage" HorizontalTextAlignment="Center" VerticalOptions="Center" Text="{Binding ZoomPercentage, Source={x:Reference Name=pdfViewerControl}}"/>

{% endhighlight %}

{% highlight c# %}

int zoom = pdfViewerControl.ZoomPercentage;

{% endhighlight %}
{% endtabs %}

On binding entry control to the ZoomPercentage property of the PDF Viewer instance, the current zoom percentage being displayed in PDF Viewer is displayed in the entry control, and the PDF Viewer will be zoomed based on the value entered.

## Set maximum zoom percentage

The PDF Viewer control allows you to set the maximum zoom percentage value for the PDF document being displayed. The following code example will set the maximum zoom percentage of PDF Viewer instance to 200.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewerControl" InputFileStream="{Binding PdfDocumentStream}" MaximumZoomPercentage="200" />

{% endhighlight %}

{% highlight c# %}

pdfViewerControl.MaximumZoomPercentage = 200;

{% endhighlight %}
{% endtabs %}

## Set minimum zoom percentage

The PDF Viewer control allows you to set the minimum zoom percentage value for the PDF document being displayed. The following code example will set the minimum zoom percentage of PDF Viewer instance to 10.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewerControl" InputFileStream="{Binding PdfDocumentStream}" MinimumZoomPercentage="10" />

{% endhighlight %}

{% highlight c# %}

pdfViewerControl.MinimumZoomPercentage = 10;

{% endhighlight %}
{% endtabs %}

## How to enable or disable the double-tap zoom

You can enable or disable the zooming of a PDF document on double-tap by setting the `EnableDoubleTapZooming` property of the PDF viewer to `true` or `false` respectively.

N>The default value of the `EnableDoubleTapZooming` API is set to `true`. 

{% tabs %}
{% highlight c# %}

//Disable the double-tap zoom
pdfViewer.EnableDoubleTapZooming = false;

{% endhighlight %}
{% endtabs %}

N>At present, this feature is available only in iOS
