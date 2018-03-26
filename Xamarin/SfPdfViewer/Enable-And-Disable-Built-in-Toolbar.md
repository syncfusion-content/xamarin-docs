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

## How to disable built-in toolbar?

By default, the toolbar is enabled. It can be disabled by setting the Toolbar.Enabled property of PDF Viewer to false. 

{% tabs %}
{% highlight c# %}

pdfViewerControl.Toolbar.Enabled = false;

{% endhighlight %}
{% endtabs %}

## How to enable built-in toolbar?

The toolbar can be enabled again by setting the same Toolbar.Enabled property to true. 

{% tabs %}
{% highlight c# %}

pdfViewerControl.Toolbar.Enabled = true;

{% endhighlight %}
{% endtabs %}