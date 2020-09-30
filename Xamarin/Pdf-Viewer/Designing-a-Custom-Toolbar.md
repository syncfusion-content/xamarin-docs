---
layout: post
title:  Designing a Custom Toolbar in Xamarin Pdf Viewer | Syncfusion
description: This section explains on designing a custom toolbar in Pdf Viewer (SfPdfViewer) for Xamarin platform.
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Designing a custom toolbar

The built-in toolbar of the PDF Viewer can be disabled and a custom toolbar can be used at the sample. The below code snippet demonstrates how to create a simple toolbar for PDF Viewer with the options such as current page number, total page count in the PDF document, go to previous page and go to next page.

In this project, two images have been used with the names - “PageDown.png” and “PageUp.png”, place the images in the below mentioned location within the respective projects.

<table>

<tr>
<th>OS</th>
<th>Location</th>
</tr>

<tr>
<td>Android</td>
<td>Resources/drawable</td>
</tr>

<tr>
<td>iOS</td>
<td>Resources</td>
</tr>

<tr>
<td>UWP</td>
<td>Directly in the project location</td>
</tr>

</table>

The MainPage.xaml would be as mentioned below.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfPdfViewer.XForms;assembly=Syncfusion.SfPdfViewer.XForms"
             >
    <ContentPage.BindingContext>
        <local:PdfViewerViewModel></local:PdfViewerViewModel>
    </ContentPage.BindingContext>
    <Grid x:Name="mainGrid">
        <Grid.RowDefinitions>
            <RowDefinition Height="50" />
            <RowDefinition Height="*" />
        </Grid.RowDefinitions>
        <AbsoluteLayout>
            <Grid x:Name="toolbar" Grid.Row="0" BackgroundColor="#E9E9E9" HorizontalOptions="Fill" VerticalOptions="Fill">
                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="1*" />
                    <ColumnDefinition Width="0.4*" />
                    <ColumnDefinition Width="1*" />
                    <ColumnDefinition Width="1*" />
                    <ColumnDefinition Width="1*" />
                </Grid.ColumnDefinitions>
                <Entry Keyboard="Numeric" FontSize="18" x:Name="pageNumberEntry" HorizontalTextAlignment="Center" Grid.Column="0" VerticalOptions="Center" Text="{Binding PageNumber, Source={x:Reference Name=pdfViewerControl}}"/>
                <Label Text="/" Grid.Column="1" FontSize="18" x:Name="slashLabel"  VerticalTextAlignment="Center" HorizontalTextAlignment="Center" HorizontalOptions="FillAndExpand" VerticalOptions="Center"/>
                <Label x:Name="pageCountLabel" Grid.Column="2" FontSize="18" VerticalTextAlignment="Center" HorizontalTextAlignment="Center" HorizontalOptions="FillAndExpand" VerticalOptions="Center" Text="{Binding PageCount, Source={x:Reference Name=pdfViewerControl}}"/>
                <Button x:Name="goToNextButton"  Grid.Column="3" BackgroundColor="Transparent" Image="PageDown.png" HorizontalOptions="Center" VerticalOptions="Center" Command="{Binding GoToNextPageCommand, Source={x:Reference Name=pdfViewerControl}}"/>
                <Button x:Name="goToPreviousButton" Grid.Column="4" BackgroundColor="Transparent" Image="PageUp.png" HorizontalOptions="Center" VerticalOptions="Center" Command="{Binding GoToPreviousPageCommand, Source={x:Reference Name=pdfViewerControl}}"/>
            </Grid>
        </AbsoluteLayout>
        <Grid x:Name="pdfViewGrid" Grid.Row="1">
            <syncfusion:SfPdfViewer x:Name="pdfViewerControl" InputFileStream="{Binding PdfDocumentStream}"/>
        </Grid>
    </Grid>
</ContentPage>

{% endhighlight %}
{% endtabs %}

The final output will look like the below on iOS, Android and Windows (UWP) devices

![SfPdfViewer](pdfviewer_images/PdfViewerWithCustomToolbar.png)

This demo can be downloaded from the below link.

<http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStarted-1533352385>
