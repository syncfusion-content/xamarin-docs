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