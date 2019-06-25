---
layout: post
title: ItemTapped event for Syncfusion Essential SfTabView.
description: ItemTapped event in TabView control for Xamarin.Forms platform
platform: Xamarin.Forms
control: TabView
documentation: ug
---

# TabItemTapped

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