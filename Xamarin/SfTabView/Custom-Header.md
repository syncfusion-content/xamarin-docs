---
layout: post
title:  Custom Header
description: Custom Header in Syncfusion TabView control for Xamarin.Forms platform
platform: Xamarin.Forms
control: TabView
documentation: ug
---

# Custom Header 

When the built-in view is not needed, it can be overridden by adding the custom view to the header region in tabs. 

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

## How to handle the events for custom view with tab view?

When you use the button or similar control with clicked event, it can be handled directly and set to the `SelectedIndex` property to navigate the clicked view.

{% highlight C# %}

private void Button_Clicked(object sender, System.EventArgs e)
{
tabView.SelectedIndex = 0;
}
			
{% endhighlight %}

N> If the click event is not available, it can be achieved by setting the `TapGestureRecognizer` to the custom view.


