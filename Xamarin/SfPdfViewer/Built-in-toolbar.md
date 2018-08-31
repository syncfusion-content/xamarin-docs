---
layout: post
title:  Working with built-in toolbar
description: Working with built-in toolbar
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Working with built-in toolbar

The SfPdfViewer has a built-in toolbar, which has provisions to perform majority of the operations in the PDF viewer. You  can disable the built-in toolbar and develop your own toolbar.

## How to disable the built-in toolbar of SfPdfViewer?

The following API is used to disable the built-in toolbar in the PDF viewer.

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

N>**By default, the built-in toolbar of SfPdfViewer is always visible.

