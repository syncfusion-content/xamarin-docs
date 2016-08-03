---
layout: post
title: Getting Started with Syncfusion NavigationDrawer control for Xamarin.Forms
description: A quick tour to initial users on Syncfusion NavigationDrawer control for Xamarin.Android platform
platform: Xamarin
control: NavigationDrawer
documentation: ug
---

# Getting Started

This section explains you the steps to configure a SfNavigationDrawer control in a real-time scenario and also provides a walk-through on some of the customization features available in SfNavigationDrawer control.

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

### PCL 

pcl\Syncfusion.SfNavigationDrawer.XForms.dll

### Android 

android\Syncfusion.SfNavigationDrawer.Android.dll
android\Syncfusion.SfNavigationDrawer.XForms.dll
android\Syncfusion.SfNavigationDrawer.XForms.Android.dll 
Xamarin.Android.Support.v4 (from NuGet Packages)
	
### iOS 

iOS-unified\Syncfusion.SfNavigationDrawer.iOS.dll
iOS-unified\SyncfusionSfNavigationDrawer.XForms.dll
iOS-unified\Syncfusion.SfNavigationDrawer.XForms.iOS.dll

### Windows Phone

wp8\Syncfusion.SfNavigationDrawer.WP8.dll
wp8\Syncfusion.SfNavigationDrawer.XForms.dll
wp8\Syncfusion.SfNavigationDrawer.XForms.WinPhone.dll

### Windows Phone 8.1

wp81\Syncfusion.SfNavigationDrawer.WP.dll
wp81\Syncfusion.SfNavigationDrawer.XForms.dll
wp81\Syncfusion.SfNavigationDrawer.XForms.WinPhone.dll

### WinRT 

winrt\Syncfusion.SfNavigationDrawer.WinRT.dll
winrt\Syncfusion.SfNavigationDrawer.XForms.dll
winrt\Syncfusion.SfNavigationDrawer.XForms.WinRT.dll

### UWP 

uwp\Syncfusion.SfNavigationDrawer.UWP.dll
uwp\Syncfusion.SfNavigationDrawer.XForms.dll
uwp\Syncfusion.SfNavigationDrawer.XForms.UWP.dll

Currently an additional step is required for Windows Phone, Windows Phone 8.1 and iOS projects. We need to create an instance of the NavigationDrawer custom renderer as shown below. 

Create an instance of SfNavigationDrawerRenderer in MainPage constructor of the Windows Phone and Windows Phone 8.1  project as shown 

{% tabs %}

{% highlight C# %}

public MainPage()
{
    new SfNavigationDrawerRenderer();
}

{% endhighlight %}

{% endtabs %}

Create an instance of SfNavigationDrawerRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% tabs %}

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{   
    new SfNavigationDrawerRenderer ();
}	

{% endhighlight %}

{% endtabs %}

## Add SfNavigationDrawer

The SfNavigationDrawer control configured entirely in C# code or by using XAML markup. The following steps explains how to create a SfNavigationDrawer and configure its elements.

* Adding namespace for the added assemblies. 

{% tabs %}

{% highlight xaml %}

	<xmlns:navigation="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"/>
	
{% endhighlight %}

{% highlight c# %}

	using Syncfusion.SfNavigationDrawer.XForms;

{% endhighlight %}

{% endtabs %}

* Now add the SfNavigationDrawer control with a required optimal name by using the included namespace.

{% tabs %}

{% highlight xaml %}

<navigation:SfNavigationDrawer x:Name="navigationDrawer"/>
	
{% endhighlight %}

{% highlight c# %}

SfNavigationDrawer navigationDrawer=new SfNavigationDrawer();
this.Content=navigationDrawer;

{% endhighlight %}

{% endtabs %}

## Add Drawer Content

SfNavigationDrawer supports to set the Main content of the sliding DrawerPanel. This can be set using `DrawerContentView` property with desired views.

The control has been initialized in XAML

{% tabs %}

{% highlight xaml %}

    <navigation:SfNavigationDrawer x:Name="navigationDrawer"  />
	
{% endhighlight %}

{% endtabs %}

and the content has set using `DrawerContentView` property.

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

{% endtabs %}


## Add Drawer Header Content

SfNavigationDrawer provides option to display certain information like user id or names in the header part instead of providing everything in the drawer content view. 

This can be done using `DrawerHeaderView` property in SfNavigationDrawer.

{% tabs %}

{% highlight xaml %}
    
<navigation:SfNavigationDrawer x:Name="navigationDrawer">
    <navigation:SfNavigationDrawer.DrawerHeaderView>
         <StackLayout x:Name="headerLayout" Orientation="Vertical" HeightRequest="200" WidthRequest="275">
                <Image x:Name="image" HeightRequest="100" WidthRequest="70" Source="user.png" />
                <Label x:Name="header" Text="James Pollock" FontSize="20" HeightRequest="30" WidthRequest="140" /> 
         </StackLayout>
    </navigation:SfNavigationDrawer.DrawerHeaderView>
</navigation:SfNavigationDrawer>
{% endhighlight %}

{% highlight c# %}

StackLayout headerLayout = new StackLayout ();
headerLayout.Orientation = StackOrientation.Vertical;
headerLayout.BackgroundColor = Color.FromHex ("#1aa1d6");
headerLayout.VerticalOptions = LayoutOptions.CenterAndExpand;
headerLayout.HorizontalOptions = LayoutOptions.CenterAndExpand;
headerLayout.HeightRequest = 200;
headerLayout.WidthRequest = 275;
Image image = new Image ();
image.Source = ImageSource.FromFile("user.png");
image.HeightRequest = 100;
image.WidthRequest =  70;
image.HorizontalOptions = LayoutOptions.CenterAndExpand;
image.VerticalOptions = LayoutOptions.Center;
image.BackgroundColor = Color.FromHex ("#1aa1d6");
headerLayout.Children.Add (image);

Label header = new Label ();
header.Text  = "James Pollock";
header.FontSize = 20;
header.HeightRequest = 30;
header.WidthRequest = 140;
header.TextColor = Color.White;
header.HorizontalOptions = LayoutOptions.Center;
header.VerticalOptions = LayoutOptions.Center;
header.BackgroundColor = Color.FromHex ("#1aa1d6");
headerLayout.Children.Add (header);			
navigationDrawer.DrawerHeaderView=headerLayout;
  
{% endhighlight %}

{% endtabs %}

## Adjust Drawer Width

Height and Width of the Drawer can be customized in SfNavigationDrawer. User can customize the size of the Drawer according to their requirement using `DrawerHeight` and `DrawerWidth` properties as in the below code snippet.

{% tabs %}

{% highlight xaml %}

<navigation:SfNavigationDrawer x:Name="navigationDrawer"  DrawerWidth="300" />
	
{% endhighlight %}

{% highlight c# %}        
        
navigationDrawer.DrawerWidth = 300;
  
{% endhighlight %}

{% endtabs %}

## Add Main Content 

The main view of the SfNavigationDrawer can be set using `ContentView` property with desired views.

{% tabs %}

{% highlight xaml %}

 	<navigation:SfNavigationDrawer x:Name="navigationDrawer">
        <navigation:SfNavigationDrawer.ContentView>
             <StackLayout x:Name="ContentFrame" Orientation="Vertical">
				<StackLayout x:Name="headerFrame" Orientation="Horizontal">
					 <Button x:Name="imageButton" FontSize="20" HeightRequest="50" Grid.Column="0" BackgroundColor="#1aa1d6" HorizontalOptions="Start" WidthRequest="50" />
					 <Label x:Name="homeLabel" FontSize="15" HorizontalTextAlignment="Center" VerticalTextAlignment="Center"     HeightRequest="50"  TextColor="White" />
			    </StackLayout>   
				<Label x:Name="mainLabel" FontSize="14" TextColor="Black">
					<Label.Text>
						Lorem ipsum dolor sit amet, lacus amet amet ultricies. Quisque mi venenatis morbi libero, orci dis, mi ut et class porta, massa ligula magna enim, aliquam orci vestibulum tempus. Turpis facilisis vitae consequat, cum a a, turpis dui consequat massa in dolor per, felis non amet. Auctor eleifend in omnis elit vestibulum, donec non elementum tellus est mauris, id aliquam, at lacus, arcu pretium proin lacus dolor et. Eu tortor, vel ultrices amet dignissim mauris vehicula. Lorem tortor neque, purus taciti quis id. Elementum integer orci accumsan minim phasellus vel.
					</Label.Text>
				</Label>   
             </StackLayout>
        </navigation:SfNavigationDrawer.ContentView>
 	</navigation:SfNavigationDrawer> 
 
{% endhighlight %}

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

{% endtabs %}

## Set Drawing Edge for Drawer Panel

SfNavigationDrawer provides support to change the sliding position of the DrawerView panel. This can be set using `Position` property. The position can be any one of the following four options.

* Left

* Right

* Top

* Bottom

N> The default option is Left.


{% tabs %}	

{% highlight xaml %}

<navigation:SfNavigationDrawer x:Name="navigationDrawer" Position="Left">
  	
{% endhighlight %}
	
{% highlight c# %}

navigationDrawer.Position=Position.Left;

{% endhighlight %}

{% endtabs %}


## Change Drawer Opening Animation

The DrawerView panel can be opened on the top of the Content. This opening animation for the DrawerView panel can be set using the `Transition` enumeration property which has the following three options.

* SlideOnTop
* Push
* Reveal

N> The default Transition is SlideOnTop.

{% tabs %}	

{% highlight xaml %}

<navigation:SfNavigationDrawer x:Name="navigationDrawer" Transition="SlideOnTop">
	
{% endhighlight %}
	
{% highlight c# %} 

navigationDrawer.Transition=Transition.SlideOnTop;

{% endhighlight %}

{% endtabs %}

The SfNavigationDrawer looks as follows

![](images/Slide-on-top.png)