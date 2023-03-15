---
layout: post
title: Working with PDF forms in Xamarin Pdf Viewer control | Syncfusion
description: Learn here all about Working with PDF forms support in Syncfusion Xamarin Pdf Viewer (SfPdfViewer) control and more.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Working with PDF forms in Xamarin Pdf Viewer (SfPdfViewer)

[Xamarin PDF Viewer](https://www.syncfusion.com/xamarin-ui-controls/xamarin-pdf-viewer) supports adding/modifying the existing forms fields content present in the PDF document. By default, it detects the form fields present in the PDF document and enables modifying or filling the values.

N>PDF Viewer supports only Acroform. PDF documents with XFA form fields cannot be viewed in PDF Viewer.

## How to restrict editing the Acroform field values in the existing PDF document

By setting the `EnableFormFilling` property of the PdfViewerControl instance to false, you can avoid modifying the values of the form field elements present in the loaded PDF document.

{% tabs %}
{% highlight c# %}

//Does not load the form fields in PDF Viewer
pdfViewerControl.EnableFormFilling = false;

{% endhighlight %}
{% endtabs %}

N>By default, the EnableFormFilling property is set to true.

## How to flatten and save the Acroform fields data

Flattening PDF form is a process of removing the form fields in the PDF document, thereby rendering the form fields appearance and its content in the page graphics. This will avoid the PDF form being edited in any device. PDF Viewer supports flattening the PDF form when saving. You can perform this action by passing the parameter `true` to the Save method of PDF Viewer.

{% tabs %}
{% highlight c# %}

//Flatten and save the form fields during saving process
pdfViewerControl.SaveDocument(true);

{% endhighlight %}
{% endtabs %}

## Editing the form field values programmatically

We can programmatically edit the form fields that are present in the document using the FormFields collection in the PdfViewer

### Editing Text Box form field
You could programmatically edit the text of the text box form field by changing the `Text` property of the text box field. Also, we could set the `CanEdit` property to false to restrict editing of individual text boxes.

{% tabs %}
{% highlight c# %}

// To take the Text box form field from the formFields collection
if (pdfViewerControl.FormFields.Where(x => x.Name == "name") is TextFormField nameTextBox) 
{
//To modify the Text entered in the text box field
 nameTextBox.Text = "Jonathan"; 
//To restrict the editing capability of the text field
 nameTextBox.CanEdit=false;
}

{% endhighlight %}
{% endtabs %}

### Editing Check box form field
You can programmatically check or uncheck the checkbox field by changing the `IsChecked` property. By default, this property is set to false. Also, you can set the `CanEdit` property to false to restrict editing of individual text boxes.

{% tabs %}
{% highlight c# %}

// To take the check box form field from the formFields collection
if (pdfViewerControl.FormFields.Where(x => x.Name == "newsletter") is CheckBoxFormField checkBox) 
{
//To change the check box to checked
 checkBox.IsChecked = true;
//To restrict the editing capability of the check box field
 checkBox.CanEdit = false;
}

{% endhighlight %}
{% endtabs %}

### Editing Combo box form field
You can programmatically select an item from the combo box by using the property `SelectedItem` of the combo box form field. Also, you can set the `CanEdit` property to false to restrict editing of combo box fields.

{% tabs %}
{% highlight c# %}

// To take the combo box form field from the formFields collection
if (pdfViewerControl.FormFields.Where(x => x.Name == "state") is ComboBoxFormField comboBox) 
{
//To select the desire item of combo box
comboBox.SelectedItem = comboBox.Items[4];
//To restrict the editing capability of the combo box field
 comboBox.CanEdit = false;
}

{% endhighlight %}
{% endtabs %}

### Editing Radio button form field
You can programmatically select an item of radio buttons by using the property `SelectedItem` of the radio button form field. Also, you can set the `CanEdit` property to false to restrict editing of radio button form fields.

{% tabs %}
{% highlight c# %}

// To take the Text box form field from the formFields collection
if (pdfViewerControl.FormFields.Where(x => x.Name == "name") is TextFormField nameTextBox) 
{
//To modify the Text entered in the text box field
 nameTextBox.Text = "Jonathan"; 
//To restrict the editing capability of the text field
 nameTextBox.CanEdit=false;
}

{% endhighlight %}
{% endtabs %}

### Editing Signature form field
You can programmatically add a signature to the signature form field by adding a handwritten signature to the `HandwrittenSignature` property. Also, you can set the `CanEdit` property to false to restrict adding the signature in the signature form field.

{% tabs %}
{% highlight c# %}

// To take the signature form field from the formFields collection
SignatureFormField signature = pdfViewerControl.FormFields.Where(x => x.Name == "signature") as SignatureFormField;
if (signature != null) 
{
var inkPointsCollection = new List<List<float>>(); inkPointsCollection.Add(new List<float> { 53f, 525f, 53f, 527f, 53f, 528f, 53f, 531f, 53f, 549f, 54f, 570f, 56f, 597f, 57f, 623f, 59f, 652f, 60f, 679f, 62f, 705f, 64f, 726f, 65f, 744f, 66f, 758f, 66f, 768f, 65f, 777f, 65f, 782f, 65f, 784f, 64f, 786f, 64f, 786f, 63f, 786f, 63f, 786f, 63f, 784f, 66f, 774f, 71f, 757f, 79f, 734f, 88f, 708f, 99f, 681f, 112f, 652f, 126f, 627f, 140f, 606f, 150f, 591f, 158f, 582f, 162f, 578f, 164f, 577f, 165f, 576f, 166f, 576f, 165f, 578f, 155f, 592f, 143f, 605f, 121f, 621f, 99f, 631f, 77f, 639f, 54f, 644f, 35f, 645f, 20f, 644f, 10f, 642f, 4f, 642f, 2f, 641f, 1f, 640f, 0f, 639f, 0f, 639f, 2f, 639f, 20f, 645f, 47f, 657f, 75f, 672f, 106f, 688f, 137f, 704f, 168f, 718f, 197f, 732f, 221f, 741f, 240f, 748f, 254f, 753f, 254f, 753f });
var sign = new HandwrittenSignature() 
{
 InkPointsCollection = inkPointsCollection, 
}; 
sign.Settings.Color = Color.Red; 
sign.Settings.Thickness = 4; 
// To add the handwritten signature to the signature form field
signature.HandwrittenSignature = sign; 
}

{% endhighlight %}
{% endtabs %}

## How to restrict editing each form field’s data

You can restrict each field's editing by setting the `CanEdit` property on the individual form to false.

{% tabs %}
{% highlight c# %}

foreach (Syncfusion.SfPdfViewer.XForms.FormField form in pdfViewerControl.FormFields)
{
  //To restrict the editing each field
  form.CanEdit = false;
}               

{% endhighlight %}
{% endtabs %}

## How to restrict editing of form field data

By setting the `CanEdit` property of the `PdfViewerControl.FormSettings` instance to false, you can avoid modifying the values of the form field elements present in the loaded PDF document.

{% tabs %}
{% highlight c# %}

//Does not allow form fields to edit in PDF Viewer 
pdfViewerControl.FormSettings.CanEdit = false;

{% endhighlight %}
{% endtabs %}

## How to clear form field data

The `ClearFormData` API can be used to remove all the form field data in the PDF document. 

{% tabs %}
{% highlight c# %}

//Clears all form field data 
pdfViewerControl.ClearFormData();

{% endhighlight %}
{% endtabs %}

## Removing all form field data in a page

The `ClearFormData(int pageNumber)` API can be used to remove all the form field data in a page of the PDF document.

{% tabs %}
{% highlight c# %}

//Clears all form field data in a page
pdfViewerControl.ClearFormData(int pageNumber);

{% endhighlight %}
{% endtabs %}

## Rendering the appearance content of signature form fields

By default, the PDF viewer does not display the appearance content of signature form fields. But the appearance can be displayed by flattening the signature form fields before loading the PDF. This can be achieved by setting the `FlattenSignatureFields` property as true. The default value of the property is set as false.

{% tabs %}
{% highlight c# %}

//Sets a value whether the signature form fields should be flattened when the PDF is loaded or not.
pdfViewerControl.FormSettings.FlattenSignatureFields = true;
//Loads the PDF. 
pdfViewerControl.LoadDocument(stream);

{% endhighlight %}
{% endtabs %}

N> Signature form fields are only flattened when the page displayed in the viewer is only for viewing the appearance of signature form fields. Once the signature form fields are flattened, the interactions such as select, edit, resize, and remove cannot be performed. Setting the `FlattenSignatureFields` property as `true` will does not affect the save and form field export operations. The signature form fields will not be flattened in these operations.

## Loading PDFs with XFA forms

PDF documents that contain XFA form fields cannot be viewed in PDF Viewer since they can be viewed only in Adobe reader. When a PDF with XFA form is loaded, its original contents may not be rendered as expected. 

The value of the [IsXFAForm](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_IsXFAForm) property indicates whether the PDF loaded contains XFA form. 

{% tabs %}
{% highlight c# %}

bool pdfContainsXFAForm = pdfViewerControl.IsXFAForm;

{% endhighlight %}
{% endtabs %}

N>You can also explore our [Xamarin.Forms PDF Viewer example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/PdfViewer) to knows the functionalities of each feature.

## Events to track form field interaction

The [PDF Viewer](https://www.syncfusion.com/xamarin-ui-controls/xamarin-pdf-viewer) allows you to track form field interactions using events. The interactions on the following types of form fields can be tracked using events.

* Text
* Check Box
* Radio button
* Combo Box
* List box
* Signature

### Detecting the value change of form fields

The`FormFieldValueChanged` event will be raised when the values of the form fields are changed.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FormFieldValueChanged="PdfViewer_FormFieldValueChanged"/>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

privatevoidPdfViewerControl_FormFieldValueChanged(object sender, FormFieldValueChangedEventArgs args)
{  
  //Get the name of the form field          
  string fieldName = args.FormFieldName;
  //Get the type of the form field   
  FormFieldType formFieldType= args.FormFieldType; 
  //Get the value of the form field after the event occurs    
  object newValue = args.NewValue;     
  //Get the value of the form field before the event occurs 
  object oldValue = args.OldValue;
}

{% endhighlight %}
{% endtabs %}

### Detecting the focus of form fields

The `FormFieldFocused` event will be raised when text or signature field is focused.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FormFieldFocused="PdfViewer_FormFieldFocused"/>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

privatevoidPdfViewerControl_FormFieldFocused(object sender, FormFieldFocusedEventArgs args)
{          
  //Get the name of the form field             
  string fieldName = args.FormFieldName;           
  //Get the type of the form field            
  FormFieldType formFieldType= args.FormFieldType; 
}

{% endhighlight %}
{% endtabs %}

N>This event will be raised only for the text and signature form fields.

### Detecting the unfocus of form fields

The `FormFieldUnfocused` event will be raised when text or signature field is unfocused.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FormFieldUnfocused="PdfViewer_FormFieldUnfocused"/>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

privatevoidPdfViewerControl_FormFieldUnfocused(object sender, FormFieldUnfocusedEventArgs args) 
{          
  //Get the name of the form field             
  string fieldName = args.FormFieldName;       
  //Get the type of the form field       
  FormFieldType formFieldType= args.FormFieldType;
}

{% endhighlight %}
{% endtabs %}

N>This event will be raised only for the text and signature form fields.