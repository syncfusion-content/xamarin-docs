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

[Xamarin PDF Viewer](https://www.syncfusion.com/xamarin-ui-controls/xamarin-pdf-viewer) allows you to track form field interactions using events. The interactions on the following types of form fields can be tracked using events.

*Text
*Check Box
*Radio button
*Combo Box
*List box
*Signature

### Detecting the value change of form fields

The event `FormFieldValueChanged` will be raised when the values of the form fields are changed.

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

The event `FormFieldFocused` will be raised when text or signature field is focused.

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

N>This event will be raised only for text and signature form fields.

### Detecting the unfocus of form fields

The event `FormFieldUnfocused` will be raised when text or signature field is unfocused.

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

N>This event will be raised only for text and signature form fields.