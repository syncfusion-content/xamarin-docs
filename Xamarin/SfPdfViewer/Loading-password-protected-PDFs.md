---
layout: post
title: Loading password protected PDFs | Syncfusion
description: Loading password protected PDFs
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Loading password protected PDFs

Password protected PDFs can be loaded using the `LoadDocument(Stream stream, string password)` method. 

{% tabs %}
{% highlight c# %}

string password = "PASSWORD";
pdfViewerControl.LoadDocument(stream, password);

{% endhighlight %}
{% endtabs %}

In the above code snippet, `stream` is the Stream instance read from the encrypted PDF and `password` is the key with which the PDF is encrypted. 


## Handling invalid passwords

If the password provided with the `LoadDocument(Stream stream, string password)` is invalid, then the `UnhandledConditionOccurred` event is raised. The `Title` property of the `UnhandledConditionEventArgs` parameter helps identify whether the event raised due to invalid password. In that case the `Title` property will read "Error loading encrypted PDF document". 

{% tabs %}
{% highlight c# %}

pdfViewerControl.UnhandledConditionOccurred += PdfViewerControl_UnhandledConditionOccurred;
private void PdfViewerControl_UnhandledConditionOccurred(object sender, UnhandledConditionEventArgs args)
{
	//Get the details regarding why the unhandled condition has occurred. 
    string title = args.Title;
    string description = args.Description;
}

{% endhighlight %}
{% endtabs %}

N>The event will also be raised when an encrypted PDF is loaded without providing a password using the `LoadDocument(Stream stream)` overload.        

