---
layout: post
title:  Custom Header
description: Custom Header in Syncfusion TabView control for Xamarin.Forms platform
platform: Xamarin.Forms
control: TabView
documentation: ug
---

# Custom Header 

When the built-in view is not needed, it can be overridden by adding the custom view to the header region in tabs. The tab view header can be customized by adding different views inside header content like image,button,label etc.The following code example explains how to customize the header content in desired way.

N> Selection indicator setting's properties will not be working when using custom header.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabItem Title="Calls" >
	<tabView:SfTabItem.HeaderContent>
	< Button 
		Text="All Calls" 
		BackgroundColor="Yellow"
		Clicked="Button_Clicked" 
	/>
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

In the below example header has been customized by adding image and label as the header content of the tab view.

{% highlight xaml %}
<syncfusion:SfTabItem.HeaderContent>
<Grid x:Name="mainGrid" VerticalOptions="Center" HeightRequest="400" WidthRequest="500" HorizontalOptions="Center">
<Grid.RowDefinitions>
<RowDefinition Height="*" />
<RowDefinition Height="*" />
</Grid.RowDefinitions>
<Label Text="James"
 TextColor="Red"
 FontSize="16" Grid.Row="0"
 WidthRequest="80"
 HeightRequest="50"
 VerticalOptions="Center"
 HorizontalOptions="Center"/>
<Grid Grid.Row="1">
<Image HeightRequest="250"  WidthRequest="250" Source="a0.png"/>
</Grid>
</Grid>

{% endhighlight %}

N> The tab view header can be resized to suit the windows size when the orientation gets changed.

## How to handle the events for custom view with tab view?

When you use the button or similar control with clicked event, it can be handled directly and set to the `SelectedIndex` property to navigate the clicked view.

{% highlight C# %}

private void Button_Clicked(object sender, System.EventArgs e)
{
tabView.SelectedIndex = 0;
}
			
{% endhighlight %}

N> If the click event is not available, it can be achieved by setting the `TapGestureRecognizer` to the custom view.


