---
layout: post
title: Working with PDF forms in Xamarin Pdf Viewer control | Syncfusion
description: Learn here all about Working with PDF forms support in Syncfusion Xamarin Pdf Viewer (SfPdfViewer) control and more.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Events to track form field interaction

[Xamarin PDF Viewer](https://www.syncfusion.com/xamarin-ui-controls/xamarin-pdf-viewer) allows you to track form field interactions using events. The interactions on the following types of form fields can be tracked using events.

1.Text
2.Check Box
3.Radio button
4.Combo Box
5.List box
6.Signature

## Detecting the value change of form fields

The event `FormFieldValueChanged` will be raised when the values of the form fields are changed.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FormFieldValueChanged="PdfViewer_FormFieldValueChanged"/>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

privatevoidPdfViewerControl_FormFieldValueChanged(object sender, FormFieldValueChangedEventArgs args) { //Get the name of the form field             string fieldName = args.FormFieldName;            //Get the type of the form field            FormFieldType formFieldType= args.FormFieldType;            //Get the value of the form field after the event occurs            object newValue = args.NewValue;           //Get the value of the form field before the event occurs            object oldValue = args.OldValue; }

{% endhighlight %}
{% endtabs %}



## Detecting the focus of form fields

The event `FormFieldFocused` will be raised when text or signature field is focused.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FormFieldFocused="PdfViewer_FormFieldFocused"/>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

privatevoidPdfViewerControl_FormFieldFocused(object sender, FormFieldFocusedEventArgs args) {            //Get the name of the form field             string fieldName = args.FormFieldName;            //Get the type of the form field            FormFieldType formFieldType= args.FormFieldType; }

{% endhighlight %}
{% endtabs %}

N>This event will be raised only for text and signature form fields.

## Detecting the unfocus of form fields

The event `FormFieldUnfocused` will be raised when text or signature field is unfocused.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewer" FormFieldUnfocused="PdfViewer_FormFieldUnfocused"/>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

privatevoidPdfViewerControl_FormFieldUnfocused(object sender, FormFieldUnfocusedEventArgs args) {            //Get the name of the form field             string fieldName = args.FormFieldName;            //Get the type of the form field          FormFieldType formFieldType= args.FormFieldType;}

{% endhighlight %}
{% endtabs %}

N>This event will be raised only for text and signature form fields.