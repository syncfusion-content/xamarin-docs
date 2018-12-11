---
layout: post
title:  Working with handwritten signatures
description: Working with handwritten signatures
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Working with handwritten signatures

PDF viewer allows you to include handwritten signatures in PDF documents and provides options to modify or remove the existing ones.

## Adding handwritten signatures

### Enabling handwritten signature mode

Set the `AnnotationMode` property of the PDF viewer instance to `HandwrittenSignature`. After setting the signature mode the signature pad would appear on which the signature can be drawn. After drawing the signature, the `Done` button should be tapped to add the drawn signature to the PDF, you can use clear button to redraw the signature or close button to cancel signing.


{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer"/>
<Button x:Name="signatureButton" Command="{Binding AnnotationModeCommand, Source={x:Reference Name=pdfViewer}}" CommandParameter="HandwrittenSignature" />

{% endhighlight %}

{% highlight c# %}

pdfViewer.AnnotationMode = AnnotationMode.HandwrittenSignature;

{% endhighlight %}
{% endtabs %}

### Disabling handwritten signature mode

Setting the `AnnotationMode` to `None` will disable the signature mode and would hide the signature pad.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer"/>
<Button x:Name="resetAnnotationButton" Command="{Binding AnnotationModeCommand, Source={x:Reference Name=pdfViewer}}" CommandParameter="None" />

{% endhighlight %}
{% highlight c# %}

pdfViewer.AnnotationMode = AnnotationMode.None;

{% endhighlight %}
{% endtabs %}


## Customizing the appearance of handwritten signatures

You can customize the default values such as stroke color, opacity, and thickness of all signatures to be added. This will not affect the already added signatures.

### Setting the default stroke color

You can set the default stroke color of handwritten signatures by using the `SfPdfViewer.AnnotationSettings.HandwrittenSignature.Color` property. Refer to the following code. 

{% tabs %} 
{% highlight c# %}

pdfViewer.AnnotationSettings.HandwrittenSignature.Color = Color.Red;

{% endhighlight %}
{% endtabs %}

### Setting the default opacity

You can set the default opacity of handwritten signatures by using the `SfPdfViewer.AnnotationSettings.HandwrittenSignature.Opacity` property. Opacity value ranges from 0 to 1. Refer to the following code example.

{% tabs %}
{% highlight c# %}

pdfViewer.AnnotationSettings.HandwrittenSignature.Opacity = 0.5f; 

{% endhighlight %}
{% endtabs %}

### Setting the default thickness

You can set the thickness of handwritten signatures by using the `SfPdfViewer.AnnotationSettings.HandwrittenSignature.Thickness` property. Refer to the following code example. 

{% tabs %}
{% highlight c# %}

pdfViewer.AnnotationSettings.HandwrittenSignature.Thickness = 5;

{% endhighlight %}
{% endtabs %}

## Similarity with Ink annotations

The handwritten signatures are preserved as ink annotations in PdfViewer. However, on saving you can choose whether to preserve the signature as ink annotation or flatten it. This can be achieved using the `pdfViewer.AnnotationSettings.HandwrittenSignature.FlattenSignatureOnSave` property.

{% tabs %}
{% highlight c# %}

pdfViewer.AnnotationSettings.HandwrittenSignature.FlattenSignatureOnSave = true;

{% endhighlight %}
{% endtabs %}

N>**The default value of the property is `true`.

### Events

Since the handwritten signature is preserved as ink annotation, the events for both handwritten signatures and ink annotations are same. The events supported by ink annotations are described in detail [here](https://help.syncfusion.com/xamarin/sfpdfviewer/ink). 

When the common events occur, ink annotation and handwritten signature can be distinguished using the event argument's `IsChildSignature` property. Also, the `sender` parameter will be of type `InkAnnotation` and `HandwrittenSignature` for the respective annotations. For brevity, only the `InkSelected` event is illustrated below. 

{% tabs %}
{% highlight c# %}

pdfViewer.InkSelected += PdfViewer_InkSelected;

private void PdfViewer_InkSelected(object sender, Syncfusion.SfPdfViewer.XForms.InkSelectedEventArgs args)
{
	if(args.IsSignature)
	{
		//The event occurred was raised by handwritten signature
		//The "sender" parameter is of type "HandwrittenSignature"
	}
	else
	{
		//The event occurred was raised by ink annotation
		//The "sender" parameter is of type "InkAnnotation"
	}
}

{% endhighlight %}
{% endtabs %}
 

