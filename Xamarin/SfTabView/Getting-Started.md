---
layout: post
title: Getting Started with Syncfusion TabView control for Xamarin.Forms 
description: A quick tour to initial users on Syncfusion TabView control for Xamarin.Forms platform
platform: Xamarin
control: TabView
documentation: ug
---

# Getting Started

This section provides an overview for working with the tab view control for Xamarin.Forms. Walk through the entire process of creating a real-world application with the tab view.

# Assembly deployment

After installing the Essential Studio for Xamarin, find all the required assemblies in installation folders, {Syncfusion Essential Studio Installed location}\Essential Studio\16.1.0.24\Xamarin\lib}.

E.g., C:\Program Files (x86)\Syncfusion\Essential Studio\16.1.0.24\Xamarin\lib

N> In Mac, assemblies can be found in unzipped package location.


### Adding SfTabView reference


Syncfusion Xamarin components are available in [nuget.org](https://www.nuget.org/). To add SfTabView to your project, open the NuGet package manager in Visual Studio, and search for [Syncfusion.Xamarin.SfTabView](https://www.nuget.org/packages/Syncfusion.Xamarin.SfTabView/), and then install it.

To know more about obtaining our components, refer to these links: [Mac](https://help.syncfusion.com/xamarin/introduction/download-and-installation/mac) and [Windows](https://help.syncfusion.com/xamarin/introduction/download-and-installation/windows). Also, if you prefer to manually refer the assemblies instead of NuGet, refer to this [link](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sftabview) to know about the dependent assemblies for SfTabView.

N> When there is a mismatch of Xamarin NuGet packages between your sample and the tabview control assemblies, an error (Could not load type Xamarin.Forms.ElementTemplate) will occur. Refer to the [System Requirements](https://help.syncfusion.com/xamarin/introduction/system-requirements) section to know the software requirements of Syncfusion controls.

# Launching the tab view on each platform

To use the tab view inside an application, each platform application must initialize the tab view renderer. This initialization steps vary from platform to platform, and it is discussed in the following sections:

# Android and UWP

Android launches the tab view without any initialization, and it is enough to only initialize the Xamarin.Forms Framework to launch the application.

# iOS

To launch the tab view in iOS, call the SfTabViewRenderer.Init() in the `FinishedLaunching` overridden method of the `AppDelegate` class after the Xamarin.Forms Framework has been initialized and before the `LoadApplication` is called, as demonstrated in the following code example.

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

### ReleaseMode issue in UWP platform

There is a known Framework issue in UWP platform. The custom controls will not render when deployed the application in `Release Mode`.

The above problem can be resolved by initializing the SfTabView assemblies in `App.xaml.cs` in UWP project as like in below code snippet.

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

### Create a simple tab view

This section explains how to create a tab view and configure it. The control can be configured entirely in C# code or by using XAML markup. The following screenshot illustrates the output of tab view on iOS, Android and UWP devices.

![TabViewImage](images/Getting-Started/xamarin_forms_tabview.png)

# Creating the project

Create a new BlankApp (Xamarin.Forms.Portable) application in Xamarin Studio or Visual Studio for Xamarin.Forms.

# Adding SfTabView in Xamarin.Forms

Add the required assembly references to the PCL and renderer projects as discussed in the Assembly deployment section.

Import the control namespace as shown in the following code.

{% tabs %}

{% highlight xaml %}

xmlns:tabView="clr-namespace:Syncfusion.XForms.TabView;assembly=Syncfusion.SfTabView.XForms"
	
{% endhighlight %}

{% highlight C# %}

using Syncfusion.XForms.TabView;

{% endhighlight %}

{% endtabs %}

Set the control to content in `ContentPage`.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
		xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
		xmlns:tabView="clr-namespace:Syncfusion.XForms.TabView;assembly=Syncfusion.SfTabView.XForms"
		x:Class="GettingStarted.MainPage">
<ContentPage.Content>   
<tabView:SfTabView  />   
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

# Adding tab items

Tab items can be configured in tab view through the `Items` property of `SfTabView`, which holds the collection of `SfTabItem` through `TabItemsCollection`.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView >
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

{% endhighlight %}

{% highlight C# %}

var tabView = new SfTabView();
var allContactsGrid = new Grid {BackgroundColor = Color.Red};
var favoritesGrid = new Grid {BackgroundColor = Color.Green};
var contactsGrid = new Grid {BackgroundColor = Color.Blue};
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

{% endhighlight %}

{% endtabs %}

## Share the header space equally

To share the header space to tabs equally, set the number of tabs that can be distributed in the available space though the `VisibleHeaderCount` property of tab view.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView VisibleHeaderCount="3" >
	
{% endhighlight %}

{% highlight C# %}

tabView.VisibleHeaderCount = 3;

{% endhighlight %}

{% endtabs %}

After set the number of tabs, you can add the required controls for your application. Here, a `ListView` has been added in the content region.

## Set background color for tab view

To set color for the whole tab view control, set `BackgroundColor` property of tab view control. This will change the background color for whole tab view content and tab view header with same color.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView BackgroundColor="Red" >
	
{% endhighlight %}

{% highlight C# %}

tabView.BackgroundColor = Color.Red;

{% endhighlight %}

{% endtabs %}


## Adding ListView in tab view

## Preparing data

Create a view model class with the `ContactsInfo` collection property, which is initialized with required number of data objects.

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

## Binding data to list view

Bind the items source of the `ListView`, and set the required appearance in its `ItemsTemplate` property in which the list view can be hosted within the content region of tab item. 

{% highlight xaml %}


<ContentPage.Content>
<syncfusion:SfTabView x:Name="tabView"  EnableSwiping="False" VisibleHeaderCount="3" Margin="0,40,0,0">
<syncfusion:SfTabView.SelectionIndicatorSettings>
<syncfusion:SelectionIndicatorSettings Color="Red" Position="Bottom" StrokeThickness="0"/>
</syncfusion:SfTabView.SelectionIndicatorSettings>
<syncfusion:SfTabItem >
<syncfusion:SfTabItem.HeaderContent>
<StackLayout VerticalOptions="Center">
<Label HorizontalTextAlignment="Center" Text="ACCOUNTS"></Label>
<BoxView BackgroundColor="Black" HorizontalOptions="Center" HeightRequest="3" WidthRequest="35">
</BoxView>
</StackLayout>
</syncfusion:SfTabItem.HeaderContent>
<syncfusion:SfTabItem.Content>
<Grid BackgroundColor="Yellow" x:Name="FavoritesGrid" />
</syncfusion:SfTabItem.Content>
</syncfusion:SfTabItem>
<syncfusion:SfTabItem >
<syncfusion:SfTabItem.HeaderContent>
<StackLayout VerticalOptions="Center">
<Label HorizontalTextAlignment="Center" Text="CARDS"></Label>
<BoxView Style="{DynamicResource Key=cards}" BackgroundColor="Black" HorizontalOptions="Center" HeightRequest="3" WidthRequest="35"></BoxView>
</StackLayout>
</syncfusion:SfTabItem.HeaderContent>
<syncfusion:SfTabItem.Content>
<Grid BackgroundColor="Blue" x:Name="ContactsGrid" />
</syncfusion:SfTabItem.Content>
</syncfusion:SfTabItem>
<syncfusion:SfTabItem>
<syncfusion:SfTabItem.HeaderContent>
<StackLayout VerticalOptions="Center">
<Label HorizontalTextAlignment="Center" Text="WALLETS"></Label>
<BoxView Style="{DynamicResource Key=wallets}" BackgroundColor="Black" HorizontalOptions="Center" HeightRequest="3" WidthRequest="35"></BoxView>
</StackLayout>
</syncfusion:SfTabItem.HeaderContent>
<syncfusion:SfTabItem.Content>
<ListView x:Name="ContactListView" 
ItemsSource="{Binding ContactList}"
BackgroundColor="Beige" RowHeight="100">
<ListView.BindingContext>
<local:ContactsViewModel />
</ListView.BindingContext>
<ListView.ItemTemplate>
<DataTemplate>
<ViewCell>
<StackLayout Orientation="Vertical">
<Label 
Text="{Binding Name}"
FontSize="24" 
TextColor="Blue" />
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
</syncfusion:SfTabItem.Content>
</syncfusion:SfTabItem>
</syncfusion:SfTabView>
</ContentPage.Content>
	
{% endhighlight %}

Similarly, content region for other tabs also can be configured.

## Swiping

By default, both the vertical swiping for list view and horizontal swiping for tab view will work. If it is not required, it can be customized by using the `EnableSwiping` property of `SfTabView`.

Note: Getting started sample can be downloaded from [this link](http://www.syncfusion.com/downloads/support/directtrac/general/ze/GettingStarted1726376415.zip).
