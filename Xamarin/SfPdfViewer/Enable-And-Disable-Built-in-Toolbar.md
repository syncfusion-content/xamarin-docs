---
layout: post
title:  Enable and disable built-in toolbar
description: Enable and disable built-in toolbar
platform: Xamarin.Forms
control: SfPdfViewer
documentation: ug
---

# Enable and disable built-in toolbar

PDF Viewer has a built-in toolbar that can be disabled or enabled. 

## How to disable/enable built-in toolbar?

By default, the built-in toolbar will be enabled. It can be disabled by setting the Toolbar.Enabled property of PDF Viewer to false.

{% tabs %}
{% highlight c# %}

pdfViewerControl.Toolbar.Enabled = false;

{% endhighlight %}
{% endtabs %}

The toolbar can be enabled by setting the same property to true.

{% tabs %}
{% highlight c# %}

pdfViewerControl.Toolbar.Enabled = true;

{% endhighlight %}
{% endtabs %}