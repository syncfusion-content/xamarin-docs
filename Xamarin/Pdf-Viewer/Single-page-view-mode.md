---
layout: post
title: Single page view mode in Xamarin Pdf Viewer control | Syncfusion
description: Learn here all about Single page view mode support in Syncfusion Xamarin Pdf Viewer (SfPdfViewer) control and more.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Single page view mode in Xamarin Pdf Viewer (SfPdfViewer)

The default continuous view mode of PDF Viewer allows vertical scrolling. In addition to that, PDF Viewer also provides options to view PDFs page by page with horizontal navigation support.

![Single page view mode flipping](pdfviewer_images/SinglePageViewerFlipping.gif)

![Single page view mode scrolling](pdfviewer_images/SinglePageViewerScrolling.gif)

## Switching between view modes

The view mode can be switched by choosing the corresponding option from the menu bar that appears when the view mode button is clicked. The view mode button is available on the top toolbar. 

![Single page view mode](pdfviewer_images/SinglePageViewer1.png)

![View mode options](pdfviewer_images/SinglePageViewer2.png)

The view mode can also be changed programmatically using the `PageViewMode` property of the PDF viewer. The enum `PageViewMode` has two constants - `Continuous`, `PageByPage`. The default value is `Continuous`. The below code snippet illustrates how to switch to the page by page view mode.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewerControl" PageViewMode="PageByPage" />

{% endhighlight %}

{% highlight c# %}

pdfViewerControl.PageViewMode = PageViewMode.PageByPage;

{% endhighlight %}
{% endtabs %}

## Tracking the changes in the `PageViewMode` property

When the `PageViewMode` property changes, the `PageViewModeChanged` event is raised. The second parameter of the event handler is of type `PageViewModeChangedEventArgs` which provides the details about the old and new view modes. 

{% tabs %}
{% highlight c# %}

pdfViewerControl.PageViewModeChanged += PdfViewerControl_PageViewModeChanged1;
private void PdfViewerControl_PageViewModeChanged1(object sender, PageViewModeChangedEventArgs e)
{
    PageViewMode oldViewMode = e.PreviousPageViewMode;
    PageViewMode newViewMode = e.CurrentPageViewMode;
}

{% endhighlight %}
{% endtabs %}

## How to disable the page navigation by flipping in a single page view mode

The page navigation by flipping the pages in a single page view mode can be enabled or disabled by setting the `IsPageFlipEnabled` API to `true` or `false` respectively.

N>The default value of the `IsPageFlipEnabled` API is set to `true`. 

{% tabs %}
{% highlight c# %}

//Disable the page navigation by flipping pages
pdfViewer.IsPageFlipEnabled= false;

{% endhighlight %}
{% endtabs %}

N>You can refer to our [Xamarin PDF Viewer](https://www.syncfusion.com/xamarin-ui-controls/xamarin-pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [Xamarin.Forms PDF Viewer example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/PdfViewer) to knows the functionalities of each feature.

## How to show and hide the page navigation buttons in the page by page view mode on desktop

By default in the Xamarin.Forms.UWP platform, buttons to navigate to the next page and the previous page in the page by page view mode will be visible. It can be shown or hidden by setting the [ShowPageFlipNavigationArrows](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_ShowPageFlipNavigationArrows) property of PDF Viewer to `true` and `false` respectively.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewerControl" ShowPageFlipNavigationArrows="False" />

{% endhighlight %}
{% highlight c# %}

pdfViewerControl.ShowPageFlipNavigationArrows = false;

{% endhighlight %}
{% endtabs %}

N>This API is only applicable for desktop device in UWP platform. Changing the value of this API does not have any effect on Android and iOS platforms.