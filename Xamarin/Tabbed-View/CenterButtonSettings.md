---
layout: post
title: CenterButton Customization in Xamarin Tabbed View Control | Syncfusion
description: Explore the customization options for the CenterButton in Syncfusion Xamarin Tabbed View (SfTabView) control and more.
control: TabView
documentation: ug
---

# CenterButton Customization in Xamarin Tabbed View (SfTabView)

This section explains how to create and customize the CenterButton in the Xamarin.Forms [`SfTabView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html). To enable the CenterButton, set the [`OverflowMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html#Syncfusion_XForms_TabView_SfTabView_OverflowMode) of the Xamarin.Forms [`SfTabView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html) to [`CenterButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.OverflowMode.html#Syncfusion_XForms_TabView_OverflowMode_CenterButton).

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView OverflowMode="CenterButton"
                   x:Name="tabView">
</tabView:SfTabView>

{% endhighlight %}

{% highlight C# %}

public MainPage()
{
    InitializeComponent();
    SfTabView tabView = new SfTabView();
    tabView.OverflowMode = OverflowMode.CenterButton;
    this.Content = tabView;
}

{% endhighlight %}

{% endtabs %}

## Customizing CenterButtonSettings

You can customize the CenterButton using the properties of the [`CenterButtonSettings`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html#Syncfusion_XForms_TabView_SfTabView_CenterButtonSettings). The properties available for customization include [`BackgroundColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.CenterButtonSettings.html#Syncfusion_XForms_TabView_CenterButtonSettings_BackgroundColor), [`BorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.CenterButtonSettings.html#Syncfusion_XForms_TabView_CenterButtonSettings_BorderColor), [`BorderThickness`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.CenterButtonSettings.html#Syncfusion_XForms_TabView_CenterButtonSettings_BorderThickness), [`Height`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.CenterButtonSettings.html#Syncfusion_XForms_TabView_CenterButtonSettings_Height), [`Title`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.CenterButtonSettings.html#Syncfusion_XForms_TabView_CenterButtonSettings_Title), [`TitleFontAttributes`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.CenterButtonSettings.html#Syncfusion_XForms_TabView_CenterButtonSettings_TitleFontAttributes), [`TitleFontColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.CenterButtonSettings.html#Syncfusion_XForms_TabView_CenterButtonSettings_TitleFontColor), [`TitleFontSize`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.CenterButtonSettings.html#Syncfusion_XForms_TabView_CenterButtonSettings_TitleFontSize), and [`Width`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.CenterButtonSettings.html#Syncfusion_XForms_TabView_CenterButtonSettings_Width).

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView.CenterButtonSettings>
    <tabView:CenterButtonSettings Height="80" Width="100"
                                  Title="Center Button" TitleFontColor="Green"
                                  TitleFontAttributes="Bold">
    </tabView:CenterButtonSettings>
</tabView:SfTabView.CenterButtonSettings>

{% endhighlight %}

{% highlight C# %}

public MainPage()
{
    InitializeComponent();
    var centerButton = tabView.CenterButtonSettings;
    centerButton.Height = 80;
    centerButton.Width = 100;
    centerButton.Title = "Center Button";
    centerButton.TitleFontAttributes = FontAttributes.Bold;
    centerButton.TitleFontColor = Color.Green;
}

{% endhighlight %}

{% endtabs %}

## CenterButtonTapped Event

When the [`CenterButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.OverflowMode.html#Syncfusion_XForms_TabView_OverflowMode_CenterButton) is tapped, the [`CenterButtonTapped`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html#Syncfusion_XForms_TabView_SfTabView_CenterButtonTapped) event is triggered. This event can be used to display an alert message.

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView CenterButtonTapped="TabView_CenterButtonTapped">
</tabView:SfTabView>

{% endhighlight %}

{% highlight C# %}

public MainPage()
{
    InitializeComponent();
    tabView.CenterButtonTapped += TabView_CenterButtonTapped;
}

private void TabView_CenterButtonTapped(object sender, EventArgs e)
{
    DisplayAlert("Message", "CenterButton Clicked", "Ok");
}

{% endhighlight %}

{% endtabs %}

## Custom CenterButton

If the built-in view does not meet your needs, you can override it by adding custom views to the [`CenterButtonView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html#Syncfusion_XForms_TabView_SfTabView_CenterButtonView). The [`CenterButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.OverflowMode.html#Syncfusion_XForms_TabView_OverflowMode_CenterButton) view can be customized by adding images, labels, or buttons within the [`CenterButtonView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.SfTabView.html#Syncfusion_XForms_TabView_SfTabView_CenterButtonView). Refer to the following code example for guidance on customizing the [`CenterButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TabView.OverflowMode.html#Syncfusion_XForms_TabView_OverflowMode_CenterButton).

{% tabs %}

{% highlight xaml %}

<tabView:SfTabView.CenterButtonView>
    <Grid>
        <Image Source="Compose.png"
               Aspect="AspectFill"
               VerticalOptions="CenterAndExpand"
               HorizontalOptions="CenterAndExpand">
            <Image.GestureRecognizers>
                <TapGestureRecognizer Tapped="TapGestureRecognizer_Tapped" />
            </Image.GestureRecognizers>
        </Image>
    </Grid>
</tabView:SfTabView.CenterButtonView>

{% endhighlight %}

{% highlight C# %}

public MainPage()
{
    InitializeComponent();
                -----
                -----
    Grid customCenterButtonGrid = new Grid();
    Image image = new Image();
    TapGestureRecognizer tapGestureRecognizer = new TapGestureRecognizer();
    image.Source = ImageSource.FromFile("Compose.png");
    image.Aspect = Aspect.AspectFill;
    image.VerticalOptions = LayoutOptions.CenterAndExpand;
    image.HorizontalOptions = LayoutOptions.CenterAndExpand;
    tapGestureRecognizer.Tapped += TapGestureRecognizer_Tapped; ;
    image.GestureRecognizers.Add(tapGestureRecognizer);
    customCenterButtonGrid.Children.Add(image);
    tabView.CenterButtonView = customCenterButtonGrid;
                -----
                -----
}

private void TapGestureRecognizer_Tapped(object sender, EventArgs e)
{
    DisplayAlert("Message", "CenterButton Clicked", "Ok");
}

{% endhighlight %}

{% endtabs %}

![TabViewImage](images/Center-Button/Center_Button_Customization.png)

You can find an example in this [sample](https://github.com/SyncfusionExamples/center-button-tabview).
