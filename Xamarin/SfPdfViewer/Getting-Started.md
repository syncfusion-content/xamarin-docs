---
layout: post
title:  Getting Started for Essential Xamarin.Forms PDF viewer
description: getting started
platform: Xamarin.Forms
control: SfPdfViewer
documentation: ug
---

# Getting started

This section demonstrates how to create an application that displays a PDF file using SfPdfViewer control.
 
## Assemblies Required

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Essential Studio Installed location}\Essential Studio\{Essential Studio version}\Xamarin\lib

Example: C:\Program Files (x86)\Syncfusion\Essential Studio\15.3.0.28\Xamarin\lib

Refer [this link](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfpdfviewer) to know about the assemblies required for adding SfPdfViewer control in a Xamarin project.

## Creating a simple PDF Viewer application

Create a new cross platform application for Xamarin.Forms.Portable in the Visual Studio with the project name "GettingStarted" and refer the above mentioned assemblies to the respective projects.

An additional step is required to render the SfPdfViewer control in iOS project. You need to create an instance of the SfPdfDocumentViewRenderer class within FinishedLaunching method of AppDelegate class in iOS project as shown below

{% tabs %}
{% highlight c# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    global::Xamarin.Forms.Forms.Init();
    LoadApplication(new App());
    new SfPdfDocumentViewRenderer();
    return base.FinishedLaunching(app, options);
}

{% endhighlight %}
{% endtabs %}

### Loading a PDF using MVVM binding

File handling with Xamarin.Forms can be done using embedded resources or writing against the native filesystem APIs. Please find more details in the below link:

https://developer.xamarin.com/guides/xamarin-forms/application-fundamentals/files/ 

Add a folder in the portable project with the name "Assets" and add the PDF document you need to display in the PDF viewer, here a PDF file named "GIS Succinctly.pdf" was used. In the properties of the PDF document set the build action property to be "Embedded Resource".

Add a folder in the portable project with the name "ViewModel and include a class file with a name "PdfViewerViewModel" inside it. Add below code snippet in the "PdfViewerViewModel" class. Ensure to maintain the namespace as "GettingStarted". 

{% tabs %}
{% highlight c# %}

using System.IO;
using System.Reflection;
using System.ComponentModel;

namespace GettingStarted
{
    class PdfViewerViewModel : INotifyPropertyChanged
    {
        private Stream m_pdfDocumentStream;

        /// <summary>
        /// An event to detect the change in the value of a property.
        /// </summary>
        public event PropertyChangedEventHandler PropertyChanged;

        /// <summary>
        /// The PDF document stream that is loaded into the instance of the PDF viewer. 
        /// </summary>
        public Stream PdfDocumentStream
        {
            get
            {
                return m_pdfDocumentStream;
            }
            set
            {
                m_pdfDocumentStream = value;
                NotifyPropertyChanged("PdfDocumentStream");
            }
        }

        /// <summary>
        /// Constructor of the view model class
        /// </summary>
        public PdfViewerViewModel()
        {
            //Accessing the PDF document that is added as embedded resource as stream.
            m_pdfDocumentStream = typeof(App).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStarted.Assets.GIS Succinctly.pdf");
        }

        private void NotifyPropertyChanged(string propertyName)
        {
            if (PropertyChanged != null)
            {
                PropertyChanged(this, new PropertyChangedEventArgs(propertyName));
            }
        }  
    }
}

{% endhighlight %}
{% endtabs %}

Add the following XAML code in the MainPage.xaml in the portable project.

•	Includes the necessary namespace where the control class resides
•	Set BindingContext of ContentPage to PdfViewerViewModel
•	Includes PDF Viewer into the page
•	Binds InputFileStream property of PDF Viewer control to PdfDocumentStream property of PdfViewerViewModel

{% tabs %}
{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfPdfViewer.XForms;assembly=Syncfusion.SfPdfViewer.XForms"
             >
    <ContentPage.BindingContext>
        <local:PdfViewerViewModel></local:PdfViewerViewModel>
    </ContentPage.BindingContext>
    <Grid x:Name="pdfViewGrid">
        <syncfusion:SfPdfViewer x:Name="pdfViewerControl" InputFileStream="{Binding PdfDocumentStream}"/>
    </Grid> 
</ContentPage>

{% endhighlight %}
{% endtabs %}

Deploying this project to various devices (Android, iOS and Windows) would display the PDF document and allow you to scroll and zoom the pages.

### Loading a PDF in code behind

In code behind a PDF can be loaded to PdfViewer just by using the [LoadDocument](https://help.syncfusion.com/cr/cref_files/xamarin/sfpdfviewer/Syncfusion.SfPdfViewer.XForms~Syncfusion.SfPdfViewer.XForms.SfPdfViewer~LoadDocument.html) method without the need of the "PdfViewerViewModel" class described in the previous section.  Use the following code snippet in the code behind of the XAML page. 

{% tabs %}
{% highlight c# %}

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {
        Stream fileStream; 
        public MainPage()
        {
            InitializeComponent();
        }

        protected override void OnAppearing()
        {
            base.OnAppearing();
            fileStream = typeof(App).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStarted.Assets.GIS Succinctly.pdf");
			//Load the PDF
            pdfViewerControl.LoadDocument(fileStream);
        }
    }
}

{% endhighlight %}
{% endtabs %}

In the XAML code described in the previous section, remove the binding of InputFileStream property of SfPdfViewer and the BindingContext of the page. 

{% tabs %}
{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfPdfViewer.XForms;assembly=Syncfusion.SfPdfViewer.XForms"
             >
    <Grid x:Name="pdfViewGrid">
        <syncfusion:SfPdfViewer x:Name="pdfViewerControl" />
    </Grid> 
</ContentPage>

{% endhighlight %}
{% endtabs %}

## Unloading PDF document from the Viewer

The SfPdfViewer control allows you to unload the PDF document from the viewer, when the PDF document is not in use anymore. This releases the PDF document and all its associated resources of the application.

You need to call the Unload method of SfPdfViewer control as in the below code snippet to achieve the same.

{% tabs %}
{% highlight c# %}

//Unloads the PDF document from the PDF viewer, freeing all the accessed resources.
pdfViewerControl.Unload();

{% endhighlight %}
{% endtabs %}

## How to get & set the current page number?

PDF viewer has a BindableProperty “PageNumber” using which the current page number can be retrieved and it can be set. 

{% tabs %}
{% highlight xaml %}

<Entry Keyboard="Numeric" FontSize="18" x:Name="pageNumberEntry" HorizontalTextAlignment="Center" VerticalOptions="Center" Text="{Binding PageNumber, Source={x:Reference Name=pdfViewerControl}}"/>

{% endhighlight %}
{% endtabs %}

On binding the Entry control to PageNumber property of the PDF viewer instance, the number of the current page being displayed in the PDF viewer will be displayed in the Entry control and the PDF viewer would navigate to the page number being entered in the same. 

## How to get the total page number?

PDF viewer has a BindableProperty “PageCount” using which the total number of pages in the document can be retrieved.

{% tabs %}
{% highlight xaml %}

<Label x:Name="pageCountLabel" FontSize="18" VerticalTextAlignment="Center" HorizontalTextAlignment="Center" HorizontalOptions="FillAndExpand" VerticalOptions="Center" Text="{Binding PageCount, Source={x:Reference Name=pdfViewerControl}}"/>

{% endhighlight %}
{% endtabs %}

On binding the Label to PageCount property of the PDF viewer instance, the total number of pages in the document can be displayed. 

## How to navigate to next page and previous page?

PDF viewer has “GoToNextPageCommand” and “GoToPreviousPageCommand” which will navigate to the next page and previous page respectively. 

{% tabs %}
{% highlight xaml %}

<Button x:Name="goToNextButton"  Grid.Column="3" BackgroundColor="Transparent" Image="PageDown.png" HorizontalOptions="Center" VerticalOptions="Center" Command="{Binding GoToNextPageCommand, Source={x:Reference Name=pdfViewerControl}}"/>

<Button x:Name="goToPreviousButton" Grid.Column="4" BackgroundColor="Transparent" Image="PageUp.png" HorizontalOptions="Center" VerticalOptions="Center" Command="{Binding GoToPreviousPageCommand, Source={x:Reference Name=pdfViewerControl}}"/>

{% endhighlight %}
{% endtabs %}

If the current page is already the last page of PDF document, then GoToNextPageCommand does not have any effect. Similarly, If the current page is already the first page of PDF document, then GoToPreviousPageCommand does not have any effect.

## How to detect a page change?

PDF viewer has PageChanged event, which helps detecting changes in the page being displayed in the viewer. 

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewerControl" Grid.Row="1" PageChanged="pdfViewerControl_PageChanged"/>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

private void pdfViewerControl_PageChanged(object sender, Syncfusion.SfPdfViewer.XForms.PageChangedEventArgs args)
{
    int currentPageNumber = args.PageNumber;
}

{% endhighlight %}
{% endtabs %}

The arguments of the PageChanged event contains details about to which page the document is navigated to.