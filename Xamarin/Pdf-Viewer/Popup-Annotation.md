---
layout: post
title: Popup annotations in Xamarin Pdf Viewer control | Syncfusion
description: Learn here all about Popup annotations support in Syncfusion Xamarin Pdf Viewer (SfPdfViewer) control and more.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Popup Annotations in Xamarin Pdf Viewer (SfPdfViewer)
[Xamarin PDF Viewer](https://www.syncfusion.com/xamarin-ui-controls/xamarin-pdf-viewer) allows you to include Popup or Sticky note annotations in a PDF document and provides options to modify or remove the existing ones.

## Adding Popup annotations using toolbar
### Enabling Popup annotation mode

Set the `AnnotationMode` property of the PDF viewer to `Popup`. After setting the annotation mode, the zooming, panning, and scrolling will be disabled. Tap anywhere on the displayed PDF page, a popup will appear. Type the text in the popup and click "Ok" to add popup or sticky note to the page. Once the popup annotation is added, the zooming, panning, and scrolling will be enabled again.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer"/> 
<Button x:Name="popupAnnotationButton" Command="{Binding AnnotationModeCommand, Source={x:Reference Name=pdfViewer}}" CommandParameter="Popup" />

{% endhighlight %}

{% highlight c# %}

SfPdfViewer pdfViewer = new SfPdfViewer(); 
pdfViewer.AnnotationMode = AnnotationMode.Popup;

{% endhighlight %}
{% endtabs %}

### Disabling Popup annotation mode

Setting the annotation mode to None disables the popup mode.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer"/> <Button x:Name="resetAnnotationButton" Command="{Binding AnnotationModeCommand, Source={x:Reference Name=pdfViewer}}" CommandParameter="None" />

{% endhighlight %}
{% highlight c# %}

pdfViewer.AnnotationMode = AnnotationMode.None;

{% endhighlight %}
{% endtabs %}

### Detecting the inclusion of Popup annotations

The event `PopupAnnotationAdded` will be raised when a popup annotation is added to the PDF.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" PopupAnnotationAdded =" PdfViewer_PopupAnnotationAdded"/>

{% endhighlight %}

{% highlight c# %}

pdfViewer.PopupAnnotationAdded += PdfViewer_PopupAnnotationAdded;

{% endhighlight %}
{% endtabs %}


## Adding popup annotations programmatically

By `AddAnnotation` method, you can add the popup annotations programmatically with the created popup annotation object passed as a parameter. The `PopupAnnotation` instance acquires the page number and position as the parameters and the text note to be added.

The following code example illustrates the same.

{% tabs %}
{% highlight c# %}

//Creates the popup annotation
PopupAnnotation popupAnnotation = new PopupAnnotation(1, new Point(100, 100));

//Add the popup text
popupAnnotation.Settings.Text = "Syncfusion";

//Add the popup annotation to the specified page and position
pdfViewerControl.AddAnnotation(popupAnnotation);

{% endhighlight %}
{% endtabs %}

## Detecting tap on popup annotations

Tapping a popup annotation selects it or deselects if it is already selected. The event `PopupAnnotationTapped` is raised when a Popup is tapped.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" PopupAnnotationTapped="PdfViewer_PopupAnnotationTapped "/>

{% endhighlight %}
{% highlight c# %}

pdfViewer.PopupAnnotationTapped += PdfViewer_PopupAnnotationTapped;

{% endhighlight %}
{% endtabs %}

## Selecting popup annotations

You can select a popup annotation by tapping on it. When a popup is selected, the `PopupAnnotationSelected` event will be raised. The properties of the selected popup can be retrieved using the sender parameter of the event handler.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" PopupAnnotationSelected="PdfViewer_PopupAnnotationSelected "/>

{% endhighlight %}

{% highlight c# %}

private void PdfViewer_PopupAnnotationSelected(object sender, EventArgs args) 
{ 

//Get the page number of the selected popup annotation
int pageNumber = (sender as PopupAnnotation).PageNumber; 

//Get the position of the selected popup annotation
Point position = (sender as PopupAnnotation).Position; 

//Get the text of the popup annotation 
string text = (sender as PopupAnnotation).Settings.Text; 

//Get the icon color 
Color iconColor = (sender as PopupAnnotation).Settings.Color; 

//Get the icon type
PopupIcon popupIcon = (sender as PopupAnnotation).Settings.Icon; 

}

{% endhighlight %}
{% endtabs %}

### Selecting popup annotation programmatically

By `SelectAnnotation` method, you can select the popup annotation with the specified popup annotation object passed as a parameter.

The following code example illustrates the same.

{% tabs %}
{% highlight c# %}

//Selects the specified popup annotation 
pdfViewer.SelectAnnotation(popupAnnotation);

{% endhighlight %}
{% endtabs %}

N> Once `SelectAnnotation` method is called and as long as the annotation stays selected, the `SelectedAnnotation` property will return the same instance as the parameter of this method.

## Deselecting popup annotations

You can deselect a selected popup annotation by tapping on it or somewhere on the PDF page. Deselection can be detected using the `PopupAnnotationDeselected` event.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" PopupAnnotationDeselected="PdfViewer_PopupAnnotationDeselected"/>

{% endhighlight %}

{% highlight c# %}

pdfViewer.PopupAnnotationDeselected += PdfViewer_PopupAnnotationDeselected;

{% endhighlight %}
{% endtabs %}

### Deselecting popup annotation programmatically

By `DeselectAnnotation` method, you can deselect the popup annotation with the specified popup annotation object passed as a parameter.

The following code example illustrates the same.

{% tabs %}
{% highlight c# %}

//Deselects the specified popup annotation 
pdfViewer.DeselectAnnotation(popupAnnotation);

{% endhighlight %}
{% endtabs %}

N>There is no effect in calling DeselectAnnotation method, if the given annotation is not selected. Once this method is called, the SelectedAnnotation property will return null until any other annotation gets selected.

##Customizing the appearance of popup annotations

###Setting the default color

You can set the default color of the popup annotations by using the `SfPdfViewer.AnnotationSettings.Popup.Color` property. Refer to the following code example.

{% highlight c# %}
pdfViewer.AnnotationSettings.Popup.Color = Color.Red;
{% endhighlight %}

### Setting the default popup appearance icon

You can set the default popup appearance icon of the popup annotations by using the `SfPdfViewer.AnnotationSettings.Popup.Icon` property. The supported popup annotation appearance icons are:
1.Note
2.Insert
3.Comment
4.Key
5.Help
6.Paragraph
7.NewParagraph 

Refer to the following code example.

{% tabs %}
{% highlight c# %}

pdfViewer.AnnotationSettings.Popup.Icon = PopupIcon.Note;

{% endhighlight %}
{% endtabs %}

### Changing the properties of a selected popup

You can change the properties of the selected annotation by casting the sender parameter of the `PopupAnnotationSelected` event handler to PopupAnnotation and modify its properties. The following code example shows how to change the properties.

{% tabs %}
{% highlight c# %}

Button changePopupPropertiesButton = new Button(); 
changePopupPropertiesButton.Clicked+= changePopupPropertiesButton_Clicked; 

PopupAnnotation selectedPopupAnnotation;
 
private void PdfViewer_PopupAnnotationSelected(object sender, EventArgs args) 
{ 

   //Cast the sender object to PopupAnnotation 
   selectedPopupAnnotation = sender as PopupAnnotation; 

} 

private void changePopupPropertiesButton_Clicked(object sender, EventArgs e) 
{ 

   //Change the color
   selectedPopupAnnotation.Settings.Color = Color.Blue;
 
   //Change the icon
   selectedPopupAnnotation.Settings.Icon = PopupIcon.Key;

   //Change the Text
   selectedPopupAnnotation.Settings.Text = "Text";

}
 
{% endhighlight %}
{% endtabs %}

## Moving popup annotations

To move the annotation, it should be selected. After the selector appears, tapping and dragging anywhere inside the selector will move the annotation.

N>Popup annotations cannot be resized.

### Detecting the movement of a popup annotation
The event `PopupAnnotationMoved` will be raised when you move the popup annotation.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" PopupAnnotationMoved="PdfViewer_PopupAnnotationMoved"/>

{% endhighlight %}

{% highlight c# %}

pdfViewer.PopupAnnotationMoved += PdfViewer_PopupAnnotationMoved

{% endhighlight %}
{% endtabs %}

The properties of the moved popup can be obtained from the args parameter of the event handler.

{% tabs %}
{% highlight c# %}

private void PdfViewer_PopupAnnotationMoved(object sender, PopupAnnotationMovedEventArgs args) 
{ 

//Retrieve the old position of the annotation 
Point oldPosition = args.OldPosition; 

//Retrieve the new position of the annotation 
Point newPosition = args.NewPosition; 

}

{% endhighlight %}
{% endtabs %}

## Deleting popup annotations

PDF viewer can remove a selected annotation or all annotations in the PDF document.

###Removing a selected popup annotation

The following code example illustrates removing a selected popup from the PDF document.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" PopupAnnotationSelected="PdfViewer_PopupAnnotationSelected"/> <Button x:Name="deletePopupAnnotationButton" Grid.Row="1" Clicked="deletePopupAnnotationButton_Clicked" />

{% endhighlight %}

{% highlight c# %}

PopupAnnotation selectedPopupAnnotation; 
private void PdfViewer_PopupAnnotationSelected(object sender, EventArgs args) 
{ 

//Cast the sender object to popup annotation. 
selectedPopupAnnotation = sender as PopupAnnotation; 

}
 private void deletePopupAnnotationButton_Clicked(object sender, EventArgs e) 
{

 //Delete the selected popup annotation
 pdfViewer.RemoveAnnotation(selectedPopupAnnotation); 
 
}

{% endhighlight %}
{% endtabs %}

### Removing all annotations

The `ClearAllAnnotations` method can be used to delete all annotations irrespective of their types from the PDF.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfPdfViewer x:Name="pdfViewer" /> <Button x:Name="deleteAllAnnotationsButton" Command="{Binding ClearAllAnnotationsCommand, Source={x:Reference Name=pdfViewer}} />
{% endhighlight %}

{% highlight c# %}
//Delete all the annotations from a button click
private void deleteAllAnnotationsButton_Clicked(object sender, EventArgs e) 
{ 
pdfViewer.ClearAllAnnotations(); 
}
{% endhighlight %}
{% endtabs %}

## Detecting the removal of a popup annotation
The event `PopupAnnotationRemoved` will be raised when a Popup annotation is removed from the PDF.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" PopupAnnotationRemoved="PdfViewer_PopupAnnotationRemoved"/>

{% endhighlight %}

{% highlight c# %}

pdfViewer.PopupAnnotationRemoved += PdfViewer_PopupAnnotationRemoved;

{% endhighlight %}
{% endtabs %}

The properties of the removed Popup can be obtained from the sender parameter of the event handler.

{% tabs %}
{% highlight c# %}

private void PdfViewer_PopupAnnotationRemoved(object sender, EventArgs args) 
{ 
//Get the page number of the selected popup annotation
int pageNumber = (sender as PopupAnnotation).PageNumber; 

//Get the text of the popup annotation 
string text = (sender as PopupAnnotation).Settings.Text; 

//Get the icon color 
Color textColor = (sender as PopupAnnotation).Settings.Color; 

//Get the icon type
PopupIcon popupIcon = (sender as PopupAnnotation).Settings.Icon; 

}
{% endhighlight %}
{% endtabs %}

## How to open and edit the text of the popup annotation?

The popup annotation can be opened and edited by selecting and double tapping on it from the UI. We can programmatically open the popup view and edit the popup annotation's text by calling the EditPopupAnnotationText method. 

The following code example illustrates the same.

{% tabs %}
{% highlight c# %}

//Edit the selected popup annotation in the PDF document 
pdfViewer.EditPopupAnnotationText();

{% endhighlight %}
{% endtabs %}

N>There will be no effect in calling the `EditPopupAnnotationText` method, if the popup annotation is not selected.

## How to lock or unlock the popup annotations?

To lock or unlock all the popup annotation, set the `IsLocked` API to true or false respectively, and the following example explains the same. But other annotation types can be moved, removed or their attributes can be changed.

{% tabs %}
{% highlight c# %}

//Disable the popup annotation interaction such as move, remove, and attributes changes. 
pdfViewerControl.AnnotationSettings.Popup.IsLocked = true;

{% endhighlight %}
{% endtabs %}

Interactions with Popup annotation types such as move, remove or attribute changes will be allowed only if the `SfPdfViewer.AnnotationSettings.IsLocked` API is set to false. The following code prevents the unlocking of popup annotations, although the `IsLocked` property of the popup annotation is set to false.

{% tabs %}
{% highlight c# %}

//Disable the popup annotation interaction, though its 'IsLocked' property is set to ‘false’.  
pdfViewerControl.AnnotationSettings.IsLocked = true; 
pdfViewerControl.AnnotationSettings.Popup.IsLocked = false;

{% endhighlight %}
{% endtabs %}

## How to enable or disable the popup annotation selection?

To enable or disable the popup annotation selection, set the `Constraints` API to `AnnotationConstraints.Selectable` or `~AnnotationConstraints.Selectable` respectively, and the following example explains the same. But other annotation types can be selected, moved, removed or their attributes can be changed.

{% tabs %}
{% highlight c# %}

//Disable the selection of popup annotations. 
pdfViewerControl.AnnotationSettings.Popup.Constraints = ~AnnotationConstraints.Selectable;

{% endhighlight %}
{% endtabs %}

Popup annotation selection will be allowed only if the `SfPdfViewer.AnnotationSettings.Constraints` API is set to `AnnotationConstraints.Selectable`. The following code prevents the Popup annotations selection, even though the `Constraints` property of the Popup annotation is set to `AnnotationConstraints.Selectable`.

{% tabs %}
{% highlight c# %}

//Disable the popup annotation selection, though its 'Constraints' property is set to ‘AnnotationConstraints.Selectable’
 pdfViewerControl.AnnotationSettings.Constraints= ~AnnotationConstraints.Selectable; 
pdfViewerControl.AnnotationSettings.Popup.Constraints = AnnotationConstraints.Selectable;

{% endhighlight %}
{% endtabs %}

## How to get and set the name of the Popup annotations?

The PDF Viewer allows the users to get and set the name of Popup annotations through the `Name` API.

The following code sample explains modifying the name of the popup annotation in the `PopupAnnotationAdded` event.

{% tabs %}
{% highlight c# %}

private void PdfViewerControl_PopupAnnotationAdded(object sender, EventArgs args) 
{ 

//Sets the name for the annotation. 
(sender as PopupAnnotation).Name = "Popup_1";

}

 {% endhighlight %}
 {% endtabs %}
 
N>For illustration purposes, we have only provided the example for modifying the name of the popup annotation in the PopupAnnotationAdded event. But this can be done in all other events as well.
N>You can also explore our [Xamarin.Forms PDF Viewer example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/PdfViewer) to knows the functionalities of each feature.

