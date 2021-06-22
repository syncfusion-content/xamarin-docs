---
layout: post
title: Custom stamp annotations in Xamarin Pdf Viewer Control | Syncfusion
description: Learn here all about Working with custom stamp annotations support in Syncfusion Xamarin Pdf Viewer (SfPdfViewer) control and more.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Working with custom stamp annotations in Xamarin Pdf Viewer

[Xamarin PDF Viewer](https://www.syncfusion.com/xamarin-ui-controls/xamarin-pdf-viewer) allows you to include any form of Xamarin.Forms View that is Button, Entry, Label, Image and more anywhere in the pages of the PDF Viewer as custom stamp annotation. You can perform operations like add, move, resize, and delete the custom stamp annotations. Also, you can save and load the existing custom stamp annotation that is associated with the PDF document

## Add a custom stamp

The custom stamps can be added using any of the following APIs:

{% tabs %}
{% highlight c# %}

//Add custom stamp/view to the specified page
pdfViewer.AddStamp(View view, int pageNumber)

//Add custom stamp/view to the specified page and position as Point object
pdfViewer.AddStamp(View view, int pageNumber, Point position)

//Add custom stamp/view to the specified page and position as Rectangle object
pdfViewer.AddStamp(View view, int pageNumber, Rectangle bounds)

{% endhighlight %}
{% endtabs %}

A typical example of the custom stamp in the real world includes, adding an image as custom stamp. PDF Viewer provides option to add any user defined signature or seal image as custom stamp to the PDF document. The following code sample explains the same.

{% tabs %}
{% highlight c# %}

private void Button_Clicked(object sender, EventArgs e)
{
    //Set image source
    Image image = new Image();
    image.Source = ImageSource.FromResource("Sample.Assets.Logo.png", typeof(App).GetTypeInfo().Assembly);
    image.WidthRequest = 200;
    image.HeightRequest = 100;

    //Add image as custom stamp to the first page
    pdfViewer.AddStamp(image, 1);
}

{% endhighlight %}
{% endtabs %}

The `StampAnnotationAdded` event will be raised when custom stamp annotations are added in the PDF document.

{% tabs %}
{% highlight c# %}

pdfViewer.StampAnnotationAdded += PdfViewer_StampAnnotationAdded;

{% endhighlight %}
{% endtabs %}

## Select a custom stamp

You can select a custom stamp annotation by tapping on it and this action is followed by the appearance of the selector around the custom stamp annotation. The `StampAnnotationSelected` event will be raised when custom stamp annotations are selected in the PDF document.

{% tabs %}
{% highlight c# %}

pdfViewer.StampAnnotationSelected += PdfViewer_StampAnnotationSelected;

{% endhighlight %}
{% endtabs %}

The `StampAnnotationSelectedEventArgs` properties of the selected custom stamp annotation includes page number and bounds information. The following code sample explains this.

{% tabs %}
{% highlight c# %}

private void PdfViewer_StampAnnotationSelected(object sender, StampAnnotationSelectedEventArgs e)
{
    //Gets the page number of selected stamp annotation
    int pageNumber = e.PageNumber;

    //Gets the bounds of selected stamp annotation
    Rectangle bounds = e.Bounds;
}

{% endhighlight %}
{% endtabs %}

Also, tapping a custom stamp annotation selects it or deselects if it is already selected. Tapping a custom stamp annotation will raise the `StampAnnotationTapped` event.

{% tabs %}
{% highlight c# %}

pdfViewer.ShapeAnnotationTapped += PdfViewer_ShapeAnnotationTapped;

{% endhighlight %}
{% endtabs %}

## Deselect a custom stamp

You can deselect a selected custom stamp annotation by tapping on it or somewhere else on the PDF document. Deselection of a custom stamp annotation can be detected using the `StampAnnotationDeselected` event.

{% tabs %}
{% highlight c# %}

pdfViewer.StampAnnotationDeselected += PdfViewer_StampAnnotationDeselected;

{% endhighlight %}
{% endtabs %}

## Move or resize a custom stamp

Select the custom stamp annotation to move or resize it. After the selector appears around the custom stamp annotation, drag it to move to a new location by tapping anywhere inside the selector. Similarly, drag the selector corner handle(s) to resize the selected custom stamp annotation. The `StampAnnotationMovedOrResized` event will be raised when you move or resize the selected annotation.

{% tabs %}
{% highlight c# %}

pdfViewer.StampAnnotationMovedOrResized += PdfViewer_StampAnnotationMovedOrResized;

{% endhighlight %}
{% endtabs %}

The `StampAnnotationMovedOrResizedEventArgs` properties of the moved or resized custom stamp annotation includes page number, old bounds, and new bounds information. The following code sample explains this.

{% tabs %}
{% highlight c# %}

private void PdfViewer_StampAnnotationMovedOrResized(object sender, StampAnnotationMovedOrResizedEventArgs e)
{
    //Get the page number of selected stamp annotation
    int pageNumber = e.PageNumber;

    //Get the old bounds of selected stamp annotation
    Rectangle oldBounds = e.OldBounds;

    //Get the new bounds of selected stamp annotation
    Rectangle newBounds = e.NewBounds;
}

{% endhighlight %}
{% endtabs %}

## Delete a custom stamp

When you select the custom stamp annotation, delete icon will appear on the bottom toolbar. By clicking that delete icon, the selected custom stamp annotation can be removed. The `StampAnnotationRemoved` event will be raised when a custom stamp annotation is removed from the PDF.

{% tabs %}
{% highlight c# %}

pdfViewer.StampAnnotationRemoved += PdfViewer_StampAnnotationRemoved;

{% endhighlight %}
{% endtabs %}

## How to enable or disable custom stamp annotation interaction?

The interaction operation can be enabled or disabled for custom stamp annotation alone by setting the `IsLocked` API to `false` or `true` respectively.

For example, the following code disables the interaction operations for all custom stamp annotations in the PDF. But other annotation types can be selected, moved, resized, or removed. 

{% tabs %}
{% highlight c# %}

//Disable the custom stamp annotation interaction
pdfViewerControl.AnnotationSettings.Stamp.IsLocked = true;

{% endhighlight %}
{% endtabs %}

The interaction with custom stamp annotation types will be allowed only if the `SfPdfViewer.AnnotationSettings.IsLocked` API is set to `false`. The following code does not allow the interactions with custom stamp annotations, although the `IsLocked` property of the custom stamp annotation is set to `false`. 

{% tabs %}
{% highlight c# %}

//Disables the custom stamp annotation interaction, though its 'IsLocked' property is set to ‘false’ 
pdfViewerControl.AnnotationSettings.IsLocked = true;
pdfViewerControl.AnnotationSettings.Stamp.IsLocked = false;

{% endhighlight %}
{% endtabs %}

## How to retrieve the actual view added as the stamp using the AddStamp method

The stamp annotation view can be retrieved when the stamp is added, tapped, selected, deselected, moved, or resized, and removed from the event data parameter of the respective event handler from the [`CustomStampView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.StampAnnotationMovedOrResizedEventArgs.html#Syncfusion_SfPdfViewer_XForms_StampAnnotationMovedOrResizedEventArgs_CustomStampView) property. The stamp view, thus retrieved, is the same instance as the one added using the [`AddStamp`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_AddStamp_Xamarin_Forms_View_System_Int32_) method. 

Refer to the following code example. The [`StampAnnotationSelected`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_StampAnnotationSelected) event is shown for illustration purposes. 

{% tabs %}
{% highlight c# %}

pdfViewerControl.StampAnnotationSelected += PdfViewerControl_StampAnnotationSelected;

private void PdfViewerControl_StampAnnotationSelected(object sender, StampAnnotationSelectedEventArgs e)
        {
            //Retrieves the actual view added as the stamp using the AddStamp method.
            var customStamp = e.CustomStampView;
        }

{% endhighlight %}
{% endtabs %}

## How to get and set the name of the custom stamp annotations?

The PDF Viewer allows the users to get and set the name of custom stamp annotations through the [Name](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.IAnnotation.html#Syncfusion_SfPdfViewer_XForms_IAnnotation_Name) API.

The following code sample explains modifying the name of the custom stamp annotation in the [StampAnnotationAdded](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_StampAnnotationAdded) event. 

{% tabs %}
{% highlight c# %}

 private void PdfViewerControl_StampAnnotationAdded(object sender, StampAnnotationAddedEventArgs e)
{
(sender as StampAnnotation).Name = "StampAnnotation1";
}

{% endhighlight %}
{% endtabs %}

N>For illustration purposes, we have only provided the sample for modifying the name of the annotation in the [StampAnnotationAdded](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_StampAnnotationAdded) event. But this can be done in all other events as well.

N>You can also explore our [Xamarin.Forms PDF Viewer example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/PdfViewer) to knows the functionalities of each feature.

## How to Customize the Minimum size of the Custom Stamp Annotations?

By the `MinimumSize` property, You can set the minimum size to which the custom stamp annotations could be resized.

Refer the following code example:

{% tabs %}
{% highlight c# %}

//Sets the minimum size for the custom stamp annotations
pdfViewerControl.AnnotationSettings.Stamp.MinimumSize = new Size(10, 10);

{% endhighlight %}
{% endtabs %}

## How to add the custom stamp annotation programmatically?

By `AddAnnotation` method , You can add the custom stamp annotations programmatically. The created custom stamp annotation object passed as a parameter. The `StampAnnotation` instance acquires the type of the stamp view, page number and bounds as the parameters. 

The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

//Creates the stamp annotation
Image image = new Image();

image.Source = ImageSource.FromResource("Sample.Assets.Logo.png", typeof(App).GetTypeInfo().Assembly);

image.WidthRequest = 200;

image.HeightRequest = 100;

StampAnnotation stampAnnotation = new StampAnnotation(image, 1, new Rectangle(100, 100, 100, 100));        

//Add the stamp annotation to the specified page 
pdfViewerControl.AddAnnotation(stampAnnotation);            

{% endhighlight %}
{% endtabs %}

## How to select the custom stamp annotation programmatically?

By `SelectAnnotation` method, You can select the custom stamp annotation programmatically. The specified custom stamp annotation object passed as a parameter. 

The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

//Selects the specified stamp annotation
pdfViewerControl.SelectAnnotation(stampAnnotation);           

{% endhighlight %}
{% endtabs %}

N> Once `SelectAnnotation` method is called and as long as the annotation stays selected, the `SelectedAnnotation` property will return the same instance as the parameter of this method.

## How to deselect the custom stamp annotation programmatically?

By `DeselectAnnotation` method , You can deselect the custom stamp annotation programmatically. The specified custom stamp annotation object passed as a parameter.

The following code sample illustrates the same.

{% tabs %}
{% highlight c# %}

//Deselects the specified stamp annotation
pdfViewerControl.DeselectAnnotation(StampAnnotation);       

{% endhighlight %}
{% endtabs %}

N> There is no effect in Calling `DeselectAnnotation` method, if the given annotation is not selected. Once this method is called, the `SelectedAnnotation` property will return null until any other annotation gets selected.

