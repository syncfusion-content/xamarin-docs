---
layout: post
title: ItemTapped event for Syncfusion Essential SfTabView.
description: Learn how to perform an operation while tapping an item, and also about Events in Behavior Commands in SfTabView Xamarin.Forms.
platform: Xamarin.Forms
control: TabView
documentation: ug
---

# How to perform an operation when tapping an item in SfTabView

Whenever the TabItem is tapped, the `TabItemTapped` event will occur. Using this event, you can Modify the selected Tab Item properties.

{% tabs %}

{% highlight xaml %}

<ContentPage.Content>
    <StackLayout>
        <tabView:SfTabView x:Name="tabView" VerticalOptions="FillAndExpand"
                           TabItemTapped="TabView_TabItemTapped"
                           VisibleHeaderCount="3">
            <tabView:SfTabItem Title="Call">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="LightGreen" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Favorites">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="LightBlue"/>
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
            <tabView:SfTabItem Title="Contacts">
                <tabView:SfTabItem.Content>
                    <Grid BackgroundColor="LightGreen" />
                </tabView:SfTabItem.Content>
            </tabView:SfTabItem>
        </tabView:SfTabView>
    </StackLayout>
</ContentPage.Content>

{% endhighlight %}

{% highlight C# %}

public MainPage()
{
    InitializeComponent();
    tabView.TabItemTapped += TabView_TabItemTapped;
}

private void TabView_TabItemTapped(object sender, Syncfusion.XForms.TabView.TabItemTappedEventArgs e)
{
    DisplayAlert("TabViewItemTapped", e.TabItem.Title + " Item Tapped", "Ok");
}

{% endhighlight %}

{% endtabs %}

Note: Please refer to this [Link](https://www.syncfusion.com/kb/11562/how-to-turn-events-into-commands-with-behaviors-in-xamarin-forms-tabbed-view) for how to turn Events into Commands with Behaviors in Xamarin.Forms Tabbed View.