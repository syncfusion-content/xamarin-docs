---
layout: post
title: How to | SfPopupLayout |Xamarin | Syncfusion
description: Explains how to achieve various requirements with SfPopupLayout
platform: Xamarin
control: SfPopupLayout
documentation: ug
--- 
# How to 

## Hide the header in the SfPopupLayout

The SfPopupLayout allows hiding the header by using the [SfPopupLayout.PopupView.ShowHeader](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~ShowHeader.html) property. The default value of this property is `true`.

To hide the header in the SfPopupLayout, follow the code example.

{% highlight c# %}
//MainPage.cs

public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.PopupView.ShowHeader = false;
    ....
}
{% endhighlight %}

Executing the above codes renders the following output in iOS, Android and Windows Phone devices respectively.

![](PopupLayout_images/ShowHeader_False.png)

## Hide the footer in SfPopupLayout

The SfPopupLayout allows hiding the footer by using the [SfPopupLayout.PopupView.ShowFooter](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~ShowFooter.html) property. The default value of this property is `true`.

To hide the footer in the SfPopupLayout, follow the code example.

{% highlight c# %}
//MainPage.cs

public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.PopupView.ShowFooter = false;
    ....
}
{% endhighlight %}

Executing the above codes renders the following output in iOS, Android and Windows Phone devices respectively.

![](PopupLayout_images/ShowFooter_False.png)

## Hide the Close icon in the SfPopupLayout 

The SfPopupLayout allows hiding the Close icon by using the [SfPopupLayout.PopupView.ShowCloseButton](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~ShowCloseButton.html) property. The default value of this property is `true`.

To hide the Close icon in the SfPopupLayout, follow the code example.

{% highlight c# %}
//MainPage.cs

public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.PopupView.ShowCloseButton = false;
    ....
}
{% endhighlight %}

Executing the above codes renders the following output in iOS, Android and Windows Phone devices respectively.

![](PopupLayout_images/ShowClosebutton_False.png)

## Load SfPopupLayout in GridTappedEvent of SfDataGrid

SfPopupLayout allows you to open popup in the grid tapped event of SfDataGrid.

Refer the below code example to show the popup in Grid tapped event.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:PopupSample"
             x:Class="PopupSample.MainPage"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms"
             xmlns:sfDataGrid="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms" >
    <ContentPage.BindingContext>
        <local:ViewModel x:Name="viewModel" />
    </ContentPage.BindingContext>
    
    <sfPopup:SfPopupLayout x:Name="popupLayout" >
        <sfPopup:SfPopupLayout.Content>
            <sfDataGrid:SfDataGrid x:Name="dataGrid"
                               ItemsSource="{Binding OrdersInfo}">
            </sfDataGrid:SfDataGrid>
       </sfPopup:SfPopupLayout.Content>
    </sfPopup:SfPopupLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using Syncfusion.XForms.PopupLayout;

namespace GettingStarted
{
    public partial class MainPage : ContentPage
    {

        SfDataGrid dataGrid;
        ViewModel viewModel;
        SfPopupLayout popupLayout;
        public MainPage()
        {
            InitializeComponent();
            dataGrid = new SfDataGrid();
            viewModel = new ViewModel();
            dataGrid.ItemsSource = viewModel.OrdersInfo;
            popupLayout = new SfPopupLayout();
            popupLayout.Content = dataGrid;
            dataGrid.GridTapped += DataGrid_GridTapped;
            this.Content = popupLayout;
        }

        private async void DataGrid_GridTapped(object sender, Syncfusion.SfDataGrid.XForms.GridTappedEventArgs e)
        {
            await Task.Delay(100);

            // Popup is opened at the Grid tapped event
            popupLayout.Show();
        }
    }
}
{% endhighlight %}
{% endtabs %}

Executing the above codes renders the following output in an android device.

![](PopupLayout_images/DataGridWithPopup.png)

## Load SfPopupLayout in Prism

Refer the below code in which SfPopupLayout is shown if we navigate to next and previous pages using button click.

{% highlight xaml %}

// MainPage.xaml

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:prism="clr-namespace:Prism.Mvvm;assembly=Prism.Forms"
             prism:ViewModelLocator.AutowireViewModel="True"
             x:Class="PrismUnitySfDataGrid.Views.MainPage"
             Title="MainPage"
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">

    <ContentPage.Content>
        <StackLayout>
            <Button Text="GO TO NEXT PAGE" VerticalOptions="Center" HorizontalOptions="Center" Clicked="Button_Clicked" />
        </StackLayout>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

// MainPage.cs

public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
    }

    private void Button_Clicked(object sender, System.EventArgs e)
    {
        (this.BindingContext as MainPageViewModel).navigation_service.NavigateAsync("SecondPage");
    }
}
{% endhighlight %}

{% highlight xaml %}

// SecondPage

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:PrismUnitySfDataGrid.ViewModels"
             xmlns:prism="clr-namespace:Prism.Mvvm;assembly=Prism.Forms"
             prism:ViewModelLocator.AutowireViewModel="True"
             x:Class="PrismUnitySfDataGrid.Views.SecondPage">

    <ContentPage.Content>
        <StackLayout>
            <Button Text="GO TO PREVIOUS PAGE" VerticalOptions="Center" HorizontalOptions="Center" Clicked="Button_Clicked" />
        </StackLayout>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

// SecondPage.cs

public partial class SecondPage : ContentPage
{
    public SecondPage()
    {
        InitializeComponent();
    }

    private void Button_Clicked(object sender, System.EventArgs e)
    {
        (this.BindingContext as SecondPageViewModel).navigation_service.NavigateAsync("MainPage");
    }
}
{% endhighlight %}

{% highlight c# %}

// App.cs

public partial class App : PrismApplication
{
    public App(IPlatformInitializer initializer = null) : base(initializer) { }

    protected override void OnInitialized()
    {
        InitializeComponent();
        NavigationService.NavigateAsync("NavigationPage/MainPage");
    }

    protected override void RegisterTypes()
    {
        Container.RegisterTypeForNavigation<NavigationPage>();
        Container.RegisterTypeForNavigation<MainPage>();
        Container.RegisterTypeForNavigation<SecondPage>();
    }
}
{% endhighlight %}

{% highlight c# %}

// MainPageViewModel.cs

public class MainPageViewModel : INavigationAware
{
    private SfPopupLayout popupLayout;
    private DataTemplate templateView;
    private Button popupContent;
    public INavigationService navigation_service;

    public MainPageViewModel(INavigationService navigationService)
    {
        navigation_service = navigationService;
        popupLayout = new SfPopupLayout();
        // Set the required content template
        templateView = new DataTemplate(() =>
        {
            popupContent = new Button();
            popupContent.Text = "Click to change background";
            popupContent.BackgroundColor = Color.Yellow;
            popupContent.Clicked += (s, e) =>
            {
                popupContent.BackgroundColor = Color.Green;
            };
            return popupContent;
        });
        popupLayout.PopupView.ContentTemplate = templateView;
    }

    public void OnNavigatedFrom(NavigationParameters parameters)
    {
    }

    public void OnNavigatedTo(NavigationParameters parameters)
    {
        if (App.Current.MainPage != null)
        {
            popupLayout.Show(((App.Current.MainPage as NavigationPage).CurrentPage as ContentPage).Content);
        }
    }

    public void OnNavigatingTo(NavigationParameters parameters)
    {
    }
}
{% endhighlight %}

{% highlight c# %}

// SecondPageViewModel.cs

public class SecondPageViewModel : INavigationAware
{
    private SfPopupLayout popupLayout;
    private DataTemplate templateView;
    private Button popupContent;
    public INavigationService navigation_service;

    public SecondPageViewModel(INavigationService navigationService)
    {
        navigation_service = navigationService;
        popupLayout = new SfPopupLayout();
        // Set the required content template
        templateView = new DataTemplate(() =>
        {
            popupContent = new Button();
            popupContent.Text = "Click to change background";
            popupContent.BackgroundColor = Color.Yellow;
            popupContent.Clicked += (s, e) =>
            {
                popupContent.BackgroundColor = Color.Green;
            };
            return popupContent;
        });
        popupLayout.PopupView.ContentTemplate = templateView;
    }

    public void OnNavigatedFrom(NavigationParameters parameters)
    {
    }

    public void OnNavigatedTo(NavigationParameters parameters)
    {
        if (App.Current.MainPage != null)
        {
            popupLayout.Show(((App.Current.MainPage as NavigationPage).CurrentPage as ContentPage).Content);
        }
    }

    public void OnNavigatingTo(NavigationParameters parameters)
    {
    }
}
{% endhighlight %}

## Load SfPopupLayout in ItemTapped event of SfListView

SfPopupLayout allows you to open it in the ItemTapped event of SfListView.

Refer the below code example to show the popup in Item tapped event.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ListViewWithPopup"
             x:Class="ListViewWithPopup.MainPage"
             xmlns:sfListview="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"     
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">

     <ContentPage.BindingContext>
        <local:ContactsViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>
    
    <sfPopup:SfPopupLayout x:Name="popupLayout">
        <sfPopup:SfPopupLayout.Content>
            <sfListview:SfListView  x:Name="listView"  ItemSpacing="5" 
                          ItemsSource="{Binding contactsInfo}" >
                <sfListview:SfListView.ItemTemplate>
                    <DataTemplate>
                        <ViewCell>
                            <ViewCell.View>
                                <Grid x:Name="grid" RowSpacing="1">
                                    <Grid.RowDefinitions>
                                        <RowDefinition Height="*" />
                                    </Grid.RowDefinitions>
                                    <Grid.ColumnDefinitions>
                                        <ColumnDefinition Width="50" />
                                        <ColumnDefinition Width="200" />
                                        <ColumnDefinition Width="50" />
                                    </Grid.ColumnDefinitions>

                                    <Image Source="{Binding ContactImage}"
                                       VerticalOptions="Center"
                                       HorizontalOptions="Center"
                                       HeightRequest="50"/>

                                    <Label Grid.Column="1"
                                        HorizontalTextAlignment="Center"
                                        LineBreakMode="NoWrap"
                                        Text="{Binding ContactName}" 
                                        FontSize="Medium" />

                                    <Image Grid.Column="2" 
                                       Source="{Binding ContactType}"
                                       VerticalOptions="End"
                                       HorizontalOptions="End"
                                       HeightRequest="50"/>
                                    
                                </Grid>
                            </ViewCell.View>
                        </ViewCell>
                    </DataTemplate>
                </sfListview:SfListView.ItemTemplate>
            </sfListview:SfListView>
        </sfPopup:SfPopupLayout.Content>
    </sfPopup:SfPopupLayout> 
 </ContentPage>
{% endhighlight %}

{% highlight c# %}

namespace ListViewWithPopup
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            popupLayout.PopupView.ContentTemplate = new DataTemplate(() =>
            {
                Label popupContent = new Label();
                popupContent.Text = "A pop-up is a graphical user interface display area that suddenly appears in the foreground of the visual interface. Pop-up can be initiated by single or double tap or can simply be timed to occur. A pop-up window should be smaller than the background window or interface; otherwise, its a replacement interface.";
                return popupContent;
            });
            listView.ItemTapped += ListView_ItemTapped;
        }

        private void ListView_ItemTapped(object sender, Syncfusion.ListView.XForms.ItemTappedEventArgs e)
        {
            popupLayout.Show();
        }
    }
}
{% endhighlight %}
{% endtabs %}

Executing the above codes renders the following output in an android device.

![](PopupLayout_images/PopupInListView.png)

## Show ListView as a popup

SfPopupLayout allows you to load SfListView as a content of the popup. You have to set `WidthRequest` and `HeightRequest` property for loading SfListView in SfPopupLayout. 

Refer the below code example to load the SfListView in SfPopupLayout.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             x:Class="ListViewWithPopup.MainPage"           
             xmlns:sfPopup="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">
    <sfPopup:SfPopupLayout x:Name="popupLayout">
        <sfPopup:SfPopupLayout.Content>
            <StackLayout x:Name="mainLayout">
                <Button x:Name="clickToShowPopup" Text="CLICK TO SHOW POPUP" VerticalOptions="Start" HorizontalOptions="FillAndExpand"    />
            </StackLayout>
        </sfPopup:SfPopupLayout.Content>
    </sfPopup:SfPopupLayout> 
</ContentPage>
{% endhighlight %}

{% highlight c# %}

namespace ListViewWithPopup
{
    public partial class MainPage : ContentPage
    {
       private ListViewPage listView;
       public MainPage()
        {
            InitializeComponent();
            listView = new ListViewPage();
            popupLayout.PopupView.ContentTemplate = new DataTemplate(() =>
            {
                return listView.Content;
            });
            clickToShowPopup.Clicked += ClickToShowPopup_Clicked;
         }

        private void ClickToShowPopup_Clicked(object sender, EventArgs e)
        {
            popupLayout.Show();
        }
    }
}
{% endhighlight %}
{% endtabs %}

Executing the above codes renders the following output in an android device.

![](PopupLayout_images/ListViewInPopup.png)