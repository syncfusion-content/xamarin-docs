---
layout: post
title:  Search for a Text Instance in Xamarin Pdf Viewer | Syncfusion
description: Search text support allows the user to locate and highlight text instances in the PDF document using PDF Viewer Xamarin.Forms
platform: Xamarin
control: SfPdfViewer
documentation: ug
---

# Search for a text instance

PDF Viewer provides support to find and highlight texts in the PDF document and it provides the following commands to perform text search operation.

<table>

<tr>
<th>Command/Binding property</th>
<th>Action</th>
</tr>

<tr>
<td>SearchTextCommand</td>
<td>Command that is executed to search for the specified text instance that is provided as the command parameter.</td>
</tr>

<tr>
<td>CancelSearchTextCommand</td>
<td>Command that is executed to cancel the text search operation when it is in progress and used to clear the highlighted text instances when the text search is completed.</td>
</tr>

<tr>
<td>SearchNextTextCommand</td>
<td>Command that is executed to navigate to the next text instance being searched.</td>
</tr>

<tr>
<td>SearchPreviousTextCommand</td>
<td>Command that is executed to navigate to the previous text instance of the text.</td>
</tr>

</table>

## How to initiate text search?

SearchTextCommand is used to initiate the text search, it takes the text to be searched as a parameter. The command searches for the text in the current page and highlights all the instances of the texts in complete document.

{% tabs %}
{% highlight xaml %}

<Entry x:Name="textSearchEntry" FontSize="18" HorizontalTextAlignment="Center" HorizontalOptions="Fill" VerticalOptions="Center"/>

<Button x:Name="searchTextButton" BackgroundColor="Transparent" Image="SearchIcon.png" HorizontalOptions="Start" Command="{Binding SearchTextCommand, Source={x:Reference Name=pdfViewerControl}}" CommandParameter="{Binding Source ={x:Reference textSearchEntry}, Path=Text}"/>

{% endhighlight %}
{% endtabs %}

Here the text entered in the textSearchEntry control is provided as the parameter to the SearchTextCommand. 

## How to identify if there is no instance of the text being searched?

SearchCompleted event of the PDF viewer can be used to identify if no instance of the searched text is found in the PDF document. This event has an event argument “NoMatchFound”, when this it is true it means that the document does not have any match to the text searched and vice versa.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewerControl" InputFileStream="{Binding PdfDocumentStream}" SearchCompleted="pdfViewerControl_SearchCompleted" />

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

private void pdfViewerControl_SearchCompleted(object sender, TextSearchCompletedEventArgs args)
{
    bool isNoMatchFound = args.NoMatchFound;
}

{% endhighlight %}
{% endtabs %}

## How to navigate to the next instance of the text?

SearchNextTextCommand is used to navigate to the next text instances in the PDF document. This command will highlight the current instance of the text with dark blue and all other instances in light blue. On executing the command continuously, the highlighted instance will navigate down the pages.

{% tabs %}
{% highlight xaml %}

<Entry x:Name="textSearchEntry" FontSize="18" HorizontalTextAlignment="Center" HorizontalOptions="Fill" VerticalOptions="Center"/>

<Button x:Name="searchTextButton" BackgroundColor="Transparent" Image="SearchIcon.png" HorizontalOptions="Start" Command="{Binding SearchNextTextCommand, Source={x:Reference Name=pdfViewerControl}}" CommandParameter="{Binding Source ={x:Reference textSearchEntry}, Path=Text}"/>

{% endhighlight %}
{% endtabs %}

This command works both with and without a parameter. When a text parameter is provided to this command, it searches for the text provided as the parameter, when no parameter is sent to this command, it searches for the text that is provided as the parameter to the SearchTextCommand.

## How to navigate to the previous instance of the text?

SearchPreviousTextCommand is used to navigate to the previous text instances in the PDF document. This command will highlight the current instance of the text with dark blue and all other instances in light blue. On executing the command continuously, the highlighted instance will navigate upwards in the pages.

{% tabs %}
{% highlight xaml %}

<Entry x:Name="textSearchEntry" FontSize="18" HorizontalTextAlignment="Center" HorizontalOptions="Fill" VerticalOptions="Center"/>

<Button x:Name="searchTextButton" BackgroundColor="Transparent" Image="SearchIcon.png" HorizontalOptions="Start" Command="{Binding SearchPreviousTextCommand, Source={x:Reference Name=pdfViewerControl}}" CommandParameter="{Binding Source ={x:Reference textSearchEntry}, Path=Text}"/>

{% endhighlight %}
{% endtabs %}

This command works both with and without a parameter. When a text parameter is provided to this command, it searches for the text provided as the parameter, when no parameter is sent to this command, it searches for the text that is provided as the parameter to the SearchTextCommand. 

## How to identify if a complete cycle of text search is performed?

The first instance of the text in the page the text search is initiated is the first instance of the text, this first instance would be reset when we manually scroll the PDF document while navigating using the SearchNextTextCommand or SearchPreviousTextCommand. 

When the search happens to hit the first instance again, the NoMoreOccurrence property of the TextSearchEventArgs of SearchCompleted event will be set to true.

For instance, if the text search is initiated at page 10 of a PDF document, the first instance in the page 10 will be considered as the first instance, on the occurrence of the same instance again in the cycle of text search NoMoreOccurrence property will be set to true.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfPdfViewer x:Name="pdfViewerControl" InputFileStream="{Binding PdfDocumentStream}" SearchCompleted="pdfViewerControl_SearchCompleted" />

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

private void pdfViewerControl_SearchCompleted(object sender, TextSearchEventArgs args)
{
    bool isNoMoreOccurrenceFound = args.NoMoreOccurrence;
}

{% endhighlight %}
{% endtabs %}

## How to cancel text search?

CancelSearchTextCommand is used to cancel the text search progress. When the text search is in progress this command can be used to cancel the same, when text search is completed, this command can be used to clear all the highlighted texts in the PDF viewer.

{% tabs %}
{% highlight xaml %}

<Button x:Name="cancelSearchButton" Grid.Column="3" BackgroundColor="Transparent" Image="CancelSearch.png" HorizontalOptions="Start" VerticalOptions="Center" Command="{Binding CancelSearchTextCommand, Source={x:Reference Name=pdfViewerControl}}"/>

{% endhighlight %}
{% endtabs %}

## How to track search progress?

Text search progress can be tracked using the TextSearchInitiated event and TextMatchFound event. 

### SearchInitiated

TextSearchInitiated event will be triggered soon after the call of the SearchTextCommand, the event argument of this event will contain details about the text being searched. 

### TextMatchFound

TextMatchFound event will be triggered once when the match of the text is found in the page of the PDF document. When text search is triggered using SearchTextCommand this event would be triggered for every page in which the match is found, when text search is triggered using SearchPreviousCommand or SearchNextCommand this event would be triggered for every match being found.

### SearchCompleted

TextSearchCompleted event will be triggered once when all the pages are being search for the match of the input text at-least once. The event argument would contain properties NoMatchFound and NoMoreOccurrenceFound.

When NoMatchFound is set to true, it means that the PDF viewer could not find any match for the searched text in the PDF document.

When NoMoreOccurrence is set to true, it means that the PDF viewer had completed one full cycle of search and has hit the first instance again.

## Implementing search bar with search features.

With the continuation of the getting started sample, you can extend the UI design to perform the text search in the PDF Viewer. Design the search toolbar in parallel to the main toolbar, here when the main toolbar is visible, search bar will be invisible and vice versa.

* Main toolbar – A new option to initiate text search toolbar will be added to the existing options.
* Search toolbar - A new and separate toolbar is created to search a text instance – it includes option to enter the text, perform search, cancel search and navigate back to the main toolbar.

In the PdfViewerViewModel class, create a new command (named – SearchAndToolbarToggleCommand) to toggle between the main toolbar and search toolbar. The view model class after the creation of the command and necessary boolean variables to toggle the visibility will be like

{% tabs %}
{% highlight c# %}

using System.IO;
using System.Reflection;
using System.ComponentModel;
using System.Windows.Input;
using Xamarin.Forms;

namespace GettingStarted
{
    class PdfViewerViewModel : INotifyPropertyChanged
    {
        private Stream m_pdfDocumentStream;
        private bool m_isToolbarVisible = true;
        private bool m_isSearchBarVisible = false;
        /// <summary>
        /// An event to detect the change in the value of a property.
        /// </summary>
        public event PropertyChangedEventHandler PropertyChanged;

        /// <summary>
        /// Command used to toggle between search bar and document toolbar.
        /// </summary>
        public ICommand SearchAndToolbarToggleCommand { get; set; }

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
        /// Gets or sets the bool value which will toggle the visibility of the toolbar.
        /// </summary>
        /// <remarks>
        /// The value true will make the toolbar visible and false would make the toolbar invisible.
        /// </remarks>
        public bool IsToolbarVisible
        {
            get { return m_isToolbarVisible; }
            set
            {
                if (m_isToolbarVisible == value)
                    return;
                m_isToolbarVisible = value;
                NotifyPropertyChanged("IsToolbarVisible");
            }
        }        

        /// <summary>
        /// Gets or sets the bool value which will toggle the visibility of the search bar.
        /// </summary>
        /// <remarks>
        /// The value true will make the toolbar visible and false would make the search bar invisible.
        /// </remarks>
        public bool IsSearchBarVisible
        {
            get { return m_isSearchBarVisible; }
            set
            {
                if (m_isSearchBarVisible == value)
                    return;
                m_isSearchBarVisible = value;
                NotifyPropertyChanged("IsSearchBarVisible");
            }
        }

        /// <summary>
        /// Constructor of the view model class
        /// </summary>
        public PdfViewerViewModel()
        {
            //Accessing the PDF document that is added as embedded resource as stream.
            m_pdfDocumentStream = typeof(App).GetTypeInfo().Assembly.GetManifestResourceStream("GettingStarted.Assets.GIS Succinctly.pdf");
            //Command used to toggle the visibility of the toolbar and search bar.
            SearchAndToolbarToggleCommand= new Command<object>(OnSearchAndToolbarToggleCommand, CanExecute);
        }
        
        private void NotifyPropertyChanged(string propertyName)
        {
            if (PropertyChanged != null)
            {
                PropertyChanged(this, new PropertyChangedEventArgs(propertyName));
            }
        }        

        private bool CanExecute(object parameter)
        {
            return true;
        }

        /// <summary>
        /// Method used to toggle the visibility of the toolbar and search bar.
        /// </summary>
        private void OnSearchAndToolbarToggleCommand(object destinationPageParam)
        {
            IsToolbarVisible = !IsToolbarVisible;
            IsSearchBarVisible = !IsToolbarVisible;
        }
    }
}

{% endhighlight %}
{% endtabs %}

The complete XAML code after the design of the search bar will look like below

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
            <Grid x:Name="toolbar" Grid.Row="0" BackgroundColor="#E9E9E9" HorizontalOptions="Fill" VerticalOptions="Fill" IsVisible="{Binding IsGridVisible}">
                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="1*" />
                    <ColumnDefinition Width="0.4*" />
                    <ColumnDefinition Width="1*" />
                    <ColumnDefinition Width="1*" />
                    <ColumnDefinition Width="1*" />
                    <ColumnDefinition Width="*"/>
                    <ColumnDefinition Width="1*" />
                </Grid.ColumnDefinitions>
                <Entry Keyboard="Numeric" FontSize="18" x:Name="pageNumberEntry" HorizontalTextAlignment="Center" Grid.Column="0" VerticalOptions="Center" Text="{Binding PageNumber, Source={x:Reference Name=pdfViewerControl}}"/>
                <Label Text="/" Grid.Column="1" FontSize="18" x:Name="slashLabel"  VerticalTextAlignment="Center" HorizontalTextAlignment="Center" HorizontalOptions="FillAndExpand" VerticalOptions="Center"/>
                <Label x:Name="pageCountLabel" Grid.Column="2" FontSize="18" VerticalTextAlignment="Center" HorizontalTextAlignment="Center" HorizontalOptions="FillAndExpand" VerticalOptions="Center" Text="{Binding PageCount, Source={x:Reference Name=pdfViewerControl}}"/>
                <Button x:Name="goToNextButton"  Grid.Column="3" BackgroundColor="Transparent" Image="PageDown.png" HorizontalOptions="Center" VerticalOptions="Center" Command="{Binding GoToNextPageCommand, Source={x:Reference Name=pdfViewerControl}}"/>
                <Button x:Name="goToPreviousButton" Grid.Column="4" BackgroundColor="Transparent" Image="PageUp.png" HorizontalOptions="Center" VerticalOptions="Center" Command="{Binding GoToPreviousPageCommand, Source={x:Reference Name=pdfViewerControl}}"/>
                <Button x:Name="searchButton" Grid.Column="6" BackgroundColor="Transparent" Image="SearchIcon.png" HorizontalOptions="Start" Command="{Binding SearchAndToolbarToggleCommand}"/>
            </Grid>
            <Grid x:Name="searchBar" Grid.Row="0" BackgroundColor="#E9E9E9" HorizontalOptions="Fill" VerticalOptions="Fill" IsVisible="{Binding IsSearchBarVisible}">
                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="*" />
                    <ColumnDefinition Width="5*" />
                    <ColumnDefinition Width="1.5*" />
                    <ColumnDefinition Width="1.5*" />
                    <ColumnDefinition Width="1.5*" />
                </Grid.ColumnDefinitions>
                <Button x:Name="backIcon" Grid.Column="0" BackgroundColor="Transparent" Image="BackIcon.png" HorizontalOptions="Start" VerticalOptions="Center" Command="{Binding SearchAndToolbarToggleCommand}"/>
                <Entry Grid.Column="1" x:Name="textSearchEntry" FontSize="18" HorizontalTextAlignment="Center" HorizontalOptions="Fill" VerticalOptions="Center"/>
                <Button x:Name="searchTextButton" Grid.Column="2" BackgroundColor="Transparent" Image="SearchIcon.png" HorizontalOptions="Start" Command="{Binding SearchTextCommand, Source={x:Reference Name=pdfViewerControl}}" CommandParameter="{Binding Source ={x:Reference textSearchEntry}, Path=Text}"/>
                <Button x:Name="cancelSearchButton" Grid.Column="3" BackgroundColor="Transparent" Image="CancelSearch.png" HorizontalOptions="Start" VerticalOptions="Center" Command="{Binding CancelSearchTextCommand, Source={x:Reference Name=pdfViewerControl}}"/>
            </Grid>
        </AbsoluteLayout>
        <Grid x:Name="pdfViewGrid" Grid.Row="1">
            <syncfusion:SfPdfViewer x:Name="pdfViewerControl" InputFileStream="{Binding PdfDocumentStream}"/>
        </Grid>
    </Grid>
</ContentPage>

{% endhighlight %}
{% endtabs %}

## Customizing search highlight color

The colors in which the current instance and other instances are highlighted can be customized. The TextSearchSettings class in the PDF viewer instance can be used for this purpose.

{% tabs %}
{% highlight c# %}

pdfViewerControl.TextSearchSettings.OtherInstanceColor = Color.FromRgba(255, 255, 0, 50);
pdfViewerControl.TextSearchSettings.CurrentInstanceColor = Color.FromRgba(255, 255, 0, 90);
{% endhighlight %}
{% endtabs %}
{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             x:Class="GettingStarted.MainPage"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfPdfViewer.XForms;assembly=Syncfusion.SfPdfViewer.XForms"
             >
	 <ContentPage.Resources>
        <ResourceDictionary>
            <sfpdfviewer:TextSearchSettings x:Key="SearchSettings">
                <sfpdfviewer:TextSearchSettings.CurrentInstanceColor>
                    <Color>#90FFFF00</Color>
                </sfpdfviewer:TextSearchSettings.CurrentInstanceColor>
                <sfpdfviewer:TextSearchSettings.OtherInstanceColor>
                    <Color>#50FFFF00</Color>
                </sfpdfviewer:TextSearchSettings.OtherInstanceColor>
            </sfpdfviewer:TextSearchSettings>
        </ResourceDictionary>
    </ContentPage.Resources>
    <Grid x:Name="mainGrid">
            <syncfusion:SfPdfViewer x:Name="pdfViewerControl" TextSearchSettings="{StaticResource Key=SearchSettings}"/>
    </Grid>
</ContentPage>
{% endhighlight %}
{% endtabs %}

![Text search in PDF viewer](pdfviewer_images/textsearch.png)