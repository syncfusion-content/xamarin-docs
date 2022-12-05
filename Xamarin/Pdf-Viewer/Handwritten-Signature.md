---
layout: post
title: Handwritten signatures in Xamarin Pdf Viewer control | Syncfusion
description: Learn here all about Handwritten signatures support in Syncfusion Xamarin Pdf Viewer (SfPdfViewer) control and more.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Handwritten signatures in Xamarin Pdf Viewer (SfPdfViewer)

[Xamarin PDF Viewer](https://www.syncfusion.com/xamarin-ui-controls/xamarin-pdf-viewer) allows you to include handwritten signatures in PDF documents and provides options to modify or remove the existing ones.

## Adding handwritten signatures using toolbar

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

## Adding Handwritten signature programmatically

By `AddHandwrittenSignature` or `AddAnnotation` method, You can add the handwritten signatures programmatically. The created handwritten signature object passed as a parameter. The `HandwrittenSignature` instance acquires the `HandwrittenSignature.InkPointsCollection`, page number and position as the parameters.

The `HandwrittenSignature.InkPointsCollection` is of type `List<List<float>>`. Each `List<float>` in this collection represent each stroke of the signature. There will be as many `List<float>` instances in the `InkPointsCollection` as the number of strokes in the handwritten signature. 

The `List<float>`, in turn, has the series of alternate X and Y coordinates of the ink stroke. i.e. the values at the odd position are X coordinates and at the even position are Y coordinates. 

The following code sample explains adding a single stroke handwritten signature programmatically.  

{% tabs %}
{% highlight c# %}

var inkPointsCollection = new List<List<float>>();
inkPointsCollection.Add(new List<float> { 53f, 525f, 53f, 527f, 53f, 528f, 53f, 531f, 53f, 549f, 54f, 570f, 56f, 597f, 57f, 623f, 59f, 652f, 60f, 679f, 62f, 705f, 64f, 726f, 65f, 744f, 66f, 758f, 66f, 768f, 65f, 777f, 65f, 782f, 65f, 784f, 64f, 786f, 64f, 786f, 63f, 786f, 63f, 786f, 63f, 784f, 66f, 774f, 71f, 757f, 79f, 734f, 88f, 708f, 99f, 681f, 112f, 652f, 126f, 627f, 140f, 606f, 150f, 591f, 158f, 582f, 162f, 578f, 164f, 577f, 165f, 576f, 166f, 576f, 165f, 578f, 155f, 592f, 143f, 605f, 121f, 621f, 99f, 631f, 77f, 639f, 54f, 644f, 35f, 645f, 20f, 644f, 10f, 642f, 4f, 642f, 2f, 641f, 1f, 640f, 0f, 639f, 0f, 639f, 2f, 639f, 20f, 645f, 47f, 657f, 75f, 672f, 106f, 688f, 137f, 704f, 168f, 718f, 197f, 732f, 221f, 741f, 240f, 748f, 254f, 753f, 254f, 753f });
System.Drawing.Point position = new System.Drawing.Point(100, 100);
HandwrittenSignature signature = new HandwrittenSignature(inkPointsCollection, 1, position);
signature.Settings.Color = Color.Red;    
//Method 1: Adds the handwritten signature using `AddHandwrittenSignature` method
pdfViewerControl.AddHandWrittenSiganture(signature);       
//Method 2: Adds the handwritten signature using `AddAnnotation` method
//pdfViewerControl.AddAnnotation(signature);

{% endhighlight %}
{% endtabs %}

### Adding handwritten signature on the specified page

The `AddHandwrittenSignature(handwrittenSignature, pageNumber)` API adds the given handwritten signature on the page specified by the `pageNumber` argument. When this API is used, the handwritten signature is added at the center of the page. 

{% tabs %}
{% highlight c# %}

pdfViewer.AddHandwrittenSignature(handwrittenSignature, 2);

{% endhighlight %}
{% endtabs %}

N>The pageNumber argument in the API is optional. If it is not specified, the signature is added to the current page. 

### Adding handwritten signature on the specified page and position

The `AddHandwrittenSignature(handwrittenSignature, position, pageNumber)` API adds the handwritten signature on the page specified by the `pageNumber` argument and the position specified by the `position` argument. 

{% tabs %}
{% highlight c# %}

System.Drawing.Point  position = new System.Drawing.Point(200,200);
pdfViewer.AddHandwrittenSignature(handwrittenSignature, position, 2);

{% endhighlight %}
{% endtabs %}

N>The pageNumber argument in the API is optional. If it is not specified, the signature is added in the current page. 

### Adding handwritten signature on multiple pages and multiple positions

The `AddHandwrittenSignature(handwrittenSignature, pageAndPositionCollection)` API can be used to add the same handwritten signature instance to the multiple positions in multiple pages. The `positionCollection` argument is of type `Dictionary` whose keys correspond to the page numbers and the values correspond to the list of positions within each page that the signature has to be added. 

{% tabs %}
{% highlight c# %}

List<System.Drawing.Point> pointCollection1 = new List<System.Drawing.Point>();
List<System.Drawing.Point> pointCollection2 = new List<System.Drawing.Point>();
Dictionary<int, List<System.Drawing.Point>> pageAndPositionCollection = new Dictionary<int, List<System.Drawing.Point>>();
System.Drawing.Point position1 = new System.Drawing.Point(20, 200);
System.Drawing.Point position2 = new System.Drawing.Point(200, 20);
System.Drawing.Point position3 = new System.Drawing.Point(400, 40);
System.Drawing.Point position4 = new System.Drawing.Point(40, 400);
pointCollection1.Add(position1);
pointCollection1.Add(position2);
pointCollection2.Add(position3);
pointCollection2.Add(position4);
pageAndPositionCollection.Add(1, pointCollection1);
pageAndPositionCollection.Add(3, pointCollection2);
pdfViewerControl.AddHandWrittenSignature(handwrittenSignature, pageAndPositionCollection);

{% endhighlight %}
{% endtabs %}

## Select handwritten signature programmatically

By `SelectAnnotation` method, You can select the handwritten signature programmatically. The specified handwritten signature object passed as a parameter.
 
The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

//Selects the specified handwritten signature 
pdfViewer.SelectAnnotation(signature);

{% endhighlight %}
{% endtabs %}

N> Once `SelectAnnotation` method is called and as long as the annotation stays selected, the `SelectedAnnotation` property will return the same instance as the parameter of this method.

## Deselect handwritten signature programmatically

By `DeselectAnnotation` method, You can deselect the handwritten signature programmatically .The specified handwritten signature object passed as a parameter. 

The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

//Deselects the specified handwritten signature
pdfViewer.DeselectAnnotation(signature);

{% endhighlight %}
{% endtabs %}

N> There is no effect in calling `DeselectAnnotation` method, if the given annotation is not selected. Once this method is called, the `SelectedAnnotation` property will return null until any other annotation gets selected.

## Customizing the position of handwritten signature drawn using the built-in signature pad

By default, when the “Done” button of the signature pad is tapped, the signature is added at the center of the current page. But the page number and position that the signature is added can be customized using the `AddHandwrittenSignature` API discussed above. 
When the “Done” button is tapped, the `InkAdded` event is raised. The handwritten signature instance that is drawn on the signature pad is exposed as the `sender` argument of the `InkAdded` event. The signature instance can then be added at any page or position using any of the required `AddHandwrittenSignature` overloads.

{% tabs %}
{% highlight c# %}


pdfViewer.InkAdded += pdfViewer_InkAdded;

private void pdfViewer_InkAdded(object sender, InkAddedEventArgs args)
{
     HandwrittenSignature handwrittenSignature = sender as HandwrittenSignature;
     System.Drawing.Point  position = new System.Drawing.Point(200,200);
	 pdfViewer.AddHandwrittenSignature(handwrittenSignature, position, 2);

}

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

### Setting the default minimum size

By the `SfPdfViewer.AnnotationSettings.HandwrittenSignature.MinimumSize` property, You can set the minimum size to which the handwritten signatures could be resized.

Refer the following code example:

{% tabs %}
{% highlight c# %}

//Sets the minimum size for the handwritten signatures
pdfViewer.AnnotationSettings.HandwrittenSignature.MinimumSize = new Size(10, 10);

{% endhighlight %}
{% endtabs %}

## Similarity with Ink annotations

The handwritten signatures are preserved as ink annotations in PdfViewer. However, on saving you can choose whether to preserve the signature as ink annotation or flatten it. This can be achieved using the `pdfViewer.AnnotationSettings.HandwrittenSignature.FlattenSignatureOnSave` property.

{% tabs %}
{% highlight c# %}

pdfViewer.AnnotationSettings.HandwrittenSignature.FlattenSignatureOnSave = true;

{% endhighlight %}
{% endtabs %}

N>The default value of the property is `true`.

### Events

Since the handwritten signature is preserved as ink annotation, the events for both handwritten signatures and ink annotations are same. The events supported by ink annotations are described in detail [here](https://help.syncfusion.com/xamarin/pdf-viewer/ink). 

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
 
## How to lock or unlock the handwritten signature?
 
To lock or unlock all the handwritten signature, set the `IsLocked` API to `true` or `false` respectively, and the following sample explains the same. But other annotation types can be moved, resized, removed or their attributes can be changed. 

{% tabs %}
{% highlight c# %}

//Disable the handwritten signature interaction such as move, resize, remove, and attributes changes.
pdfViewerControl.AnnotationSettings.HandwrittenSignature.IsLocked = true;

{% endhighlight %}
{% endtabs %}
 
Interactions with handwritten signature types such as move, resize, remove or attribute changes will be allowed only if the `SfPdfViewer.AnnotationSettings.IsLocked` API is set to `false`. The following code prevents the unlocking of the handwritten signatures, although the `IsLocked` property of the handwritten signature is set to `false`.
 
{% tabs %}
{% highlight c# %}

//Disable the handwritten signature interaction, though its 'IsLocked' property is set to ‘false’ .
pdfViewerControl.AnnotationSettings.IsLocked = true;
pdfViewerControl.AnnotationSettings.HandwrittenSignature.IsLocked = false;

{% endhighlight %}
{% endtabs %}

## How to enable or disable the handwritten signature selection?

To enable or disable the handwritten signature selection, set the `Constraints` API to `AnnotationConstraints.Selectable` or `~AnnotationConstraints.Selectable` respectively, and the following sample explains the same. But other annotation types can be selected, moved, resized, removed or their attributes can be changed. 

{% tabs %}
{% highlight c# %}

//Disable the selection of handwritten signatures.
pdfViewerControl.AnnotationSettings.HandwrittenSignature.Constraints = ~AnnotationConstraints.Selectable;

{% endhighlight %}
{% endtabs %}

Handwritten signature selection will be allowed only if the `SfPdfViewer.AnnotationSettings.Constraints` API is set to `AnnotationConstraints.Selectable`. The following code prevents the handwritten signatures selection, even though the `Constraints` property of the handwritten signature annotation is set to `AnnotationConstraints.Selectable`.

{% tabs %}
{% highlight c# %}

//Disable the handwritten signature selection, though its 'Constraints' property is set to ‘AnnotationConstraints.Selectable’ 
pdfViewerControl.AnnotationSettings.Constraints= ~AnnotationConstraints.Selectable;
pdfViewerControl.AnnotationSettings.HandwrittenSignature.Constraints = AnnotationConstraints.Selectable;

{% endhighlight %}
{% endtabs %}

## How to get and set the name of the handwritten signatures?

The PDF Viewer allows the users to get and set the name of handwritten signatures through the [Name](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.IAnnotation.html#Syncfusion_SfPdfViewer_XForms_IAnnotation_Name) API.

The following code sample explains modifying the name of the handwritten signature in the [InkAdded](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_InkAdded) event. 

{% tabs %}
{% highlight c# %}
private void PdfViewerControl_InkAdded(object sender, InkAddedEventArgs args)
{
   if(sender is HandwrittenSignature)
    {
    	(sender as HandwrittenSignature).Name = "HandwrittenSignature1";
    }
}

{% endhighlight %}
{% endtabs %}

N>For illustration purposes, we have only provided the sample for modifying the name of the handwritten signature in the [InkAdded](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_InkAdded) event. But this can be done in all other events as well. 

N>You can also explore our [Xamarin.Forms PDF Viewer example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/PdfViewer) to knows the functionalities of each feature.
