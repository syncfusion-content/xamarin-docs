---
layout: post
title: Getting started | SfListView | Xamarin | Syncfusion
description: Describes about quick overview for getting started with the ListView in Xamarin.Forms, binding data, layouts, sorting, filtering and much more.
platform: xamarin
control: SfListView
documentation: ug
---

# Getting Started with Xamarin ListView (SfListView)

This section provides a quick overview for getting started with the SfListView for Xamarin.Forms. Walk through the entire process of creating the real world SfListView.

## Assembly Deployment

After installing Essential Studio for Xamarin, you can find all the required assemblies in the {Syncfusion Essential Studio Installed location}\Essential Studio\{{ site.releaseversion }}\Xamarin\lib installation folder.

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\Xamarin\lib

Refer [control dependencies](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sflistview) section to get the list of assemblies or NuGet package needs to be added as reference to use the SfListView control in any application.

N> Assemblies can be found in an unzipped package location in Mac.

## Adding SfListView reference

You can add SfListView reference using one of the following methods:

**Method 1: Adding SfListView reference from nuget.org**

Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfListView to your project, open the NuGet package manager in Visual Studio, search for [Syncfusion.Xamarin.SfListView](https://www.nuget.org/packages/Syncfusion.Xamarin.SfListView), and then install it.

![Adding SfListView reference from NuGet](SfListView_images/Adding SfListView reference.png)

N> Install the same version of SfListView NuGet in all the projects.

**Method 2: Adding SfListView reference from toolbox**

Syncfusion also provides Xamarin Toolbox. Using this toolbox, you can drag the SfListView control to the XAML page. It will automatically install the required NuGet packages and add the namespace to the page. To install Syncfusion Xamarin Toolbox, refer to [Toolbox](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfListView assemblies manually from the installed location**

If you prefer to manually reference the assemblies instead referencing from NuGet, add the following assemblies in respective projects.

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.DataSource.Portable.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.GridCommon.Portable.dll<br/>Syncfusion.SfListView.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.DataSource.Portable.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.GridCommon.Portable.dll<br/>Syncfusion.SfListView.XForms.Android.dll<br/>Syncfusion.SfListView.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.DataSource.Portable.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.GridCommon.Portable.dll<br/>Syncfusion.SfListView.XForms.iOS.dll<br/>Syncfusion.SfListView.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.DataSource.Portable.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.GridCommon.Portable.dll<br/>Syncfusion.SfListView.XForms.UWP.dll<br/>Syncfusion.SfListView.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>macOS</td>
<td>pcl\Syncfusion.DataSource.Portable.dll<br/>pcl\Syncfusion.Core.XForms.dll<br/>pcl\Syncfusion.GridCommon.Portable.dll<br/>pcl\Syncfusion.SfListView.XForms.dll<br/>macOS\Syncfusion.Core.XForms.macOS.dll<br/>macOS\Syncfusion.SfListView.XForms.macOS<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac/) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows/).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/license-key/) to know about registering Syncfusion license key in your Xamarin application to use our components.

N> After adding the reference, an additional step is required for [iOS](https://help.syncfusion.com/xamarin/sflistview/getting-started#ios) and [UWP](https://help.syncfusion.com/xamarin/sflistview/getting-started#universal-windows-platform-uwp) projects. For UWP alone, one more additional step is required if the project is built-in release mode with .NET Native tool chain is enabled. You can refer to this [KB article](https://www.syncfusion.com/kb/8476/how-to-overcome-the-crash-system-reflection-missingmetadataexception-when-usedotnetnativetoolchain-is?_ga=2.156869305.342100434.1550463054-1358537634.1524639131) for more details. If you are adding the references from toolbox, this step is not needed.

## System Requirements

In the SfListView, current supported Xamarin.Forms version is `3.5.0.129452` and later.

The following table lists the platforms supported versions:

<table>
    <tr>
        <td>
            Platform
            <br/>
            <br/>
        </td>
        <td>
            Supported versions
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Android
            <br/>
            <br/>
        </td>       
         <td>
            API level 19 and later versions
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            iOS
            <br/>
            <br/>
        </td>
        <td>
            iOS 9.0 and later versions
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            UWP
            <br/>
            <br/>
        </td>
        <td>
            Windows 10 devices
            <br/>
            <br/>
        </td>
    </tr>   
    <tr>
        <td>
            macOS
            <br/>
            <br/>
        </td>
        <td>
            10.11
            <br/>
            <br/>
        </td>
    </tr>
</table>

## Launching the SfListView on Each Platform

To use this control inside an application, each platform application must initialize the SfListView renderer. This initialization step varies from platform to platform, and is discussed in the following sections:

### Android

The Android launches the SfListView without any initialization, and is enough to only initialize the Xamarin.Forms Framework to launch the application.

### iOS

To launch the SfListView in iOS, call the `SfListViewRenderer.Init()` in the `FinishedLaunching` overridden method of the AppDelegate class after the Xamarin.Forms Framework initialization, and before the LoadApplication is called as demonstrated in the following code example:

{% tabs %}
{% highlight c# %}
using Syncfusion.XForms.iOS.EffectsView;
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    …
    global::Xamarin.Forms.Forms.Init ();
    SfListViewRenderer.Init();
    SfEffectsViewRenderer.Init();  //Initialize only when effects view is added to Listview.
    LoadApplication (new App ());
    …
}
{% endhighlight %} 
{% endtabs %}

N> When effects view is applied to listview by adding `Visual as "Material"`, it is necessary to initialize `EffectsViewRenderer` in iOS.

### Universal Windows Platform (UWP)

To launch the SfListView in UWP, call the `SfListViewRenderer.Init()` in the `MainPage` constructor before the LoadApplication is called as demonstrated in the following code example:

{% tabs %}
{% highlight c# %}
public MainPage()
{
    …
    SfListViewRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %} 
{% endtabs %}

### macOS

To launch SfListView in macOS, call the `SfListViewRenderer.Init()` in the `DidFinishLaunching` override method of AppDelegate class, after calling the Xamarin.Forms Framework and LoadApplication initialization.

{% tabs %}
{% highlight c# %}
public override void DidFinishLaunching(NSNotification notification)
{
    Forms.Init();
    LoadApplication(new App());
    SfListViewRenderer.Init();
    …
}
{% endhighlight %} 
{% endtabs %}

### ReleaseMode Issue in UWP Platform

The known Framework issue in UWP platform is the custom controls will not render when deployed the application in `Release Mode`.

The above problem can be resolved by initializing the SfListView assemblies in `App.xaml.cs` in UWP project as in the following code snippet:

{% tabs %}
{% highlight c# %}
// In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)
{
    …

    rootFrame.NavigationFailed += OnNavigationFailed;
        
    // you'll need to add `using System.Reflection;`
    List<Assembly> assembliesToInclude = new List<Assembly>();

    //Now, add all the assemblies your app uses
    assembliesToInclude.Add(typeof(SfListViewRenderer).GetTypeInfo().Assembly);

    // replaces Xamarin.Forms.Forms.Init(e);        
    Xamarin.Forms.Forms.Init(e, assembliesToInclude);
        
    …     
}
{% endhighlight %}
{% endtabs %}

## Create a Simple SfListView 

This section explains how to create a SfListView, and configure it. The SfListView control can be configured entirely in C# code, or by using XAML markup. This is how the control will look like on iOS, Android, and Windows devices.
 
![Xamarin.Forms listview](SfListView_images/SfListView-Xamarin_img1.jpg)

In this walk through, you will create a new application with the SfListView that includes the following topics:

* [Creating the project](#creating-the-project) 
* [Adding SfListView in Xamarin.Forms](#adding-sflistview-in-xamarin.forms)     
* [Creating Data Model](#creating-data-model-for-the-sflistview)  
* [Binding data](#binding-data-to-sflistview) 
* [Defining an ItemTemplate](#defining-an-itemtemplate)
* [Layouts](#layouts)
* [Sorting](#sorting) 
* [Filtering](#filtering) 
* [Grouping](#grouping) 
* [Selection](#selection)
* [Header and Footer](#header-and-footer)

## Creating the Project

Create a new blank [(Xamarin.Forms.NET Standard) application](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/get-started/first-app/?pivots=windows) in Xamarin Studio or Visual Studio for Xamarin.Forms.

## Adding the SfListView in Xamarin.Forms 

 1. Add the required assembly references to the corresponding projects as discussed in the [Assembly deployment](#assembly-deployment) section.
 2. Import the SfListView control namespace Syncfusion.ListView.XForms.
 3. Set the SfListView control to the ContentPage.


{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
             xmlns:local="clr-namespace:GettingStarted;assembly=GettingStarted"
             x:Class="GettingStarted.MainPage">
  <syncfusion:SfListView x:Name="listView" />
</ContentPage>
{% endhighlight %}
{% highlight c# %}
using Syncfusion.ListView.XForms;
using Xamarin.Forms;

namespace GettingStarted
{
    public class App : Application
    {
        SfListView listView;
        public App()
        {
            listView = new SfListView();
            MainPage = new ContentPage { Content = listView };
        }
    }
} 
{% endhighlight %}
{% endtabs %}

## Creating Data Model for the SfListView

Create a data model to bind it to the control. 

Create a simple data source as shown in the following code example in a new class file, and save it as BookInfo.cs file: 

{% tabs %}
{% highlight c# %}
public class BookInfo : INotifyPropertyChanged
{
    private string bookName;
    private string bookDesc;

    public string BookName
    {
        get { return bookName; }
        set
        {
            bookName = value;
            OnPropertyChanged("BookName");
        }
    }

    public string BookDescription
    {
        get { return bookDesc; }
        set
        {
            bookDesc = value;
            OnPropertyChanged("BookDescription");
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;

    public void OnPropertyChanged(string name)
    {
        if (this.PropertyChanged != null)
           this.PropertyChanged(this, new PropertyChangedEventArgs(name));
    }
}
 
{% endhighlight %}
{% endtabs %}

N> If you want your data model to respond to property changes, then implement `INotifyPropertyChanged` interface in your model class.

Create a model repository class with BookInfo collection property initialized with required number of data objects in a new class file as shown in the following code example, and save it as BookInfoRepository.cs file:

{% tabs %}
{% highlight c# %}
public class BookInfoRepository
{
    private ObservableCollection<BookInfo> bookInfo;

    public ObservableCollection<BookInfo> BookInfo
    {
        get { return bookInfo; }
        set { this.bookInfo = value; }
    }

    public BookInfoRepository()
    {
        GenerateBookInfo();
    }

    internal void GenerateBookInfo()
    {
        bookInfo = new ObservableCollection<BookInfo>();
        bookInfo.Add(new BookInfo() { BookName = "Object-Oriented Programming in C#", BookDescription = "Object-oriented programming is a programming paradigm based on the concept of objects" });
        bookInfo.Add(new BookInfo() { BookName = "C# Code Contracts", BookDescription = "Code Contracts provide a way to convey code assumptions" });
        bookInfo.Add(new BookInfo() { BookName = "Machine Learning Using C#", BookDescription = "You’ll learn several different approaches to applying machine learning" });
        bookInfo.Add(new BookInfo() { BookName = "Neural Networks Using C#", BookDescription = "Neural networks are an exciting field of software development" });
        bookInfo.Add(new BookInfo() { BookName = "Visual Studio Code", BookDescription = "It is a powerful tool for editing code and serves for end-to-end programming" });
        bookInfo.Add(new BookInfo() { BookName = "Android Programming", BookDescription = "It is provides a useful overview of the Android application life cycle" });
        bookInfo.Add(new BookInfo() { BookName = "iOS Succinctly", BookDescription = "It is for developers looking to step into frightening world of iPhone" });
        bookInfo.Add(new BookInfo() { BookName = "Visual Studio 2015", BookDescription = "The new version of the widely-used integrated development environment" });
        bookInfo.Add(new BookInfo() { BookName = "Xamarin.Forms", BookDescription = "Its creates mappings from its C# classes and controls directly" });
        bookInfo.Add(new BookInfo() { BookName = "Windows Store Apps", BookDescription = "Windows Store apps present a radical shift in Windows development" });
    }
}

{% endhighlight %}
{% endtabs %}

## Binding Data to the SfListView

To bind the data source of the SfListView, set the [SfListView.ItemsSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_ItemsSource) property as shown as follows. You can bind the data source of the SfListView either from XAML or in code. 

The following code example binds the collection created in previous step to the `SfListView.ItemsSource` property:

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
             xmlns:local="clr-namespace:GettingStarted;assembly=GettingStarted"
             x:Class="GettingStarted.MainPage">
  <ContentPage.BindingContext>
    <local:BookInfoRepository />
  </ContentPage.BindingContext>
   <syncfusion:SfListView x:Name="listView" 
                   ItemsSource="{Binding BookInfo}" />
</ContentPage>
{% endhighlight %}
{% highlight c# %}
BookInfoRepository viewModel = new BookInfoRepository ();
listView.ItemsSource = viewModel.BookInfo; 
{% endhighlight %}
{% endtabs %}

## Defining an ItemTemplate
 
 By defining the [SfListView.ItemTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_ItemTemplate) of the SfListView, a custom user interface(UI) can be achieved to display the data items. 
 
{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
  <syncfusion:SfListView x:Name="listView" 
                   ItemsSource="{Binding BookInfo}"
                   ItemSize="100">
    <syncfusion:SfListView.ItemTemplate>
        <DataTemplate>
        <Grid Padding="10">
            <Grid.RowDefinitions>
            <RowDefinition Height="0.4*" />
            <RowDefinition Height="0.6*" />
            </Grid.RowDefinitions>
            <Label Text="{Binding BookName}" FontAttributes="Bold" TextColor="Teal" FontSize="21" />
            <Label Grid.Row="1" Text="{Binding BookDescription}" TextColor="Teal" FontSize="15"/>
        </Grid>
        </DataTemplate>
    </syncfusion:SfListView.ItemTemplate>
  </syncfusion:SfListView>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
using Syncfusion.ListView.XForms;
using Xamarin.Forms;

namespace GettingStarted
{
    public class App : Application
    {
        SfListView listView;
        public App()
        {
            BookInfoRepository viewModel = new BookInfoRepository ();
            listView = new SfListView();
            listView.ItemSize = 100;
            listView.ItemsSource = viewModel.BookInfo;
            listView.ItemTemplate = new DataTemplate(() => {
                var grid = new Grid();
                var bookName = new Label { FontAttributes = FontAttributes.Bold, BackgroundColor = Color.Teal, FontSize = 21 };
                bookName.SetBinding(Label.TextProperty, new Binding("BookName"));
                var bookDescription = new Label { BackgroundColor = Color.Teal, FontSize = 15 };
                bookDescription.SetBinding(Label.TextProperty, new Binding("BookDescription"));

                grid.Children.Add(bookName);
                grid.Children.Add(bookDescription, 1, 0);

                return grid;
            });
            MainPage = new ContentPage { Content = listView };
        }
    }
} 
{% endhighlight %}
{% endtabs %}

Now, run the application to render the below output:

You can also download the entire source code of this demo [here](https://github.com/SyncfusionExamples/ListView-GettingStarted-in-Xamarin-Forms).

![Xamarin.Forms listview getting started](SfListView_images/SfListView-Xamarin_img2.png)

## Layouts

SfListView supports different layouts such as linear layout and grid layout. The linear layout arranges the items in a single column, whereas the grid layout arranges the items in a predefined number of columns defined by the [SpanCount](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.GridLayout.html#Syncfusion_ListView_XForms_GridLayout_SpanCount) property of [GridLayout](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.GridLayout.html). 

The [SfListView.LayoutManager](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LayoutManager) property is used to define the layout of the SfListView. [LinearLayout](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.LinearLayout.html) is default layout of this control.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
 <syncfusion:SfListView x:Name="listView" 
                   ItemsSource="{Binding BookInfo}"
                   ItemSize="100">
    <syncfusion:SfListView.LayoutManager>
      <syncfusion:GridLayout SpanCount="3" />
    </syncfusion:SfListView.LayoutManager>
  </syncfusion:SfListView>
</ContentPage>
{% endhighlight%}
{% highlight c# %}
listView.LayoutManager = new GridLayout() { SpanCount = 3 };
{% endhighlight%}
{% endtabs %}

## DataSource

The [DataSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html) gets the raw data and processes data operations such as sorting, filtering, and grouping in SfListView. The data source of the ListView is set using the `ItemsSource` attribute.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
             xmlns:data="clr-namespace:Syncfusion.DataSource;assembly=Syncfusion.DataSource.Portable"             
             xmlns:local="clr-namespace:GettingStarted;assembly=GettingStarted"
             x:Class="GettingStarted.MainPage">             
             
  <syncfusion:SfListView x:Name="listView"  ItemsSource="{Binding BookInfo}" >
  </syncfusion:SfListView>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
 SfListView listView = new SfListView();
    DataSource dataSource = new DataSource();
    dataSource.Source = ViewModel.BookInfo;
	listView.DataSource = dataSource;
    listView.DataSource.Refresh();
{% endhighlight %}
{% endtabs %}

## Sorting

The SfListView allows sorting on its data by using the [SfListView.DataSource.SortDescriptors](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html#Syncfusion_DataSource_DataSource_SortDescriptors) property. Create [SortDescriptor](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.SortDescriptor.html) for the property to be sorted, and add it into the `DataSource.SortDescriptors` collection.

Refresh the view by calling [SfListView.RefreshView](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_RefreshView) method. 

SortDescriptor object holds the following three properties:

 * [PropertyName](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.SortDescriptor.html#Syncfusion_DataSource_SortDescriptor_PropertyName): Describes name of the sorted property.
 * [Direction](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.SortDescriptor.html#Syncfusion_DataSource_SortDescriptor_Direction): Describes an object of type [ListSortDirection](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.ListSortDirection.html) defines the sorting direction.
 * [Comparer](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.SortDescriptor.html#Syncfusion_DataSource_SortDescriptor_Comparer): Describes a comparer to be applied when sorting takes place.
 
{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
             xmlns:data="clr-namespace:Syncfusion.DataSource;assembly=Syncfusion.DataSource.Portable"             
             xmlns:local="clr-namespace:GettingStarted;assembly=GettingStarted"
             x:Class="GettingStarted.MainPage">             
             
  <syncfusion:SfListView x:Name="listView">
    <syncfusion:SfListView.DataSource>
      <data:DataSource>
        <data:DataSource.SortDescriptors>
          <data:SortDescriptor PropertyName="BookName" Direction="Ascending"/>
        </data:DataSource.SortDescriptors>
      </data:DataSource>
    </syncfusion:SfListView.DataSource>
  </syncfusion:SfListView>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
 listView.DataSource.SortDescriptors.Add(new SortDescriptor()
 {
   PropertyName = "BookName",
   Direction = ListSortDirection.Ascending,
 }); 
 listView.RefreshView();
{% endhighlight %}
{% endtabs %}

## Filtering

The SfListView supports to filter the records in view by setting predicate to the [SfListView.DataSource.Filter](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html#Syncfusion_DataSource_DataSource_Filter) property. Call the [DataSource.RefreshFilter](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html#Syncfusion_DataSource_DataSource_RefreshFilter) method after assigning the Filter property for refreshing the view.

To filter the items based on the Title property of the underlying data by using `FilterContacts` method, follow the code example:
 
{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
    <Grid>
	 <Grid.RowDefinitions>
           <RowDefinition Height="Auto"/>
           <RowDefinition Height="Auto"/>
     </Grid.RowDefinitions>
      <SearchBar x:Name="filterText" HeightRequest="40"
           Placeholder="Search here to filter"
           TextChanged="OnFilterTextChanged" Grid.Row="0"/>
      <syncfusion:SfListView x:Name="listView" Grid.Row="1" ItemsSource="{Binding BookInfo}"/>
    </Grid>
  </ContentPage>
{% endhighlight %}
{% highlight c# %}
var grid = new Grid();
var viewModel = new BookInfoRepository ();

var searchBar = new SearchBar() { Placeholder = "Search here to filter" };
searchBar.TextChanged += OnFilterTextChanged;

listView = new SfListView();
listView.ItemsSource = viewModel.BookInfo;

grid.Children.Add(searchBar);
grid.Children.Add(listView, 0, 1);
...
private void OnFilterTextChanged(object sender, TextChangedEventArgs e)
{
  searchBar = (sender as SearchBar);
  if (listView.DataSource != null)
  {
     this.listView.DataSource.Filter = FilterContacts;
     this.listView.DataSource.RefreshFilter();
  }
}

private bool FilterContacts(object obj)
{
  if (searchBar == null || searchBar.Text == null)
    return true;

  var bookInfo = obj as BookInfo;
  if (bookInfo.BookName.ToLower().Contains(searchBar.Text.ToLower())
      || bookInfo.BookDescription.ToLower().Contains(searchBar.Text.ToLower()))
      return true;
  else
      return false;
}
{% endhighlight %}
{% endtabs %}

## Grouping

The SfListView allows displaying the items in a group using the [SfListView.DataSource.GroupDescriptors](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.DataSource.html#Syncfusion_DataSource_DataSource_GroupDescriptors) property. Create [GroupDescriptor](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.GroupDescriptor.html) for the property to be grouped, and add it in the `DataSource.GroupDescriptors` collection. 

`GroupDescriptor` object holds the following properties:

 * [PropertyName](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.GroupDescriptor.html#Syncfusion_DataSource_GroupDescriptor_PropertyName): Describes name of the property to be grouped.
 * [KeySelector](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.GroupDescriptor.html#Syncfusion_DataSource_GroupDescriptor_KeySelector): Describes selector to return the group key.
 * [Comparer](https://help.syncfusion.com/cr/xamarin/Syncfusion.DataSource.GroupDescriptor.html#Syncfusion_DataSource_GroupDescriptor_Comparer): Describes comparer to be applied when sorting takes place.

It also supports to stick the group header by enabling the [SfListView.IsStickyGroupHeader](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_IsStickyGroupHeader) property.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
             xmlns:data="clr-namespace:Syncfusion.DataSource;assembly=Syncfusion.DataSource.Portable"">
  <syncfusion:SfListView x:Name="listView">
    <syncfusion:SfListView.DataSource>
      <data:DataSource>
        <data:DataSource.GroupDescriptors>
          <data:GroupDescriptor PropertyName="BookName"/>
        </data:DataSource.GroupDescriptors>
      </data:DataSource>
    </syncfusion:SfListView.DataSource>
  </syncfusion:SfListView>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
 listView.DataSource.GroupDescriptors.Add(new GroupDescriptor()
 {
   PropertyName = "BookName",
 });
{% endhighlight %}
{% endtabs %}

## Selection

The SfListView allows selecting the item by setting the [SfListView.SelectionMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_SelectionMode) property. Set the `SfListView.SelectionMode` property to single, multiple, and none based on the requirements. Informations about the selected item can be tracked using the [SfListView.SelectedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_SelectedItem) and [SfListView.SelectedItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_SelectedItems) properties. It also allows changing the selection highlight color by using the [SfListView.SelectionBackgroundColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_SelectionBackgroundColor).

The gesture type can be changed to select the item by setting the [SfListView.SelectionGesture](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_SelectionGesture) property. Set the `SfListView.SelectionGesture` property to Tap, DoubleTap, and Hold based on the requirements.

The selection operations can be handled with the help of [SelectionChanging](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) and [SelectionChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) events of the SfListView.
 
{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
  <syncfusion:SfListView x:Name="listView" 
                 SelectionMode="Single"
                 SelectionGesture="Tap"
                 SelectionBackgroundColor="#E4E4E4"/>}
</ContentPage>
{% endhighlight %}
{% highlight c# %}
listView.SelectionMode = SelectionMode.Single;
listView.SelectionGesture = TouchGesture.Tap;
listView.SelectionBackgroundColor = Color.FromHex("#E4E4E4");
{% endhighlight %}
{% endtabs %}

## Header and Footer

The SfListView allows setting the header and footer to the user interface(UI) view by setting the DataTemplate to the [HeaderTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_HeaderTemplate) and [FooterTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_FooterTemplate).

The header and footer can be handled either by scrollable, or sticky to the view by enabling or disabling the [IsStickyHeader](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_IsStickyHeader) and [IsStickyFooter](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_IsStickyFooter) properties.
 
{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms">
<syncfusion:SfListView x:Name="listView"
                 ItemsSource="{Binding InboxInfo}"
                 IsStickyHeader="true"
                 IsStickyFooter="true">
  <syncfusion:SfListView.HeaderTemplate>
    <DataTemplate>
      <Grid BackgroundColor="#4CA1FE" HeightRequest="45">
        <Label Text="Inbox" FontAttributes="Bold" FontSize="18" TextColor="White" />
      </Grid>
    </DataTemplate>
  </syncfusion:SfListView.HeaderTemplate>
  <syncfusion:SfListView.FooterTemplate>
    <DataTemplate>
      <Grid BackgroundColor="#DC595F">
        <Grid.ColumnDefinitions>
          <ColumnDefinition />
          <ColumnDefinition />
        </Grid.ColumnDefinitions>
        <Image Grid.Column="0" Source="Edit.png" />
        <Image Grid.Column="1" Source="Delete.png" />
      </Grid>
    </DataTemplate>
  </syncfusion:SfListView.FooterTemplate>
  </syncfusion:SfListView>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
ViewModel viewModel = new ViewModel ();
listView.ItemsSource = viewModel.InboxInfo; 
listView.IsStickyHeader = true;
listView.IsStickyFooter = true;
listView.HeaderTemplate = new DataTemplate(() =>
{
  var grid = new Grid();
  grid.BackgroundColor = Color.FromHex("#4CA1FE");
  var headerLabel = new Label { BackgroundColor = Color.White, FontSize = 18,
                                FontAttributes = FontAttributes.Bold };
  headerLabel.Text = "Inbox";
  grid.Children.Add(headerLabel);
  return grid;
});
listView.FooterTemplate = new DataTemplate(() =>
{
  var grid = new Grid();
  grid.BackgroundColor = Color.FromHex("#DC595F");
  var editImage = new Image();
  editImage.Source = "Edit.png";
  var deleteImage = new Image();
  deleteImage.Source = "Delete.png";
  grid.Children.Add(editImage);
  grid.Children.Add(deleteImage, 0, 1);
  return grid;
});
{% endhighlight %}
{% endtabs %}

## See also

### Data binding

[How to bind data from the DataTable to ListView in Xamarin.Forms](https://www.syncfusion.com/kb/9697/)  
[How to bind OData to Xamarin.Forms ListView (SfListView)](https://www.syncfusion.com/kb/11211/)                                                                                           
[How to bind JSON data to Xamarin.Forms ListView (SfListView)](https://www.syncfusion.com/kb/11173/)                                                                                                                                  
[How to load the data from SQLite offline database in SfListView?](https://www.syncfusion.com/kb/7550/)                                                                                                                                                                         
[How to load the data from SQLite online database in SfListView?](https://www.syncfusion.com/kb/7821/)     
[How to bind data using FreshMVVM in Xamarin.Forms ListView (SfListView)](https://www.syncfusion.com/kb/11277)                                                                                                                                                              
[How to render ListView using RealmObject in Xamarin.Forms (SfListView)](https://www.syncfusion.com/kb/11445/)

### Resolve exception issues

[How to solve "System.MethodMissingException" in Xamarin.Forms.iOS when using SfListView](https://www.syncfusion.com/kb/7613/)                                                                                                                                                                 
["No Count Method exist exception" when using SfListView in Xamarin.Forms.iOS](https://www.syncfusion.com/kb/7614/)                                                                                                                                             
[How to overcome the crash System.Reflection.MissingMetadataException when UseDotNetNativeToolChain is enabled in UWP](https://www.syncfusion.com/kb/8476/)
[How to render SfListView for Xamarin.Forms.UWP in release mode](https://www.syncfusion.com/kb/7615/)                                                                                                                                                                                                                          

### Miscellaneous

[How to create a application using Xamarin.Forms listview in Rider IDE](https://www.syncfusion.com/kb/9833/)   
[How to show empty message when listview has no items in Xamarin.Forms](https://www.syncfusion.com/kb/9956/)                                                                         
[How to bind image and text in the listview](https://www.syncfusion.com/kb/9636/)                                                                                                                      
[How to load listview with background image](https://www.syncfusion.com/kb/9479/)                                                                                                                                                                                                                          
[How to resolve ItemTapped event not firing in Forms.Android when when MainActivity type is FormsApplicationActivity](https://www.syncfusion.com/kb/8996/)                                                                                                                                                            
[How to use Xamarin.Forms ListView in Xamarin.Android and Xamarin.iOS platforms](https://www.syncfusion.com/kb/9392/)                                                                                                                                                   
[How to resolve SfListView not rendering issue in iOS, macOS and UWP in Xamarin.Forms](https://www.syncfusion.com/kb/11292)                                                                                                                                                                                                 
[How use Xamarin.Forms ListView in SfNavigationDrawer (SfListView)](https://www.syncfusion.com/kb/11396/)                                                                                                                                                                                       
[How to use custom renderer for ListView in Xamarin.Forms (SfListView)](https://www.syncfusion.com/kb/11398)