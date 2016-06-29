---
layout: post
title: Getting Started with Syncfusion NavigationDrawer control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion NavigationDrawer control for Xamarin.Android platform
platform: Xamarin
control: NavigationDrawer
documentation: ug
---

# Getting Started

This section provides overview for working with Essential NavigationDrawer for Xamarin Forms. You can walk through the entire process of creating an NavigationDrawer.

![](images/getting-started.png)

## Referencing Essential Studio Components in Your Solution	

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.

Components/syncfusionessentialstudio-version/lib/pcl/

Alternatively if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.

After installing Essential Studio for Xamarin, all the required assemblies can be found in the installation folders, typically

{Syncfusion Installed location}\Essential Studio\syncfusionessentialstudio-version\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\lib

Or after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder

{Download location}\syncfusionessentialstudio-version\lib

You can then add the assembly references to the respective projects as shown below

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>PCL</td>
<td>pcl\Syncfusion.SfNavigationDrawer.XForms.dll</td>
</tr>
<tr>
<td>Android</td>
<td>android\Syncfusion.SfNavigationDrawer.Android.dll<br/>android\Syncfusion.SfNavigationDrawer.XForms.dll<br/> android\Syncfusion.SfNavigationDrawer.XForms.Android.dll <br/> Xamarin.Android.Support.v4 (from Nuget Packages)</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>ios-unified\Syncfusion.SfNavigationDrawer.iOS.dll<br/>ios-unified\SyncfusionSfNavigationDrawer.XForms.dll<br/>ios-unified\Syncfusion.SfNavigationDrawer.XForms.iOS.dll</td>
</tr>
<tr>
<td>Windows Phone</td>
<td>wp8\Syncfusion.SfInput.WP8.dll<br/>wp8\Syncfusion.SfShared.WP8.dll<br/>wp8\Syncfusion.SfNavigationDrawer.XForms.dll<br/>wp8\Syncfusion.SfNavigationDrawer.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>Windows Phone 8.1</td>
<td>wp81\Syncfusion.SfInput.WP.dll<br/>wp81\Syncfusion.SfShared.WP.dll<br/>wp81\Syncfusion.SfNavigationDrawer.XForms.dll<br/>wp81\Syncfusion.SfNavigationDrawer.XForms.WinPhone.dll</td>
</tr>
<tr>
<td>WinRT</td>
<td>winrt\Syncfusion.SfInput.WinRT.dll<br/>winrt\Syncfusion.SfShared.WinRT.dll<br/>winrt\Syncfusion.SfNavigationDrawer.XForms.dll<br/>winrt\Syncfusion.SfNavigationDrawer.XForms.WinRT.dll</td>
</tr>
<tr>
<td>UWP</td>
<td>uwp\Syncfusion.SfInput.UWP.dll<br/>uwp\Syncfusion.SfShared.UWP.dll<br/>uwp\Syncfusion.SfNavigationDrawer.XForms.dll<br/>uwp\Syncfusion.SfNavigationDrawer.XForms.UWP.dll</td>
</tr>
</table>

Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the NavigationDrawer custom renderer as shown below. 

Create an instance of SfNavigationDrawerRenderer in MainPage constructor of the Windows Phone and Windows Phone 8.1  project as shown 

{% highlight C# %}

public MainPage()

{

    new SfNavigationDrawerRenderer();

    ...    

}

{% endhighlight %}

Create an instance of SfNavigationDrawerRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)

{

    ...

    new SfNavigationDrawerRenderer ();

    ...

}	

{% endhighlight %}

## Add and Configure the NavigationDrawer

The NavigationDrawer control configured entirely in C# code or by using XAML markup. The following steps explain on how to create a NavigationDrawer and configure its elements,

* Adding reference to NavigationDrawer.

{% tabs %}

{% highlight c# %}

	using Syncfusion.SfNavigationDrawer.XForms;

{% endhighlight %}

{% highlight xaml %}

	xmlns:navigation="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms" 
	
{% endhighlight %}

{% endtabs %}

* Create an instance of NavigationDrawer.

{% tabs %}

{% highlight c# %}

	SfNavigationDrawer navigationDrawer=new SfNavigationDrawer();
	this.Content=navigationDrawer;

{% endhighlight %}

{% highlight xaml %}

	<navigation:SfNavigationDrawer x:Name="navigationDrawer"/>
	
{% endhighlight %}

{% endtabs %}

### Setting Content View

The main view of the NavigationDrawer can be set using `ContentView` property with desired views.

{% tabs %}

{% highlight c# %}
	
	Button imageButton = new Button();
	imageButton.Source = (FileImageSource)ImageSource.FromFile ("_menu_.png");
	imageButton.WidthRequest=50;
	
	Label homeLabel=new Label();
	homeLabel.Text="Home";
	homeLabel.FontSize=15;
	homeLabel.TextColor=Color.White;
	homeLabel.HorizontalTextAlignment=TextAlignment.Center;
	homeLabel.VerticalTextAlignment=TextAlignment.Center;
	
	StackLayout headerFrame=new StackLayout(); 
	headerFrame.Orientation = StackOrientation.Horizontal;
	headerFrame.Children.Add(imageButton);
	headerFrame.Children.Add(homeLabel);
	
	Label mainLabel=new Label();
	mainLabel.FontSize=14;
	mainLabel.TextColor=Color.Black;
	mainLabel.Text="Lorem ipsum dolor sit amet, lacus amet amet ultricies. Quisque mi venenatis morbi libero, orci dis, mi ut et class porta, massa ligula magna enim, aliquam orci vestibulum tempus. Turpis facilisis vitae consequat, cum a a, turpis dui consequat massa in dolor per, felis non amet. Auctor eleifend in omnis elit vestibulum, donec non elementum tellus est mauris, id aliquam, at lacus, arcu pretium proin lacus dolor et. Eu tortor, vel ultrices amet dignissim mauris vehicula. Lorem tortor neque, purus taciti quis id. Elementum integer orci accumsan minim phasellus vel.";
	
	StackLayout ContentFrame=new StackLayout();
	ContentFrame.Orientation = StackOrientation.Vertical; 
	ContentFrame.BackgroundColor=Color.White;
	ContentFrame.Children.Add(headerFrame);
	ContentFrame.Children.Add(mainLabel);
	navigationDrawer.ContentView=ContentFrame;
  
{% endhighlight %}

	  
{% highlight xaml %}

 	<navigation:SfNavigationDrawer x:Name="navigationDrawer">
        <navigation:SfNavigationDrawer.ContentView>
            <StackLayout x:Name="ContentFrame" Orientation="Horizontal">
				<StackLayout x:Name="headerFrame" Orientation="Vertical">
					 <Button x:Name="imageButton" FontSize="20" HeightRequest="50" Grid.Column="0" Clicked="Btn_Clicked" BackgroundColor="#1aa1d6" HorizontalOptions="Start" WidthRequest="50" />
					 <Label x:Name="homeLabel" FontSize="15" HorizontalTextAlignment="Center" VerticalTextAlignment="Center"     HeightRequest="50"  TextColor="White" />
			    </StackLayout>   
				<Label x:Name="mainLabel" FontSize="14" TextColor="Black" />   
             </StackLayout>
        </navigation:SfNavigationDrawer.ContentView>
 	</navigation:SfNavigationDrawer>
 
 
{% endhighlight %}

{% endtabs %}

### Setting DrawerContent View

The sliding main content of the NavigationDrawer which is a part of DrawerPanel can be set using `DrawerContentView` property with desired views.

{% tabs %}

{% highlight c# %}

	StackLayout mainStack = new StackLayout ();
	mainStack.Opacity = 1;
	mainStack.Orientation = StackOrientation.Vertical;
	mainStack.HeightRequest = 500;
	mainStack.BackgroundColor = Color.White;

	ObservableCollection<String> list = new ObservableCollection<string> ();
	list.Add ("Home");
	list.Add ("Profile");
	list.Add ("Inbox");
	list.Add ("Outbox");
    list.Add ("Sent");
	list.Add ("Draft");

	ListView listView = new ListView();
	listView.WidthRequest= 200;
	listView.VerticalOptions = LayoutOptions.FillAndExpand;
	listView.ItemsSource = list;
	mainStack.Children.Add (listView);
            
    navigationDrawer.DrawerContentView = mainStack;
  
{% endhighlight %}

{% highlight xaml %}

    <navigation:SfNavigationDrawer x:Name="navigationDrawer" DrawerContentView="{Binding }" />
	
{% endhighlight %}

{% endtabs %}