---
layout: post
title:  ScrollHead in PDF Viewer Xamarin.Forms | Syncfusion
description: Working with ScrollHead
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Working with ScrollHead

The scroll head in the PDF Viewer allows users to easily scroll through and navigate to destination page in the PDF document. ScrollHead always appears on the right side of PDF Viewer.

## Enabling and disabling ScrollHead

By setting the `EnableScrollHead` property of the PdfViewerControl instance to false, you can disable the scroll head.

<table>

<tr>
<th>Property</th>
<th>Action</th>
</tr>

<tr>
<td>EnableScrollHead</td>
<td>Gets or sets the value that enable and disable the ScrollHead feature in PDF Viewer. By default, this property is set to true.</td>
</tr>

</table>

{% tabs %}
{% highlight xaml %}

<pdfviewer:SfPdfViewer x:Name="pdfViewerControl" EnableScrollHead="False"/>               

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

//Disables the scroll head
pdfViewerControl.EnableScrollHead = false;             

{% endhighlight %}
{% endtabs %}

## Navigate to a desired page using ScrollHead

PDF Viewer allows users to navigate to a desired destination page using ScrollHead. On tapping the ScrollHead of PDF Viewer, a page navigation pop-up will appear and users can navigate to the destination page by entering a valid page number.
