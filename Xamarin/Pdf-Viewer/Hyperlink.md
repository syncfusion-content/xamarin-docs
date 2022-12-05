---
layout: post
title: Hyperlink Navigation in Xamarin Pdf Viewer control | Syncfusion
description: Learn here all about Hyperlink Navigation support in Syncfusion Xamarin Pdf Viewer (SfPdfViewer) control and more.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Hyperlink Navigation in Xamarin Pdf Viewer (SfPdfViewer)

[Xamarin PDF Viewer](https://www.syncfusion.com/xamarin-ui-controls/xamarin-pdf-viewer) supports hyperlink navigation that detects hyperlinks and tapping on the hyperlink will open the URL in the browser.


## How to disable hyperlink navigation in PDF document using PDF viewer control?

You can disable the hyperlink navigation by setting the “AllowHyperlinkNavigation” property of PDF viewer to false. By default, hyperlink navigation is enabled in PDF viewer.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewerControl" AllowHyperlinkNavigation="False" InputFileStream="{Binding PdfDocumentStream}" />

{% endhighlight %}
{% endtabs %}

## How to acquire the properties of clicked URI from PDF viewer?

You can acquire the details of the hyperlink that is tapped in the PDF viewer control from the HyperlinkClickedEventArgs and HyperlinkClicked event. Refer to the following code snippet for more details.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewerControl" HyperlinkClicked="pdfViewerControl_HyperlinkClicked"  InputFileStream="{Binding PdfDocumentStream}" />

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

        public void pdfViewerControl_HyperlinkClicked(object sender,HyperlinkClickedEventArgs args)
        {
            // Gets or sets a value indicating whether the hyperlink navigation was handled.
            args.Handled = false;

            // Gets the hyperlink being clicked.
            string uri = args.Uri;

            // Gets the current page index of the hyperlink.
            int pageIndex = args.PageIndex;

            //Gets the bounds of the hyperlink is being clicked.
            Rectangle hyperlinkBound = args.Bounds;

        }


{% endhighlight %}
{% endtabs %}

N>You can also explore our [Xamarin.Forms PDF Viewer example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/PdfViewer) to knows the functionalities of each feature.
