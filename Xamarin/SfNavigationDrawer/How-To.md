---
layout: post
title: Opening drawer panel in Syncfusion's NavigationDrawer control for Xamarin.Forms
description: Learn how to open Drawer panel programmatically.
platform: Xamarin
control: NavigationDrawer
documentation: ug
---
## How To Open Drawer Panel Programmatically?

In order to open NavigationDrawer's drawer panel, a public method is available which can be hooked through NavigationDrawer instance

{% tabs %}

{% highlight C# %}

				DependencyService.Get<IToggleDrawer>().ToggleDrawer();

{% endhighlight %}

{% endtabs %}


## How To Open the Drawer Content in Full Screen?

It can be done using `DrawerWidth` and `DrawerHeight` properties in SfNavigationDrawer control. Width and Height can be set according to the screen bounds to acquire the sliding panel to desired size.

{% tabs %}

{% highlight c# %}

navigationDrawer.DrawerHeight=300;
navigationDrawer.DrawerWidth=300;

{% endhighlight %}

{% endtabs %}

## How To Perform an Action while Drawer is Opening Or Closing?

The `Toggled` event can be hooked to get opening and closing events. This has parameters of NavigationDrawer and a boolean property to display whether it is open or closed.

{% tabs %}

{% highlight C# %}

navigationDrawer.Toggled += (object sender,Syncfusion.SfNavigationDrawer.XForms.ToggledEventArgs e) => {
		// your codes here
		bool drawerState = e.isOpen;
};
{% endhighlight %}

{% endtabs %}

## How to add burger icon to toggle menu.?

By default NavigationDrawer does not provide toggle button. This can be created and customized as per the application's requirement.

{% tabs %}

{% highlight xaml %}

 	<navigation:SfNavigationDrawer x:Name="navigationDrawer">
        <navigation:SfNavigationDrawer.ContentView>
           <StackLayout x:Name="ContentFrame" Orientation="Vertical">
				<StackLayout x:Name="headerFrame" Orientation="Horizontal">
					 <Button x:Name="imageButton" FontSize="20" HeightRequest="50"  BackgroundColor="#1aa1d6" HorizontalOptions="Start" WidthRequest="50" />
					 <Label x:Name="homeLabel" FontSize="15" HorizontalTextAlignment="Center" VerticalTextAlignment="Center"     HeightRequest="50"  TextColor="White" />
			    </StackLayout>   
				// your main content can be added here
             </StackLayout>
        </navigation:SfNavigationDrawer.ContentView>
 	</navigation:SfNavigationDrawer>
 
 
{% endhighlight %}

{% highlight c# %}
	
Button imageButton = new Button();
imageButton.Source = (FileImageSource)ImageSource.FromFile ("menu.png"); // menu.png is the burger icon and it has to be added to resources
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
	
StackLayout ContentFrame=new StackLayout();
ContentFrame.Orientation = StackOrientation.Vertical; 
ContentFrame.BackgroundColor=Color.White;
ContentFrame.Children.Add(headerFrame);
ContentFrame.Children.Add(mainContent); // here main content is not added
navigationDrawer.ContentView=ContentFrame;

imageButton.Clicked += (sender, e) =>
{
			DependencyService.Get<IToggleDrawer>().ToggleDrawer();
};
  
{% endhighlight %}

{% endtabs %}

## How to modify touch drag sensitivity.?

In few screens user may find difficult to drag the drawer from the edge, in such cases we can vary the touch drag region using Touch threshold property. This increases the dragging bounds of the drawer

{% tabs %}

{% highlight xaml %}

 	<navigation:SfNavigationDrawer x:Name="navigationDrawer" TouchThreshold="100">
 
 
{% endhighlight %}

{% highlight C# %}

	navigationDrawer.TouchThreshold= 100;

{% endhighlight %}

{% endtabs %}