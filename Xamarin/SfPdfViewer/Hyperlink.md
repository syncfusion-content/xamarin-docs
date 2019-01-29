---
layout: post
title:  Hyperlink navigation in PDF Viewer Xamarin.Forms | Syncfusion
description: Hyperlink navigation support in PDF Viewer Xamarin.Forms detects hyperlinks present in PDF and on tapping it, will open the URL in the browser.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Working with Hyperlink navigation

PDF viewer supports hyperlink navigation that detects hyperlinks and tapping on the hyperlink will open the URL in the browser.


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
