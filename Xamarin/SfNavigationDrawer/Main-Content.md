---
layout: post
title: Various features of Syncfusion NavigationDrawer control for Xamarin.Forms
description: Learn how to set content view, drawer content view, footer view, header view, drawer size in NavigationDrawer.
platform: Xamarin
control: NavigationDrawer
documentation: ug
---


# Main Content

Main content of NavigationDrawer is always visible and it can be set using `ContentView` property. In the following code example, ContentView is switched when selection changes in ListView.

{% tabs %}

{% highlight xaml %}

	<navigationdrawer:SfNavigationDrawer x:Name="navigationDrawer" DrawerHeaderHeight="160">
        <navigationdrawer:SfNavigationDrawer.ContentView>
            <Grid x:Name="mainContentView" BackgroundColor="White">
                <Grid.RowDefinitions>
                    <RowDefinition Height="auto"/>
                    <RowDefinition/>
                </Grid.RowDefinitions>
                <StackLayout BackgroundColor="#1aa1d6" Orientation="Horizontal">
                    <Button x:Name="hamburgerButton" HeightRequest="50" WidthRequest="50" HorizontalOptions="Start" FontSize="20" BackgroundColor="#1aa1d6" Clicked="hamburgerButton_Clicked"/>
                    <Label x:Name="headerLabel" HeightRequest="50" HorizontalTextAlignment="Center" VerticalTextAlignment="Center" Text="Home" FontSize="16" TextColor="White" BackgroundColor="#1aa1d6"/>
                </StackLayout>
                <Label Grid.Row="1" x:Name="contentLabel" VerticalOptions="Center" HorizontalOptions="Center" Text="Content View" FontSize="14" TextColor="Black"/>
            </Grid>
        </navigationdrawer:SfNavigationDrawer.ContentView>
        <navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
            <Grid BackgroundColor="#1aa1d6">
                <Grid.RowDefinitions>
                    <RowDefinition Height="120"/>
                    <RowDefinition Height="40"/>
                </Grid.RowDefinitions>
                <Image Source="user.png" HeightRequest="110" Margin="0,10,0,0" BackgroundColor="#1aa1d6" VerticalOptions="Center" HorizontalOptions="Center"/>
                <Label Text="James Pollock" Grid.Row="1" HorizontalTextAlignment="Center" HorizontalOptions="Center" FontSize="20" TextColor="White"/>
            </Grid>
        </navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
        <navigationdrawer:SfNavigationDrawer.DrawerContentView>
            <ListView x:Name="listView" ItemSelected="listView_ItemSelected">
                <ListView.ItemTemplate>
                    <DataTemplate>
                        <ViewCell>
                            <StackLayout HeightRequest="40">
                                <Label Margin="10,7,0,0" Text="{Binding}" FontSize="16"/>
                            </StackLayout>
                        </ViewCell>
                    </DataTemplate>
                </ListView.ItemTemplate>
            </ListView>
        </navigationdrawer:SfNavigationDrawer.DrawerContentView>
    </navigationdrawer:SfNavigationDrawer>


{% endhighlight %}

{% highlight c# %}

public MainPage()

        {
            InitializeComponent();
            navigationDrawer.DrawerWidth = 200;
            hamburgerButton.Image = (FileImageSource)ImageSource.FromFile("hamburger_icon.png");
            List<string> list = new List<string>();
            list.Add("Home");
            list.Add("Profile");
            list.Add("Inbox");
            list.Add("Out box");
            list.Add("Sent");
            list.Add("Draft");
            listView.ItemsSource = list;            
        }

        void hamburgerButton_Clicked(object sender, EventArgs e)
        {
            navigationDrawer.ToggleDrawer();
        }

        private void listView_ItemSelected(object sender, SelectedItemChangedEventArgs e)
        {
            if (e.SelectedItem.ToString() == "Home")
                contentLabel.Text = "Home";
            else if (e.SelectedItem.ToString() == "Profile")
                contentLabel.Text = "Profile";
            else if (e.SelectedItem.ToString() == "Inbox")
                contentLabel.Text = "Inbox";
            else if (e.SelectedItem.ToString() == "Out box")
                contentLabel.Text = "Out box";
            else if (e.SelectedItem.ToString() == "Sent")
                contentLabel.Text = "Sent";
            else if (e.SelectedItem.ToString() == "Draft")
                contentLabel.Text = "The folder is empty";
            navigationDrawer.ToggleDrawer();
        }

  
{% endhighlight %}

{% endtabs %}

![](Images/MainContent.png)