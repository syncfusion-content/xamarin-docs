---
layout: post
title: Various features of Syncfusion NavigationDrawer control for Xamarin.Forms
description: Learn how to set content view, drawer content view, footer view, header view, drawer size in NavigationDrawer.
platform: Xamarin
control: NavigationDrawer
documentation: ug
---


# Setting Main Content

The SfNavigationDrawer is mainly divided into two parts, such as [Main Content](#main-content) and  [Drawer Panel Content](/Xamarin/SfNavigationDrawer/Drawer-Content "Sliding Panel Contents")

## Main Content

The main display view that displays our various content of the app can be set using `ContentView` property with desired views.

{% tabs %}

{% highlight xaml %}

 	<navigation:SfNavigationDrawer x:Name="navigationDrawer">
        <navigation:SfNavigationDrawer.ContentView>
           <StackLayout x:Name="ContentFrame" Orientation="Vertical">
				<StackLayout x:Name="headerFrame" BackgroundColor="#1aa1d6" Orientation="Horizontal">
					 <Button x:Name="imageButton" FontSize="20" HeightRequest="50" Image="_menu_.png"  BackgroundColor="#1aa1d6" HorizontalOptions="Start" WidthRequest="50" />
					 <Label x:Name="homeLabel" FontSize="15" HorizontalTextAlignment="Center" VerticalTextAlignment="Center" Text="Home"  HeightRequest="50" HorizontalOptions="FillAndExpand" TextColor="White" />
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
	
SfNavigationDrawer navigationDrawer = new SfNavigationDrawer();
			Button imageButton = new Button();
			imageButton.Image = (FileImageSource)ImageSource.FromFile("_menu_.png");
			imageButton.BackgroundColor = Color.Transparent;
			imageButton.BorderColor = Color.Transparent;
			imageButton.WidthRequest = 50;

			Label homeLabel = new Label();
			homeLabel.Text = "Home";
			homeLabel.FontSize = 15;
			homeLabel.TextColor = Color.White;
			homeLabel.HorizontalOptions = LayoutOptions.FillAndExpand;
			homeLabel.HorizontalTextAlignment = TextAlignment.Center;
			homeLabel.VerticalTextAlignment = TextAlignment.Center;

			StackLayout headerFrame = new StackLayout();
			headerFrame.Padding = new Thickness(0, 0, 0, 0);
			headerFrame.BackgroundColor = Color.FromHex("#1aa1d6");
			headerFrame.Orientation = StackOrientation.Horizontal;
			headerFrame.Children.Add(imageButton);
			headerFrame.Children.Add(homeLabel);

			Label mainLabel = new Label();
			mainLabel.FontSize = 14;
			mainLabel.TextColor = Color.Black;
			mainLabel.Text = "Lorem ipsum dolor sit amet, lacus amet amet ultricies. Quisque mi venenatis morbi libero, orci dis, mi ut et class porta, massa ligula magna enim, aliquam orci vestibulum tempus. Turpis facilisis vitae consequat, cum a a, turpis dui consequat massa in dolor per, felis non amet. Auctor eleifend in omnis elit vestibulum, donec non elementum tellus est mauris, id aliquam, at lacus, arcu pretium proin lacus dolor et. Eu tortor, vel ultrices amet dignissim mauris vehicula. Lorem tortor neque, purus taciti quis id. Elementum integer orci accumsan minim phasellus vel.";

			StackLayout ContentFrame = new StackLayout();
			ContentFrame.Orientation = StackOrientation.Vertical;
			ContentFrame.BackgroundColor = Color.White;
			ContentFrame.Children.Add(headerFrame);
			ContentFrame.Children.Add(mainLabel);
			navigationDrawer.ContentView = ContentFrame;
  
{% endhighlight %}

{% endtabs %}
	
![](images/Content-View.png)