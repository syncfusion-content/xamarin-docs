---
layout: post
title:  Built-in toolbar in PDF Viewer Xamarin.Forms | Syncfusion
description: The PDF Viewer Xamarin.Forms allows the users to perform almost all operations in PDF Viewer using the built-in toolbar.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Working with built-in toolbar

The SfPdfViewer has a built-in toolbar that has provisions to perform majority of the operations in the PDF Viewer and that can be disabled or enabled. You  can disable the built-in toolbar and develop your own toolbar.

## How to disable/enable built-in toolbar

By default, the built-in toolbar will be enabled. It can be disabled by setting the Toolbar.Enabled property of PDF Viewer to false.

{% tabs %}
{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace: PdfViewerGettingStarted "
             xmlns:syncfusion ="clr-namespace:Syncfusion.SfPdfViewer.XForms;assembly=Syncfusion.SfPdfViewer.XForms"
             x:Class=" PdfViewerGettingStarted.MainPage">

  <ContentPage.Resources>
        <ResourceDictionary>
            <syncfusion:Toolbar x:Key="ToolbarSettings">
                <syncfusion:Toolbar.Enabled>false
                </syncfusion:Toolbar.Enabled>
            </syncfusion:Toolbar>
        </ResourceDictionary>
    </ContentPage.Resources>

    <ContentPage.Content>
        <syncfusion:SfPdfViewer x:Name="pdfViewerControl" Toolbar = "{StaticResource ToolbarSettings}"/>
    </ContentPage.Content>

</ContentPage>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

pdfViewerControl.Toolbar.Enabled = false;

{% endhighlight %}
{% endtabs %}

![Build-in-toolbar disable in PDF Viewer](pdfviewer_images/ToolbarDisabled.png)

The toolbar can be enabled by setting the Toolbar.Enabled property to true.

{% tabs %}
{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace: PdfViewerGettingStarted "
             xmlns:syncfusion ="clr-namespace:Syncfusion.SfPdfViewer.XForms;assembly=Syncfusion.SfPdfViewer.XForms"
             x:Class=" PdfViewerGettingStarted.MainPage">

  <ContentPage.Resources>
        <ResourceDictionary>
            <syncfusion:Toolbar x:Key="ToolbarSettings">
                <syncfusion:Toolbar.Enabled>true
                </syncfusion:Toolbar.Enabled>
            </syncfusion:Toolbar>
        </ResourceDictionary>
    </ContentPage.Resources>

    <ContentPage.Content>
        <syncfusion:SfPdfViewer x:Name="pdfViewerControl" Toolbar = "{StaticResource ToolbarSettings}"/>
    </ContentPage.Content>

</ContentPage>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

pdfViewerControl.Toolbar.Enabled = true;

{% endhighlight %}
{% endtabs %}

![Build-in-toolbar enable in PDF Viewer](pdfviewer_images/ToolbarEnabled.png)

N>By default, the built-in toolbar of SfPdfViewer is always visible.

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
<td><i>page-view-mode</i></td>
</tr>

<tr>
<td>Continuous page view mode button</td>
<td><i>continuous-pages</i></td>
</tr>

<tr>
<td>Single page view mode button</td>
<td><i>page-by-page</i></td>
</tr>

<tr>
<td>Bookmark button</td>
<td><i>bookmark</i></td>
</tr>

<tr>
<td>Page number entry</td>
<td><i>page-entry</i></td>
</tr>

<tr>
<td>Page count label</td>
<td><i>page-count</i></td>
</tr>

<tr>
<td>Previous page button</td>
<td><i>previous-page</i></td>
</tr>

<tr>
<td>Next page button</td>
<td><i>next-page</i></td>
</tr>

<tr>
<td>Search button</td>
<td><i>search</i></td>
</tr>

<tr>
<td>Search back button</td>
<td><i>search-back</i></td>
</tr>

<tr>
<td>Search Bar</td>
<td><i>search-bar</i></td>
</tr>

<tr>
<td>Clear/Cancel search button</td>
<td><i>search-clear</i></td>
</tr>

<tr>
<td>Search next button</td>
<td><i>search-next</i></td>
</tr>

<tr>
<td>Search previous button</td>
<td><i>search-previous</i></td>
</tr>

<tr>
<td>Search instances label</td>
<td><i>search-instances</i></td>
</tr>

<tr>
<td>More options button</td>
<td><i>more-options</i></td>
</tr>

<tr>
<td>Undo button</td>
<td><i>undo</i></td>
</tr>

<tr>
<td>Redo button</td>
<td><i>redo</i></td>
</tr>

<tr>
<td>Save button</td>
<td><i>save</i></td>
</tr>

<tr>
<td>Print button</td>
<td><i>print</i></td>
</tr>

<tr>
<td>Annotation button</td>
<td><i>annotation</i></td>
</tr>

<tr>
<td>Annotation back button</td>
<td><i>annotation-back</i></td>
</tr>

<tr>
<td>Text markups annotation button</td>
<td><i>text-markups</i></td>
</tr>

<tr>
<td>Text markups back button</td>
<td><i>text-markups-back</i></td>
</tr>

<tr>
<td>Text highlight button</td>
<td><i>text-highlight</i></td>
</tr>

<tr>
<td>Text underline button</td>
<td><i>text-underline</i></td>
</tr>

<tr>
<td>Text strikethrough button</td>
<td><i>text-strikethrough</i></td>
</tr>

<tr>
<td>Shapes annotation button</td>
<td><i>shapes</i></td>
</tr>

<tr>
<td>Shapes back button</td>
<td><i>shapes-back</i></td>
</tr>

<tr>
<td>Rectangle shape button</td>
<td><i>rectangle</i></td>
</tr>

<tr>
<td>Ellipse shape button</td>
<td><i>ellipse</i></td>
</tr>

<tr>
<td>Line shape button</td>
<td><i>line</i></td>
</tr>

<tr>
<td>Arrow shape button</td>
<td><i>arrow</i></td>
</tr>

<tr>
<td>Ink annotation button</td>
<td><i>ink</i></td>
</tr>

<tr>
<td>Ink undo button</td>
<td><i>undo-ink</i></td>
</tr>

<tr>
<td>Ink redo button</td>
<td><i>redo-ink</i></td>
</tr>

<tr>
<td>Ink confirmation button</td>
<td><i>done</i></td>
</tr>

<tr>
<td>Free text annotation button</td>
<td><i>free-text</i></td>
</tr>

<tr>
<td>Signature button</td>
<td><i>signature</i></td>
</tr>

<tr>
<td>Selected annotation button</td>
<td><i>selected-annotation</i></td>
</tr>

<tr>
<td>Edited annotation button</td>
<td><i>edited-annotation</i></td>
</tr>

<tr>
<td>Selected annotation back button</td>
<td><i>selected-annotation-back</i></td>
</tr>

<tr>
<td>Edited annotation back button</td>
<td><i>edited-annotation-back</i></td>
</tr>

<tr>
<td>Selected annotation color button</td>
<td><i>selected-annotation-color</i></td>
</tr>

<tr>
<td>Edited annotation color button</td>
<td><i>edited-annotation-color</i></td>
</tr>

<tr>
<td>Magenta color button</td>
<td><i>magenta</i></td>
</tr>

<tr>
<td>Black color button</td>
<td><i>black</i></td>
</tr>

<tr>
<td>Red color button</td>
<td><i>red</i></td>
</tr>

<tr>
<td>Green color button</td>
<td><i>green</i></td>
</tr>

<tr>
<td>Yellow color button</td>
<td><i>yellow</i></td>
</tr>

<tr>
<td>Blue color button</td>
<td><i>blue</i></td>
</tr>

<tr>
<td>Cyan color button</td>
<td><i>cyan</i></td>
</tr>

<tr>
<td>Color opacity button</td>
<td><i>opacity</i></td>
</tr>

<tr>
<td>Color opacity slider</td>
<td><i>opacity-slider</i></td>
</tr>

<tr>
<td>Font size button</td>
<td><i>font-size</i></td>
</tr>

<tr>
<td>Font size label</td>
<td><i>font-label</i></td>
</tr>

<tr>
<td>Font range slider</td>
<td><i>font-range-slider</i></td>
</tr>

<tr>
<td>Selected annotation thickness button</td>
<td><i>selected-annotation-thickness</i></td>
</tr>

<tr>
<td>Edited annotation thickness button</td>
<td><i>edited-annotation-thickness</i></td>
</tr>

<tr>
<td>First thickness button</td>
<td><i>1pt-thickness</i></td>
</tr>

<tr>
<td>Second thickness button</td>
<td><i>3pt-thickness</i></td>
</tr>

<tr>
<td>Third thickness button</td>
<td><i>5pt-thickness</i></td>
</tr>

<tr>
<td>Fourth thickness button</td>
<td><i>7pt-thickness</i></td>
</tr>

<tr>
<td>Fifth thickness button</td>
<td><i>9pt-thickness</i></td>
</tr>

<tr>
<td>Edited annotation font size button</td>
<td><i>edited-annotation-font-size</i></td>
</tr>

<tr>
<td>Edited annotation modify free text button</td>
<td><i>edited-annotation-modify-free-text</i></td>
</tr>

<tr>
<td>Edited annotation delete button</td>
<td><i>edited-annotation-delete</i></td>
</tr>

</table>