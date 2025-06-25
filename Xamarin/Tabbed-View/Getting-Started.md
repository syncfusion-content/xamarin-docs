---
layout: post
title: Getting Started with Xamarin Tabbed View Control | Syncfusion
description: Learn how to get started with the Syncfusion Xamarin Tabbed View (SfTabView) control, its elements, and more.
platform: Xamarin
control: TabView
documentation: ug
---

# Getting Started with Xamarin Tabbed View (SfTabView)

This section provides an overview of working with the [Xamarin.Forms Tabbed View](https://www.syncfusion.com/xamarin-ui-controls/xamarin-tabbed-view) control. Follow the process to create a real-world application using the tab view.

## Assembly Deployment

After installing [Essential Studio for Xamarin](https://www.syncfusion.com/downloads/xamarin), you can find all the required assemblies in the installation directories: {Syncfusion Essential Studio Installed location}\Essential Studio\\{Version #}\Xamarin\lib.

E.g.: C:\Program Files (x86) \Syncfusion\Essential Studio\19.1.0.54\Xamarin\lib

> **Note:** Assemblies can be found in the unzipped package location (Documents/Syncfusion/{Version #}/Xamarin/lib) on a Mac.

## Adding SfTabView Reference

You can add the [`SfTabView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html) reference using one of the following methods:

**Method 1: Adding SfTabView Reference from NuGet.org**

Syncfusion Xamarin components are available on [NuGet.org](https://www.nuget.org/). To add SfTabView to your project, open the [NuGet package manager](https://help.syncfusion.com/xamarin/visual-studio-integration/nuget-packages) in Visual Studio, search for [Syncfusion.Xamarin.SfTabView](https://www.nuget.org/packages/Syncfusion.Xamarin.SfTabView), and install it.

![Adding SfTabView reference from NuGet](images/Getting-Started/Adding SfTabView reference.png)

> **Note:** Install the same version of SfTabView NuGet in all projects.

**Method 2: Adding SfTabView Reference from Toolbox**

Syncfusion provides a Xamarin Toolbox. Using this toolbox, you can drag the [`SfTabView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html) control to the XAML page, and it will automatically install the required NuGet packages and add the namespace to the page. For installation details, refer to the [Toolbox documentation](https://help.syncfusion.com/xamarin/utility#toolbox).

**Method 3: Adding SfTabView Assemblies Manually from the Installed Location**

If you prefer manual referencing of assemblies instead of using NuGet, add the following assemblies to the respective projects:

Location: {Installed location}/{version}/Xamarin/lib

<table>
<tr>
<td>PCL</td>
<td>Syncfusion.SfTabView.XForms.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>Android</td>
<td>Syncfusion.SfTabView.XForms.dll<br/>Syncfusion.SfTabView.XForms.Android.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.Android.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>iOS</td>
<td>Syncfusion.SfTabView.XForms.dll<br/>Syncfusion.SfTabView.XForms.iOS.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.iOS.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
<tr>
<td>UWP</td>
<td>Syncfusion.SfTabView.XForms.dll<br/>Syncfusion.SfTabView.XForms.UWP.dll<br/>Syncfusion.Core.XForms.dll<br/>Syncfusion.Core.XForms.UWP.dll<br/>Syncfusion.Licensing.dll<br/></td>
</tr>
</table>

N> To know more about obtaining our components, refer to these links for [Mac](https://help.syncfusion.com/xamarin/installation/mac-installer/how-to-download) and [Windows](https://help.syncfusion.com/xamarin/installation/web-installer/how-to-download).

I> Starting with v16.2.0.x, if you reference Syncfusion assemblies from the trial setup or from the NuGet feed, you also have to include a license key in your projects. Please refer to [Syncfusion license key](https://help.syncfusion.com/common/essential-studio/licensing/overview) to know about registering Syncfusion license key in your Xamarin application to use our components.

## Launching the SfTabView on each platform

To use the tab view inside an application, each platform application must initialize the tab view renderer. This initialization steps vary from platform to platform, and it is discussed in the following sections:

### Android and UWP

Android launches the tab view without any initialization. It is sufficient to initialize the Xamarin.Forms Framework to launch the application.

> **Note:** If you add references from the toolbox, this step is unnecessary.

### iOS

To launch the tab view in iOS, call `SfTabViewRenderer.Init()` in the `FinishedLaunching` method of the `AppDelegate` class, after initializing the Xamarin.Forms Framework and before calling `LoadApplication`, as demonstrated below:

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
 {
      …            
      global::Xamarin.Forms.Forms.Init ();   
      Syncfusion.XForms.iOS.TabView.SfTabViewRenderer.Init();  
      LoadApplication (new App ());   
      …   
 }
	

{% endhighlight %}

### Release Mode Issue on UWP Platform

There is a known framework issue on the UWP platform where custom controls do not render when the application is deployed in `Release Mode`.

This problem can be resolved by initializing the [`SfTabView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html) assemblies in `App.xaml.cs` in the UWP project as shown below:

{% highlight C# %}

// In App.xaml.cs

protected override void OnLaunched(LaunchActivatedEventArgs e)
{
…

	rootFrame.NavigationFailed += OnNavigationFailed;
		
	// you'll need to add `using System.Reflection;`
	List<Assembly> assembliesToInclude = new List<Assembly>();

	//Now, add all the assemblies your app uses
	assembliesToInclude.Add(typeof(Syncfusion.XForms.UWP.TabView.SfTabViewRenderer).GetTypeInfo().Assembly);

	// replaces Xamarin.Forms.Forms.Init(e);        
	Xamarin.Forms.Forms.Init(e, assembliesToInclude);
		
…     
}
{% endhighlight %}

## Creating a Simple SfTabView

This section explains how to create and configure a tab view. The control can be configured entirely in C# code or using XAML markup. The screenshot below illustrates the output of a tab view on iOS, Android, and UWP devices.

![TabViewImage](images/Getting-Started/xamarin_forms_tabview.png)

### Creating the Project

Create a new BlankApp (Xamarin.Forms.Portable) application in Xamarin Studio or Visual Studio for Xamarin.Forms.

### Adding SfTabView in Xamarin.Forms

Add the required assembly references to the PCL and renderer projects, as discussed in the Assembly Deployment section.

Import the control namespace as follows:

{% tabs %}

{% highlight xaml %}

xmlns:tabView="clr-namespace:Syncfusion.XForms.TabView;assembly=Syncfusion.SfTabView.XForms"
	
{% endhighlight %}

{% highlight C# %}

using Syncfusion.XForms.TabView;

{% endhighlight %}

{% endtabs %}

Set the control to the content in `ContentPage`.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:tabView="clr-namespace:Syncfusion.XForms.TabView;assembly=Syncfusion.SfTabView.XForms"
             x:Class="TabViewAutomationSample.TabViewAutomationSample">
    <ContentPage.Content> 
        <tabView:SfTabView/> 
    </ContentPage.Content>  
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.XForms.TabView;
using Xamarin.Forms;

namespace GettingStarted  
{  
    public partial class MainPage : ContentPage                  
    {   
        private SfTabView tabView;   
        public MainPage()   
        {   
            InitializeComponent();       
            tabView = new SfTabView();   
            this.Content = tabView;  
        }  
    }  
}  

{% endhighlight %}

{% endtabs %}

## Populating Tab Items

Tab items can be configured within the tab view using the [`Items`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html#Syncfusion_XForms_TabView_SfTabView_Items) property of the [`SfTabView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html). This property holds a collection of [`SfTabItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabItem.html) objects via the [`TabItemCollection`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.TabItemCollection.html).

{% tabs %}

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:tabView="clr-namespace:Syncfusion.XForms.TabView;assembly=Syncfusion.SfTabView.XForms"
             x:Class="TabViewAutomationSample.TabViewAutomationSample">
    <ContentPage.Content>
        <tabView:SfTabView BackgroundColor="Aqua">
                    <tabView:SfTabItem Title="Call">
                        <tabView:SfTabItem.Content>
                            <Grid BackgroundColor="Red" x:Name="AllContactsGrid" />
                        </tabView:SfTabItem.Content>
                    </tabView:SfTabItem>
                    <tabView:SfTabItem Title="Favorites">
                        <tabView:SfTabItem.Content>
                            <Grid BackgroundColor="Green" x:Name="FavoritesGrid" />
                        </tabView:SfTabItem.Content>
                    </tabView:SfTabItem>
                    <tabView:SfTabItem Title="Contacts">
                        <tabView:SfTabItem.Content>
                            <Grid BackgroundColor="Blue" x:Name="ContactsGrid" />
                        </tabView:SfTabItem.Content>
                    </tabView:SfTabItem>
        </tabView:SfTabView>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight C# %}

using Syncfusion.XForms.TabView;
using Xamarin.Forms;
using Xamarin.Forms.Xaml;

namespace TabViewAutomationSample
{
    [XamlCompilation(XamlCompilationOptions.Compile)]
	public partial class TabView : ContentPage
	{
        SfTabView tabView;
		public TabView ()
		{
			InitializeComponent ();
            var tabView = new SfTabView();
            Grid allContactsGrid = new Grid {BackgroundColor = Color.Red};
            Grid favoritesGrid = new Grid {BackgroundColor = Color.Green};
            Grid contactsGrid = new Grid {BackgroundColor = Color.Blue};
            var tabItems = new TabItemCollection
            {
                new SfTabItem()
                {
                    Title = "Calls",
                    Content = allContactsGrid
                },
                new SfTabItem()
                {
                    Title = "Favorites",
                    Content = favoritesGrid
                },
                new SfTabItem()
                {
                    Title = "Contacts",
                    Content = contactsGrid
                }
            };
            tabView.Items = tabItems;
            this.Content = tabView;
		}
	}
}

{% endhighlight %}

{% endtabs %}

## Adding ListView in SfTabView

### Use Case: Sample with Contacts Information Stored as a ListView in SfTabView Control

Create a view model class with a `ContactsInfo` collection property, initialized with the required number of data objects.

{% highlight c# %}

public class ContactInfo
{
	public string Name { get; set; }
	public long Number { get; set; }
}

public class ContactsViewModel : INotifyPropertyChanged
{
	private ObservableCollection<ContactInfo> contactList;
	public event PropertyChangedEventHandler PropertyChanged;

	public ObservableCollection<ContactInfo> ContactList
	{
		get { return contactList; }
		set { contactList = value; }
	}
	public ContactsViewModel()
	{
	ContactList = new ObservableCollection<ContactInfo>();
	ContactList.Add(new ContactInfo{Name = "Aaron",Number = 7363750});
	ContactList.Add(new ContactInfo { Name = "Adam", Number = 7323250 });
	ContactList.Add(new ContactInfo { Name = "Adrian", Number = 7239121 });
	ContactList.Add(new ContactInfo { Name = "Alwin", Number = 2329823 });
	ContactList.Add(new ContactInfo { Name = "Alex", Number = 8013481 });
	ContactList.Add(new ContactInfo { Name = "Alexander", Number = 7872329 });
	ContactList.Add(new ContactInfo { Name = "Barry", Number = 7317750 });
	}
}

{% endhighlight %}

## Binding Data to ListView

Bind the items source of the `ListView`, and set the required appearance in its `ItemTemplate` property. The list view can be hosted within the content region of a tab item.

{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:TabViewAutomationSample"
             xmlns:tabView="clr-namespace:Syncfusion.XForms.TabView;assembly=Syncfusion.SfTabView.XForms"
             x:Class="TabViewAutomationSample.XAMARIN_22272">
   <ContentPage.Content>
        <tabView:SfTabView BackgroundColor="#f6f6f6" x:Name="tabView">
            <tabView:SfTabItem Title="{Binding Title1}">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="White" x:Name="AllContactsGrid" >
                        <ListView x:Name="ContactListView" 
                                  ItemsSource="{Binding ContactList}"
                                  RowHeight="75">
                            <ListView.BindingContext>
                                <local:ContactsViewModel />
                            </ListView.BindingContext>
                            <ListView.ItemTemplate>
                                <DataTemplate>
                                    <ViewCell>
                                        <StackLayout Orientation="Vertical" Margin="30,0,0,0">
                                            <Label 
                                                Text="{Binding Name}"
                                                FontSize="24"  />
                                            <Label 
                                                Text="{Binding Number}" 
                                                FontSize="20" 
                                                TextColor="LightSlateGray" />
                                        </StackLayout>
                                    </ViewCell>
                                </DataTemplate>
                            </ListView.ItemTemplate>
                        </ListView>
                    </Grid>
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Favorites">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Green" x:Name="FavouritesGrid" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Contacts">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="Blue" x:Name="ContactsGrid" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
        </tabView:SfTabView>
    </ContentPage.Content>
</ContentPage>
	
{% endhighlight %}

Similarly, the content region for other tabs can be configured.

![ListViewImage](images/Getting-Started/ListView.png)

## Swiping

By default, both vertical swiping for list view and horizontal swiping for tab view are enabled. If not required, this can be customized using the [`EnableSwiping`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html#Syncfusion_XForms_TabView_SfTabView_EnableSwiping) property of [`SfTabView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html).

> **Note:** The getting started sample can be downloaded from this [link](https://github.com/SyncfusionExamples/xamarin-forms-sftabview).
