---
layout: post
title: How to | SfPopupLayout |Xamarin | Syncfusion
description: How to topics in SfPopupLayout
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

## Loading SfPopupLayout in GridTappedEvent of SfDataGrid

SfPopupLayout allows you to open it in the GridTapped event of SfDataGrid.

Refer the below code example to show the popup in Grid tapped event.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:PopupSample"
             x:Class="PopupSample.MainPage"
              Padding="0,40,0,0"
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

## Loading SfPopupLayout in Prism

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

## Loading SfPopupLayout in ItemTapped event of SfListView

SfPopupLayout allows you to open it in the ItemTapped event of SfListView.

Refer the below code example to show the popup in Item tapped event.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ListViewWithPopup"
             x:Class="ListViewWithPopup.MainPage"
             xmlns:listView="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"     
             xmlns:popuplayout="clr-namespace:Syncfusion.XForms.PopupLayout;assembly=Syncfusion.SfPopupLayout.XForms">

    <ContentPage.BindingContext>
        <local:ContactsViewModel />
    </ContentPage.BindingContext>
    
    <ContentPage.Content>
      <popuplayout:SfPopupLayout x:Name="popupLayout">
        <popuplayout:SfPopupLayout.Content>-->
          <listView:SfListView  x:Name="listView" 
                                ItemSize="70"
                                ItemsSource="{Binding contactsInfo}" 
                                ItemSpacing="0,0,5,0" >
            <listView:SfListView.ItemTemplate>
                <DataTemplate>
                    <ViewCell>
                        <ViewCell.View>
                            <Grid x:Name="grid" RowSpacing="1">
                                <Grid.RowDefinitions>
                                    <RowDefinition Height="*" />
                                    <RowDefinition Height="1" />
                                </Grid.RowDefinitions>
                                   <Grid.ColumnDefinitions>
                                        <ColumnDefinition Width="100" />
                                        <ColumnDefinition Width="200" />
                                        <ColumnDefinition Width="70" />
                                    </Grid.ColumnDefinitions>

                                    <Image Source="{Binding ContactImage}"
                                           VerticalOptions="Center"
                                           HorizontalOptions="Center"
                                           HeightRequest="50"/>

                                    <Grid Grid.Column="1"
                                          RowSpacing="1"
                                          Padding="10,0,0,0"
                                          VerticalOptions="Center">
                                        <Grid.RowDefinitions>
                                            <RowDefinition Height="*" />
                                            <RowDefinition Height="*" />
                                        </Grid.RowDefinitions>

                                        <Label LineBreakMode="NoWrap"
                                               TextColor="#474747"
                                               Text="{Binding ContactName}">
                                            <Label.FontSize>
                                                <OnPlatform x:TypeArguments="x:Double">
                                                    <OnPlatform.WinPhone>
                                                        <OnIdiom x:TypeArguments="x:Double" Phone="18" Tablet="20" />
                                                    </OnPlatform.WinPhone>
                                                    <OnPlatform.Android>
                                                        <OnIdiom x:TypeArguments="x:Double"
                                                                 Phone="16"
                                                                 Tablet="18" />
                                                    </OnPlatform.Android>
                                                    <OnPlatform.iOS>
                                                        <OnIdiom x:TypeArguments="x:Double"
                                                                 Phone="16"
                                                                 Tablet="18" />
                                                    </OnPlatform.iOS>
                                                </OnPlatform>
                                            </Label.FontSize>
                                        </Label>
                                        <Label Grid.Row="1"
                                               Grid.Column="0"
                                               TextColor="#474747"
                                               LineBreakMode="NoWrap"
                                               Text="{Binding ContactNumber}">
                                            <Label.FontSize>
                                                <OnPlatform x:TypeArguments="x:Double">
                                                    <OnPlatform.WinPhone>
                                                        <OnIdiom x:TypeArguments="x:Double" Phone="12" Tablet="12" />
                                                    </OnPlatform.WinPhone>
                                                    <OnPlatform.Android>
                                                        <OnIdiom x:TypeArguments="x:Double"
                                                                         Phone="12"
                                                                         Tablet="14" />
                                                    </OnPlatform.Android>
                                                    <OnPlatform.iOS>
                                                        <OnIdiom x:TypeArguments="x:Double"
                                                                         Phone="12"
                                                                         Tablet="14" />
                                                    </OnPlatform.iOS>
                                                </OnPlatform>
                                            </Label.FontSize>
                                        </Label>
                                    </Grid>
                                    
                                    <Grid Grid.Row="0"
                                          Grid.Column="2"
                                          RowSpacing="0"
                                          HorizontalOptions="End"
                                          Padding="0,10,10,0">
                                        <Image
                                             VerticalOptions="Center"
                                             HorizontalOptions="Center"
                                             HeightRequest="50"
                                             Source="{Binding ContactType}">
                                           
                                        </Image>
                                    </Grid>
                               </Grid>
                        </ViewCell.View>
                    </ViewCell>
                </DataTemplate>
            </listView:SfListView.ItemTemplate>
        </listView:SfListView>
     </popuplayout:SfPopupLayout.Content>
  </popuplayout:SfPopupLayout>-->
 </ContentPage.Content>
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
