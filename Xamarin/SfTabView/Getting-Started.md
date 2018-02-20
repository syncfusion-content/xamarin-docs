---
layout: post
title: Getting Started with Syncfusion TabView control for Xamarin.Forms 
description: A quick tour to initial users on Syncfusion TabView control for Xamarin.Forms platform
platform: Xamarin
control: TabView
documentation: ug
---

# Getting Started

This section provides a quick overview for working with the tab view control for Xamarin.Forms. Walk through the entire process of creating a real-world application with tab view.

# Assembly deployment

After installing Essential Studio for Xamarin, find all the required assemblies in the installation folders,   
{Syncfusion Essential Studio Installed location}\Essential Studio\16.1.0.24\Xamarin\lib
Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\16.1.0.24\Xamarin\lib

N> Assemblies can be found in unzipped package location in Mac.


## Tab View for Xamarin.Forms

The following list of assemblies should be added as reference from the lib folder to use the tab view.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>PCL</td>
<td>pcl\Syncfusion.SfTabView.XForms.dll</td>
</tr>
<tr>
<td>Android renderer</td>
<td>android\Syncfusion.SfTabView.XForms.dll<br/>android\Syncfusion.SfTabView.XForms.Android.dll</td>
</tr>
<tr>
<td>iOS renderer</td>
<td>ios-unified\Syncfusion.SfTabView.XForms.dll<br/>ios-unified\Syncfusion. SfTabView.XForms.iOS.dll</td>
</tr>
</table>

N> When there is a mismatch of Xamarin NuGet packages between your sample and the tab view assemblies, an error Could not load type Xamarin.Forms.ElementTemplate will occur. Refer to the ReadMe to know the software requirements of the Syncfusion controls.

# Launching the tab view on each platform

To use the tab view inside an application, each platform application must initialize the tab view renderer. This initialization step varies from platform to platform and is discussed in the following sections:

# Android

The Android launches the tab view without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application.

# iOS

To launch the tab view in iOS, call the SfTabViewRenderer.Init() in the FinishedLaunching overridden method of the AppDelegate class after the Xamarin.Forms Framework initialization and before the LoadApplication is called, as demonstrated in the following code example:

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
 {
      …            
      global::Xamarin.Forms.Forms.Init ();   
      SfTabViewRenderer.Init();   
      LoadApplication (new App ());   
      …   
 }
	
	
{% endhighlight %}

### Create a simple tab view

This section explains how to create a tab view and configure it. The control can be configured entirely in C# code or by using XAML markup. This is how the final output will look like on iOS, Android devices.

![](images/Getting-Started/xamarin_forms_tabview.png)

# Creating the project

Create a new BlankApp (Xamarin.Forms.Portable) application in Xamarin Studio or Visual Studio for Xamarin.Forms.

# Adding SfTabView in Xamarin.Forms

Add the required assembly references to the pcl and renderer projects as discussed in the Assembly deployment section.

Import the control namespace as

{% tabs %}

{% highlight xaml %}

xmlns:tabView="clr-namespace:Syncfusion.XForms.TabView;assembly=Syncfusion.SfTabView.XForms"
	
{% endhighlight %}

{% highlight C# %}

using Syncfusion.XForms.TabView;

{% endhighlight %}

{% endtabs %}

Set the control as content to the ContentPage.

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

# Adding Tab items

Tab items can be configured in tab view through the Items property of `SfTabView`, where it holds collection of `SfTabItem` through `TabItemsCollection`

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

In order to share the header space equally for the , we can set the number of tabs which can be distributed in the available space though `VisibleHeaderCount` of SfTabView.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView VisibleHeaderCount="3" >
	
{% endhighlight %}

{% highlight C# %}

tabView.VisibleHeaderCount = 3;

{% endhighlight %}

{% endtabs %}

That’s it, tab view control is ready. Now we can add the required controls for our application.  Here we are adding a `ListView` in the content region.

## Adding List view in the tab view

## Preparing data

Create a view model class with ContactsInfo collection property, initialized with required number of data objects.

{% highlight c# %}

public class ContactInfo
{
	public string Name { get; set; }
	public long Number { get; set; }
}

public class ContactsViewModel
{
	private ObservableCollection<ContactInfo> contactList;

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

Bind the items source of the `ListView` and set required appearance in its ItemsTemplate property. Where the list view can be hosted within the content region of tab item. 

{% highlight xaml %}


<tabView:SfTabItem.Content>
				<Grid BackgroundColor="Red" x:Name="AllContactsGrid" >
					<ListView x:Name="ContactListView" 
								ItemsSource="{Binding ContactList}"
								BackgroundColor="Beige" RowHeight="100">
						<ListView.BindingContext>
							<gettingStarted:ContactsViewModel />
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
			</tabView:SfTabItem.Content>

	
{% endhighlight %}

Similarly, content region for other tabs can be configured in the same way.

## Swiping

Both vertical swiping for the list view and horizontal swiping for the tab view will works by default. If it is not required it can be customized by `EnableSwiping` property of `SfTabView`.

## Tab Items

Tab items can be configured in tab view through the Items property of `SfTabView`, where it holds collection of `SfTabItem` through `TabItemsCollection`


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

## Selection changed

When selection changed due to swiping or by dynamically setting the `SelectedIndex` property of `SfTabView`, there is an event available in tab view control to get notified for the change.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView  SelectionChanged="SfTabView_SelectionChanged" >

{% endhighlight %}

{% highlight C# %}

tabView.SelectionChanged += SfTabView_SelectionChanged;

		// Raised when selected index changed
	private void SfTabView_SelectionChanged(object sender, SelectionChangedEventArgs e)
	{
		var selectedIndex = e.Index;
	}

{% endhighlight %}

{% endtabs %}

## Enable Swiping

When selection changed is needs to be restricted through user interaction, `EnableSwiping` property of `SfTabView` can be set as `false`.

## Display Type

Tab view will display the title of each tab item by default. It can be changed to any of the below type.

* Text only.
* Image only.
* Image with text.
* No header.

![](images/Getting-Started/tabstyle01.png)


It can be changed by settings the `DisplayMode` property of `SfTabView`.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView VisibleHeaderCount="3" DisplayMode="ImageWithText" >

{% endhighlight %}

{% highlight C# %}

tabView.DisplayMode = TabDisplayMode.ImageWithText;

{% endhighlight %}

{% endtabs %}

`No header` can be used when header is not needed for the tab view control, so content space will be occupied in the entire available height.

N> Image appearance in the header can be achieved through font icons.

How to change the selection color for text and font icons.

Selected index can be differentiated by setting `SelectionColor` property of `SfTabItem`.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabItem 
			Title="Calls"
			SelectionColor="Green">
			
{% endhighlight %}

{% highlight C# %}

var tabViewItem = new SfTabItem()
			{
				Title = "Calls",
				TitleFontColor = Color.Green,
			}
			
{% endhighlight %}

{% endtabs %}

Further customizations of header are discussed in the below sections.

* How to customize text appearance of the header title?
* How to set and customize font icons appearance in the header?
* Setting font file for font icons.

How to customize text appearance of the header title?

{% tabs %}

{% highlight xaml %}

tabView:SfTabItem 
			Title="Calls"
			TitleFontAttributes="Bold"
			TitleFontColor="Red"
			TitleFontSize="22">

			
{% endhighlight %}

{% highlight C# %}

var tabViewItem = new SfTabItem()
			{
				Title = "Calls",
				Content = allContactsGrid,
				TitleFontAttributes = FontAttributes.Bold,
				TitleFontColor = Color.Red,
				TitleFontSize = 22
			}
			
{% endhighlight %}

{% endtabs %}

How to set and customize font icons appearance in the header?

Add the font file into your application by following the below steps for each platform.

## Adding font file for iOS

* Add the font file with Build Action: `BundleResource`, and
* Update the `Info.plist` file (Fonts provided by application, or UIAppFonts, key).

## Adding font file for Android

* Add the font file to the `Assets` folder in the application project and set Build Action: `AndroidAsset`.
Setting font file for font icons.

{% tabs %}

{% highlight xaml %}

<ResourceDictionary>
	<OnPlatform x:TypeArguments="x:String" x:Key="fontfamily" iOS="TabIcons" Android="TabIcons.ttf" />
</ResourceDictionary>

	// . . . //

<tabview:SfTabItem Title="Calls"
	IconFont="a"
	FontIconFontColor="LightBlue"
	FontIconFontSize="20"
	FontIconFontFamily="{StaticResource fontfamily}">
			
{% endhighlight %}

{% highlight C# %}

var tabViewItem = new SfTabItem
		{
			Title = "Calls",
			Content = allContactsGrid,
			IconFont = "a", // setting value for font icons as mentioned in *.ttf.
			FontIconFontFamily = Device.RuntimePlatform == "iOS" ? "TabIcons" : "TabIcons.ttf",
			FontIconFontColor = Color.LightBlue,
			FontIconFontSize =  20
		};

			
{% endhighlight %}

{% endtabs %}

## Selection Indicator strip

Selection indicator strip can be used to indicate the selected index of the tab view control. It can be customized with the built in APIs available in `SelectionIndicatorSettings` of `SfTabView`.

![](images/Getting-Started/tabstyle02.png)


Selection indicator can be positioned below the title or above the title or else it can be filled in the entire selected header space.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView.SelectionIndicatorSettings>
			<tabView:SelectionIndicatorSettings
				Color="Yellow" 
				Position="Top" 
				StrokeThickness="10"/>
		</tabView:SfTabView.SelectionIndicatorSettings>
			
{% endhighlight %}

{% highlight C# %}

		var selectionIndicatorSettings = new SelectionIndicatorSettings();
		selectionIndicatorSettings.Color = Color.Yellow;
		selectionIndicatorSettings.Position = SelectionIndicatorPosition.Top;
		selectionIndicatorSettings.StrokeThickness = 10;

		tabView.SelectionIndicatorSettings = selectionIndicatorSettings;

			
{% endhighlight %}

{% endtabs %}

N> Stroke thickness is not applicable when selection indicator’s position is set as Fill.

## Positioning of header

Tab headers can be positioned either above the content or below the content, it can be done by setting TabHeaderPosition property of SfTabView.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView  TabHeaderPosition="Bottom" >
			
{% endhighlight %}

{% highlight C# %}

tabView.TabHeaderPosition = TabHeaderPosition.Bottom;
			
{% endhighlight %}

{% endtabs %}

When header is not needed we can set `DisplayMode` of `SfTabView` as `NoHeader`.

## Handling overflow tabs

When having large number of tabs, by default scroller will be enabled to view the overflow of headers, in case needed, it can be selected from pop-up by setting `OverflowMode` of `SfTabView` as `DropDown`.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView  OverflowMode="DropDown">
			
{% endhighlight %}

{% highlight C# %}

tabView.OverflowMode = OverflowMode.DropDown;
			
{% endhighlight %}

{% endtabs %}

By selection drop-down option for tab view control, there is a button named `“Overflow button”` (or `“More button”`) will be added to the header. When click on this button, it will display a pop-up to navigate the other indices.

N> Pop-up will display the text value only, it will show the title value of the respective tab item.

How to customize the more button?

Appearance of the text can be customized through the APIs available `OverflowButtonSettings` of `SfTabView`. It has APIs to customize both text and font icons available in this button. 

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView.OverflowButtonSettings>
			<tabView:OverflowButtonSettings 
				BackgroundColor="Red" 
				DisplayMode="Text"
				Title="..."
				TitleFontSize="30"
				TitleFontColor="Yellow"/>
		</tabView:SfTabView.OverflowButtonSettings>	

{% endhighlight %}

{% highlight C# %}

var overflowButtonSettings = new OverflowButtonSettings();
		overflowButtonSettings.BackgroundColor = Color.Red;
		overflowButtonSettings.DisplayMode = OverflowButtonDisplayMode.Text;
		overflowButtonSettings.Title = "...";
		overflowButtonSettings.TitleFontSize = 30;
		overflowButtonSettings.TitleFontColor = Color.Yellow;
		tabView.OverflowButtonSettings = overflowButtonSettings;
			
{% endhighlight %}

{% endtabs %}

## Custom  

When built-in view is not needed, it can be overridden by adding custom view for the header region for a tab. 

{% tabs %}

{% highlight xaml %}

<tabView:SfTabItem Title="Calls" >
			<tabView:SfTabItem.HeaderContent>
				< Button 
					Text="All Calls" 
					BackgroundColor="Yellow"
					Clicked="Button_Clicked" />
			</tabView:SfTabItem.HeaderContent>
			<tabView:SfTabItem.Content>
				<!--Some content -->
			</tabView:SfTabItem.Content>
		</tabView:SfTabItem>

{% endhighlight %}

{% highlight C# %}

var allCallsButton = new Button();
	allCallsButton.Text = "All Calls";
	allCallsButton.BackgroundColor = Color.Yellow;
	allCallsButton.Clicked += AllCallsButton_Clicked;
	var tabViewItem = new SfTabItem()
	{
		Title = "Calls",
		Content = allContactsGrid,
		HeaderContent = allCallsButton
	};
			
{% endhighlight %}

{% endtabs %}

How to handle events for custom view with tab view?

When using button or similar control with clicked event, it can be handled directly and set the SelectedIndex property to navigate the clicked view.

{% highlight C# %}

private void Button_Clicked(object sender, System.EventArgs e)
{
	tabView.SelectedIndex = 0;
}
			
{% endhighlight %}

N> If click event is not available, it can be achieved by set TapGestureRecognizer for the custom view.


