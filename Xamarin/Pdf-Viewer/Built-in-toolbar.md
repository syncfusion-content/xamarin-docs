---
layout: post
title: Built-In Toolbar in Xamarin Pdf Viewer Control | Syncfusion
description: Learn here all about Working with Built-In Toolbar support in Syncfusion Xamarin Pdf Viewer (SfPdfViewer) control and more.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Working with Built-In Toolbar in Xamarin Pdf Viewer (SfPdfViewer)

The SfPdfViewer has a built-in toolbar that has provisions to perform majority of the operations in the PDF Viewer and that can be shown or hidden. You can hide the built-in toolbar and develop your own toolbar.

## How to show/hide built-in toolbar

By default, the built-in toolbar will be visible. It can be hidden by setting the `IsToolbarVisible` property of PDF Viewer to false.

{% tabs %}
{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace: PdfViewerGettingStarted "
             xmlns:syncfusion ="clr-namespace:Syncfusion.SfPdfViewer.XForms;assembly=Syncfusion.SfPdfViewer.XForms"
             x:Class=" PdfViewerGettingStarted.MainPage">
    <ContentPage.Content>
        <syncfusion:SfPdfViewer x:Name="pdfViewerControl" IsToolbarVisible="False" />
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

pdfViewerControl.IsToolbarVisible = false;

{% endhighlight %}
{% endtabs %}

![Build-in-toolbar disable in PDF Viewer](pdfviewer_images/ToolbarDisabled.png)

The toolbar can be shown by setting the `IsToolbarVisible` property to true.

{% tabs %}
{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace: PdfViewerGettingStarted "
             xmlns:syncfusion ="clr-namespace:Syncfusion.SfPdfViewer.XForms;assembly=Syncfusion.SfPdfViewer.XForms"
             x:Class=" PdfViewerGettingStarted.MainPage">
    <ContentPage.Content>
        <syncfusion:SfPdfViewer x:Name="pdfViewerControl" IsToolbarVisible="True" />
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

pdfViewerControl.IsToolbarVisible = true;

{% endhighlight %}
{% endtabs %}

![Build-in-toolbar enable in PDF Viewer](pdfviewer_images/ToolbarEnabled.png)

N>The older API `SfPdfViewer.Toolbar.Enabled` have been marked as obsolete. 

## How to show/hide built-in toolbar dynamically using data binding

The below code snippet illustrates how to show/hide the built-in toolbar dynamically at run time using data binding.

{% tabs %}
{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace: PdfViewerGettingStarted "
             xmlns:syncfusion ="clr-namespace:Syncfusion.SfPdfViewer.XForms;assembly=Syncfusion.SfPdfViewer.XForms"
             x:Class=" PdfViewerGettingStarted.MainPage">			 
	<ContentPage.BindingContext>
        <local:PdfViewerViewModel></local:PdfViewerViewModel>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <syncfusion:SfPdfViewer x:Name="pdfViewerControl" IsToolbarVisible={Binding ToolbarVisible} />
    </ContentPage.Content>
</ContentPage>          

{% endhighlight %}
{% endtabs %}

## How to disable/enable bookmark

By default, the bookmark button will be enabled. It can be disabled by setting the `BookmarkNavigationEnabled` property of PDF Viewer to false.  

{% tabs %}
{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace: PdfViewerGettingStarted "
             xmlns:syncfusion ="clr-namespace:Syncfusion.SfPdfViewer.XForms;assembly=Syncfusion.SfPdfViewer.XForms"
             x:Class=" PdfViewerGettingStarted.MainPage">
    <ContentPage.Content>
        <syncfusion:SfPdfViewer x:Name="pdfViewerControl" BookmarkNavigationEnabled="False"/>
    </ContentPage.Content>
</ContentPage>          

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

//Bookmark feature is disabled
pdfViewerControl. BookmarkNavigationEnabled = false;             

{% endhighlight %}
{% endtabs %}

## How to show/hide the toolbar items in built-in toolbar

The built-in toolbar in PdfViewer includes various items to perform operations such as navigation (bookmark, hyperlink and table of contents) and reviewing the PDF files with different annotation tools. These toolbar items can be hidden and customized as per the requirement.

The items in the toolbar is shown or hidden using the following API.

{% tabs %}
{% highlight c# %}

//Show/Hide the toolbar item(s)
pdfViewerControl.Toolbar.SetToolbarItemVisibility(string itemName, bool isVisible);             

{% endhighlight %}
{% endtabs %}

For an example, the following code snippet explains how to hide the `Save` button from the built-in toolbar.

{% tabs %}
{% highlight c# %}

//Hides the 'Save' button
pdfViewerControl.Toolbar.SetToolbarItemVisibility(“save”, false);        

{% endhighlight %}
{% endtabs %}

Similarly, the other items can be hidden by mentioning the appropriate key names. Find the key names of all the toolbar items from the following table:

<table>

<tr>
<th>Toolbar Item Name</th>
<th>Key Name</th>
</tr>

<tr>
<td>Page view mode button</td>
<td><i><b>page-view-mode</b></i></td>
</tr>

<tr>
<td>Continuous page view mode button</td>
<td><i><b>continuous-pages</b></i></td>
</tr>

<tr>
<td>Single page view mode button</td>
<td><i><b>page-by-page</b></i></td>
</tr>

<tr>
<td>Bookmark button</td>
<td><i><b>bookmark</b></i></td>
</tr>

<tr>
<td>Page number entry</td>
<td><i><b>page-entry</b></i></td>
</tr>

<tr>
<td>Page count label</td>
<td><i><b>page-count</b></i></td>
</tr>

<tr>
<td>Previous page button</td>
<td><i><b>previous-page</b></i></td>
</tr>

<tr>
<td>Next page button</td>
<td><i><b>next-page</b></i></td>
</tr>

<tr>
<td>Search button</td>
<td><i><b>search</b></i></td>
</tr>

<tr>
<td>Search back button</td>
<td><i><b>search-back</b></i></td>
</tr>

<tr>
<td>Search Bar</td>
<td><i><b>search-bar</b></i></td>
</tr>

<tr>
<td>Clear/Cancel search button</td>
<td><i><b>search-clear</b></i></td>
</tr>

<tr>
<td>Search next button</td>
<td><i><b>search-next</b></i></td>
</tr>

<tr>
<td>Search previous button</td>
<td><i><b>search-previous</b></i></td>
</tr>

<tr>
<td>Search instances label</td>
<td><i><b>search-instances</b></i></td>
</tr>

<tr>
<td>More options button</td>
<td><i><b>more-options</b></i></td>
</tr>

<tr>
<td>Undo button</td>
<td><i><b>undo</b></i></td>
</tr>

<tr>
<td>Redo button</td>
<td><i><b>redo</b></i></td>
</tr>

<tr>
<td>Save button</td>
<td><i><b>save</b></i></td>
</tr>

<tr>
<td>Print button</td>
<td><i><b>print</b></i></td>
</tr>

<tr>
<td>Annotation button</td>
<td><i><b>annotation</b></i></td>
</tr>

<tr>
<td>Annotation back button</td>
<td><i><b>annotation-back</b></i></td>
</tr>

<tr>
<td>Text markups annotation button</td>
<td><i><b>text-markups</b></i></td>
</tr>

<tr>
<td>Text markups back button</td>
<td><i><b>text-markups-back</b></i></td>
</tr>

<tr>
<td>Text highlight button</td>
<td><i><b>text-highlight</b></i></td>
</tr>

<tr>
<td>Text underline button</td>
<td><i><b>text-underline</b></i></td>
</tr>

<tr>
<td>Text strikethrough button</td>
<td><i><b>text-strikethrough</b></i></td>
</tr>

<tr>
<td>Shapes annotation button</td>
<td><i><b>shapes</b></i></td>
</tr>

<tr>
<td>Shapes back button</td>
<td><i><b>shapes-back</b></i></td>
</tr>

<tr>
<td>Rectangle shape button</td>
<td><i><b>rectangle</b></i></td>
</tr>

<tr>
<td>Ellipse shape button</td>
<td><i><b>ellipse</b></i></td>
</tr>

<tr>
<td>Line shape button</td>
<td><i><b>line</b></i></td>
</tr>

<tr>
<td>Arrow shape button</td>
<td><i><b>arrow</b></i></td>
</tr>

<tr>
<td>Ink annotation button</td>
<td><i><b>ink</b></i></td>
</tr>

<tr>
<td>Ink undo button</td>
<td><i><b>undo-ink</b></i></td>
</tr>

<tr>
<td>Ink redo button</td>
<td><i><b>redo-ink</b></i></td>
</tr>

<tr>
<td>Ink confirmation button</td>
<td><i><b>done</b></i></td>
</tr>

<tr>
<td>Free text annotation button</td>
<td><i><b>free-text</b></i></td>
</tr>

<tr>
<td>Signature button</td>
<td><i><b>signature</b></i></td>
</tr>

<tr>
<td>Selected annotation button</td>
<td><i><b>selected-annotation</b></i></td>
</tr>

<tr>
<td>Edited annotation button</td>
<td><i><b>edited-annotation</b></i></td>
</tr>

<tr>
<td>Selected annotation back button</td>
<td><i><b>selected-annotation-back</b></i></td>
</tr>

<tr>
<td>Edited annotation back button</td>
<td><i><b>edited-annotation-back</b></i></td>
</tr>

<tr>
<td>Selected annotation color button</td>
<td><i><b>selected-annotation-color</b></i></td>
</tr>

<tr>
<td>Edited annotation color button</td>
<td><i><b>edited-annotation-color</b></i></td>
</tr>

<tr>
<td>Magenta color button</td>
<td><i><b>magenta</b></i></td>
</tr>

<tr>
<td>Black color button</td>
<td><i><b>black</b></i></td>
</tr>

<tr>
<td>Red color button</td>
<td><i><b>red</b></i></td>
</tr>

<tr>
<td>Green color button</td>
<td><i><b>green</b></i></td>
</tr>

<tr>
<td>Yellow color button</td>
<td><i><b>yellow</b></i></td>
</tr>

<tr>
<td>Blue color button</td>
<td><i><b>blue</b></i></td>
</tr>

<tr>
<td>Cyan color button</td>
<td><i><b>cyan</b></i></td>
</tr>

<tr>
<td>Color opacity button</td>
<td><i><b>opacity</b></i></td>
</tr>

<tr>
<td>Color opacity slider</td>
<td><i><b>opacity-slider</b></i></td>
</tr>

<tr>
<td>Font size button</td>
<td><i><b>font-size</b></i></td>
</tr>

<tr>
<td>Font size label</td>
<td><i><b>font-label</b></i></td>
</tr>

<tr>
<td>Font range slider</td>
<td><i><b>font-range-slider</b></i></td>
</tr>

<tr>
<td>Selected annotation thickness button</td>
<td><i><b>selected-annotation-thickness</b></i></td>
</tr>

<tr>
<td>Edited annotation thickness button</td>
<td><i><b>edited-annotation-thickness</b></i></td>
</tr>

<tr>
<td>First thickness button</td>
<td><i><b>1pt-thickness</b></i></td>
</tr>

<tr>
<td>Second thickness button</td>
<td><i><b>3pt-thickness</b></i></td>
</tr>

<tr>
<td>Third thickness button</td>
<td><i><b>5pt-thickness</b></i></td>
</tr>

<tr>
<td>Fourth thickness button</td>
<td><i><b>7pt-thickness</b></i></td>
</tr>

<tr>
<td>Fifth thickness button</td>
<td><i><b>9pt-thickness</b></i></td>
</tr>

<tr>
<td>Edited annotation font size button</td>
<td><i><b>edited-annotation-font-size</b></i></td>
</tr>

<tr>
<td>Edited annotation modify free text button</td>
<td><i><b>edited-annotation-modify-free-text</b></i></td>
</tr>

<tr>
<td>Edited annotation delete button</td>
<td><i><b>edited-annotation-delete</b></i></td>
</tr>

</table>

N>You can refer to our [Xamarin PDF Viewer](https://www.syncfusion.com/xamarin-ui-controls/xamarin-pdf-viewer) feature tour page for its groundbreaking feature representations. You can also explore our [Xamarin.Forms PDF Viewer example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/PdfViewer) to knows the functionalities of each feature.
