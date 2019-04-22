---
layout: post
title: CenterButtonSettings in Syncfusion TabView control for Xamarin.Forms
description: Learn how to create and customize CenterButton in TabView
platform: Xamarin
control: TabView
documentation: ug
---

# CenterButtonSettings

This section explains how to create and customize The Xamarin.Forms SfTabView CenterButton. To enable CenterButton, set the `OverFlowMode` of Xamarin.Forms SfTabView to `CenterButton`.

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

## Customize CenterButtonSettings

We can customize the CenterButton using the properties of `CenterButtonSetting`. The following properties are used to customize the view of CenterButton `BackgroundColor`, `BorderColor`, `BorderThickness`, `Height`, `Title`, `TitleFontAttributes`, `TitleFontColor`, `TitleFontSize`, `Width`.

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

## CenterButtonTapped event

When `CenterButton` is tapped, the `CenterButtonTapped` event occurs. Using this event we can set alert message.

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

When built-in view is not needed, it can be overridden by adding custom views to the CenterButtonView. The CenterButton view can be customized by adding images, labels, buttons inside the CenterButtonView. Refer the following code sample to know about customizing the view of CenterButton.

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

Please find the sample from the following [Sample](http://www.syncfusion.com/downloads/support/directtrac/general/ze/TabView_CenterButton1561492158.zip).