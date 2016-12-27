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

## Add SfNavigationDrawer

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
<td>android\Syncfusion.SfNavigationDrawer.Android.dll<br/>android\Syncfusion.SfNavigationDrawer.XForms.dll<br/> android\Syncfusion.SfNavigationDrawer.XForms.Android.dll <br/> Xamarin.Android.Support.v4 (from NuGet Packages)</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>iOS-unified\Syncfusion.SfNavigationDrawer.iOS.dll<br/>iOS-unified\SyncfusionSfNavigationDrawer.XForms.dll<br/>iOS-unified\Syncfusion.SfNavigationDrawer.XForms.iOS.dll</td>
</tr>
<tr>
<td>UWP</td>
<td>uwp\Syncfusion.SfNavigationDrawer.UWP.dll<br/>uwp\Syncfusion.SfNavigationDrawer.XForms.dll<br/>uwp\Syncfusion.SfNavigationDrawer.XForms.UWP.dll</td>
</tr>
</table>

Currently an additional step is required for iOS project. We need to create an instance of the NavigationDrawer custom renderer as shown below. 

Create an instance of SfNavigationDrawerRenderer in FinishedLaunching overridden method of AppDelegate class in iOS Project as shown below

{% tabs %}

{% highlight C# %}

public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{   
    new SfNavigationDrawerRenderer ();
}	

{% endhighlight %}

{% endtabs %}

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


## Change Drawer Opening Animation

The DrawerView panel can be opened on the top of the Content. This opening animation for the DrawerView panel can be set using the `Transition` enumeration property which has the following three options.

* SlideOnTop
* Push
* Reveal

N> The default Transition is SlideOnTop.

{% tabs %}	

{% highlight xaml %}

<navigation:SfNavigationDrawer x:Name="navigationDrawer" Transition="SlideOnTop" DrawerWidth="300">
	
{% endhighlight %}
	
{% highlight c# %} 

navigationDrawer.Transition=Transition.SlideOnTop;
navigationDrawer.DrawerWidth = 300;

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

<navigation:SfNavigationDrawer x:Name="navigationDrawer" Position="Left" Transition="SlideOnTop" DrawerWidth="300">
  	
{% endhighlight %}
	
{% highlight c# %}

navigationDrawer.Position=Position.Left;
navigationDrawer.Transition=Transition.SlideOnTop;
navigationDrawer.DrawerWidth = 300;

{% endhighlight %}

{% endtabs %}

## Add Drawer Content

SfNavigationDrawer supports to set the Main content of the sliding DrawerPanel. This can be set using `DrawerContentView` property with desired views.

The control has been initialized in XAML


{% highlight xaml %}

    <navigation:SfNavigationDrawer x:Name="navigationDrawer" Position="Left" Transition="SlideOnTop" DrawerWidth="300">
    			<navigation:SfNavigationDrawer.DrawerContentView>
					<ListView x:Name="listView" BackgroundColor="White"/>
				</navigation:SfNavigationDrawer.DrawerContentView>
	</navigation:SfNavigationDrawer>
	
{% endhighlight %}


and the list items are created in C#. 


{% highlight c# %}
			ObservableCollection<String> list = new ObservableCollection<string>();
			list.Add("Home");
			list.Add("Profile");
			list.Add("Inbox");
			list.Add("Outbox");
			list.Add("Sent");
			list.Add("Draft");
			listView.ItemsSource = list;  
{% endhighlight %}


## Add Drawer Header Content

SfNavigationDrawer provides option to display certain information like user id or names in the header part instead of providing everything in the drawer content view. 

This can be done using `DrawerHeaderView` property in SfNavigationDrawer.

{% tabs %}

{% highlight xaml %}
    
<navigation:SfNavigationDrawer x:Name="navigationDrawer" Position="Left" Transition="SlideOnTop" DrawerWidth="300">
    <navigation:SfNavigationDrawer.DrawerHeaderView>
					<Grid x:Name="headerLayout" BackgroundColor="#1aa1d6" >
						<Label x:Name="header"  Text="Header View" FontSize="14" TextColor="White"  VerticalTextAlignment="Center" HorizontalTextAlignment="Center"  />
					</Grid>
	</navigation:SfNavigationDrawer.DrawerHeaderView>
	<navigation:SfNavigationDrawer.DrawerContentView>
					<ListView x:Name="listView" BackgroundColor="White"/> <!--list items has to be created in C#-->
				</navigation:SfNavigationDrawer.DrawerContentView>
</navigation:SfNavigationDrawer>
{% endhighlight %}

{% highlight c# %}
SfNavigationDrawer navigationDrawer=new SfNavigationDrawer();
			navigationDrawer.Position=Position.Left;
			navigationDrawer.Transition=Transition.SlideOnTop;
			navigationDrawer.DrawerWidth = 300;
			Grid headerLayout = new Grid();
			headerLayout.BackgroundColor = Color.FromHex("#1aa1d6");
			Label header = new Label();
			header.Text = "Header View";
			header.FontSize = 20;
			header.TextColor = Color.White;
			header.HorizontalTextAlignment = TextAlignment.Center;
			header.VerticalTextAlignment = TextAlignment.Center;
			header.BackgroundColor = Color.FromHex("#1aa1d6");
			headerLayout.Children.Add(header);

			navigationDrawer.DrawerHeaderView = headerLayout;
			
			ListView listView = new ListView();
			listView.BackgroundColor = Color.White;
			ObservableCollection<String> list = new ObservableCollection<string>();
			list.Add("Home");
			list.Add("Profile");
			list.Add("Inbox");
			list.Add("Outbox");
			list.Add("Sent");
			list.Add("Draft");
			listView.ItemsSource = list;

			navigationDrawer.DrawerContentView = listView;
  
{% endhighlight %}

{% endtabs %}

## Add Main Content 

The main view of the SfNavigationDrawer can be set using `ContentView` property with desired views.

{% tabs %}

{% highlight xaml %}

 <navigation:SfNavigationDrawer x:Name="navigationDrawer" Position="Left" Transition="SlideOnTop" DrawerWidth="200" DrawerHeaderHeight="50" DrawerFooterHeight="0">
        <navigation:SfNavigationDrawer.ContentView>
            <Grid>
				<Grid.RowDefinitions>
					<RowDefinition Height="Auto"/>
					<RowDefinition Height="*"/>
				</Grid.RowDefinitions>
				<Label x:Name="ContentHeader" Text="Content View" BackgroundColor="#1aa1d6"  FontSize="14" TextColor="White" VerticalOptions="StartAndExpand" HorizontalTextAlignment="Center" HorizontalOptions="FillAndExpand" />
         		<Button Text="Show Menu" Grid.Row="1"  BackgroundColor="#1aa1d6"  x:Name="Btnmenu" HorizontalOptions="Center" VerticalOptions="Center" ></Button>
    		</Grid>
        </navigation:SfNavigationDrawer.ContentView>
        
         <navigation:SfNavigationDrawer.DrawerHeaderView>
					<Grid x:Name="headerLayout" BackgroundColor="#1aa1d6" >
						<Label x:Name="header"  Text="Header View" FontSize="14" TextColor="White"  VerticalTextAlignment="Center" HorizontalTextAlignment="Center"  />
					</Grid>
	</navigation:SfNavigationDrawer.DrawerHeaderView>
	
	<navigation:SfNavigationDrawer.DrawerContentView>
					<ListView x:Name="listView" BackgroundColor="White"/> <!--list items has to be created in C#-->
				</navigation:SfNavigationDrawer.DrawerContentView>
 </navigation:SfNavigationDrawer> 
 
{% endhighlight %}

{% highlight c# %}
SfNavigationDrawer navigationDrawer=new SfNavigationDrawer();
			navigationDrawer.Position = Position.Left;
			navigationDrawer.Transition = Transition.SlideOnTop;
			navigationDrawer.DrawerWidth = 200;
			navigationDrawer.DrawerHeaderHeight = 50;
			navigationDrawer.DrawerFooterHeight = 0;
			Grid headerLayout = new Grid();
			headerLayout.BackgroundColor = Color.FromHex("#1aa1d6");
			Label header = new Label();
			header.Text = "Header View";
			header.FontSize = 14;
			header.TextColor = Color.White;
			header.HorizontalTextAlignment = TextAlignment.Center;
			header.VerticalTextAlignment = TextAlignment.Center;
			header.BackgroundColor = Color.FromHex("#1aa1d6");
			headerLayout.Children.Add(header);

			navigationDrawer.DrawerHeaderView = headerLayout;

			ListView listView = new ListView();
			listView.BackgroundColor = Color.White;
			ObservableCollection<String> list = new ObservableCollection<string>();
			list.Add("Home");
			list.Add("Profile");
			list.Add("Inbox");
			list.Add("Outbox");
			list.Add("Sent");
			list.Add("Draft");
			listView.ItemsSource = list;

			navigationDrawer.DrawerContentView = listView;

			Button Btnmenu = new Button();
			Btnmenu.Text = "Show Menu";
			Btnmenu.HorizontalOptions = LayoutOptions.Center;
			Btnmenu.VerticalOptions = LayoutOptions.Center;
			Btnmenu.BackgroundColor = Color.FromHex("#1aa1d6");

			Label homeLabel = new Label();
			homeLabel.Text = "Content View";
			homeLabel.FontSize = 15;
			homeLabel.TextColor = Color.White;
			homeLabel.BackgroundColor = Color.FromHex("#1aa1d6");
			homeLabel.HorizontalOptions = LayoutOptions.FillAndExpand;
			homeLabel.VerticalOptions = LayoutOptions.StartAndExpand;
			homeLabel.HorizontalTextAlignment = TextAlignment.Center;
			homeLabel.VerticalTextAlignment = TextAlignment.Center;

			Grid contentView = new Grid();
			contentView.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(50, GridUnitType.Auto) });
			contentView.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(1, GridUnitType.Star) });
			contentView.Children.Add(homeLabel);
			contentView.Children.Add(Btnmenu);

			Grid.SetRow(homeLabel, 0);
			Grid.SetRow(Btnmenu, 1);

			navigationDrawer.ContentView = contentView;

			Btnmenu.Clicked += (sender, e) =>
			{
				DependencyService.Get<IToggleDrawer>().ToggleDrawer();
			};
  
{% endhighlight %}

{% endtabs %}



The SfNavigationDrawer looks as follows

![](images/getting-started.png)