---
layout: post
title: Load and save RTF content | SfRichTextEditor | Xamarin | Syncfusion
description: This page explains how to load and save Rich Text Format content in the Syncfusion Rich Text Editor for Xamarin.Forms platform.
platform: xamarin
control: Rich Text Editor
documentation: ug
---

# Loading and saving RTF content in Xamarin Rich Text Editor (SfRichTextEditor)

The Xamarin Rich Text Editor control provides support to load and save RTF content with help of [`Essential DocIO`](https://help.syncfusion.com/file-formats/docio/overview).

## Prerequisite

To manipulate RTF content in your application, [`Syncfusion.Xamarin.DocIO.nupkg`](https://www.nuget.org/packages/Syncfusion.Xamarin.DocIO/) is must be refered. The installation procedure of this NuGet package is available [`here`](https://help.syncfusion.com/file-formats/docio/nuget-packages-required#installing-syncfusion-docio-through-nuget-packages).

### Loading RTF content into Rich Text Editor.

The RTF content must be converted as HTML using Essential DocIO and then converted HTML need to be loaded into Rich Text Editor. The following code example shows how to load RTF content into a Rich Text Editor control.

{% tabs %} 

{% highlight C# %} 
public MainPage()
{
    InitializeComponent();
	MemoryStream rtfStream = new MemoryStream();
    StreamWriter writer = new StreamWriter(rtfStream);
    writer.Write(/* RTF content */);
    writer.Flush();           
    rtfStream.Position = 0;
	// Loading RTF content as Word document using DocIO
    WordDocument doc = new WordDocument(rtfStream, Syncfusion.DocIO.FormatType.Rtf);
    writer.Close();
    rtfStream.Dispose();
    HTMLExport export = new HTMLExport();
    MemoryStream htmlStream = new MemoryStream();      
	// Saving Word document as RTF
    export.SaveAsXhtml(doc, htmlStream, Encoding.UTF8);
    doc.Close();
    htmlStream.Position = 0;
	// Loading equivalent HTML obtained from DocIO
    RichTextEditor.HtmlText = IgnoreVoidElementsInHTML(System.Text.Encoding.UTF8.GetString(htmlStream.ToArray()));
	htmlStream.Dispose();
}

/// <summary>
/// Correcting void elements in the HTML. 
/// </summary>
/// <param name="inputString">HTML string with void HTML elements</param>
/// <returns></returns>
private string IgnoreVoidElementsInHTML(string inputString)
{
    inputString = inputString.Replace("<meta http-equiv=\"Content-Type\" content=\"application/xhtml+xml; charset=utf-8\">", "")
    inputString = inputString.Replace("<br>", "<br/>");
    inputString = inputString.Replace("\n", "");
    inputString = inputString.Replace("\r", "");
    inputString = inputString.Replace("<title></title>", "");
    inputString = inputString.Replace("﻿<?xml version=\"1.0\" encoding=\"utf-8\"?><!DOCTYPE html PUBLIC" +
        " \"-//W3C//DTD XHTML 1.1//EN\" \"http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd\">", "");
    return inputString;
}
{% endhighlight %}

{% endtabs %}

## Save Rich Text Editor content as RTF

SfRichTextEditor doesn't directly retrieves the content as RTF. Instead, HTML content must be converted as RTF using Essential DocIO. The following code example shows how to retrieve RTF content from Rich Text Editor.

{% tabs %} 

{% highlight C# %} 
public MainPage()
{
    InitializeComponent();
	string htmlstring = IgnoreVoidElementsInHTML(RTE.HtmlText);
    var htmlStream = new MemoryStream();
    var writer = new StreamWriter(htmlStream, Encoding.UTF8);
    writer.Write(htmlstring);
    writer.Flush();
    htmlStream.Position = 0;
	// Creates a Word document using RTE HTML
    WordDocument document = new WordDocument(htmlStream, Syncfusion.DocIO.FormatType.Html, XHTMLValidationType.None);
    MemoryStream rtfStream = new MemoryStream();
    document.SaveOptions.OptimizeRtfFileSize = true;
	// Save the Word document as RTF
    document.Save(rtfStream, Syncfusion.DocIO.FormatType.Rtf);
    rtfStream.Position = 0;
	// Retrieving RTF stream as string
    string rtfString = System.Text.Encoding.UTF8.GetString(rtfStream.ToArray());
    rtfStream.Dispose();
    document.Close();
}

/// <summary>
/// Correcting void elements in the HTML. 
/// </summary>
/// <param name="inputString">HTML string with void HTML elements</param>
/// <returns>This method make your HTML to pass the DocIO HTML validation</returns>
private string IgnoreVoidElementsInHTML(string inputString)
{
    inputString = inputString.Replace("<meta http-equiv=\"Content-Type\" content=\"application/xhtml+xml; charset=utf-8\">", "")
    inputString = inputString.Replace("<br>", "<br/>");
    inputString = inputString.Replace("\n", "");
    inputString = inputString.Replace("\r", "");
    inputString = inputString.Replace("<title></title>", "");
    inputString = inputString.Replace("﻿<?xml version=\"1.0\" encoding=\"utf-8\"?><!DOCTYPE html PUBLIC" +
        " \"-//W3C//DTD XHTML 1.1//EN\" \"http://www.w3.org/TR/xhtml11/DTD/xhtml11.dtd\">", "");
    return inputString;
}
{% endhighlight %}

{% endtabs %}

N> While loading HTML content in a Word document, DocIO will perform XHTML 1.0 validation and HTML will be loaded only if the validation is passed. Kindly refer [`this`](https://help.syncfusion.com/file-formats/docio/html) documentation to know about HTML Validation.

The sample illustrating loading and saving RTF content in RichTextEditor can be downloaded [`here`](https://www.syncfusion.com/downloads/support/directtrac/general/ze/RTFManipulation-20682191.zip).