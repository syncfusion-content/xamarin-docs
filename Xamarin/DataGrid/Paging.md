---
layout: post
title: Paging | SfDataGrid | Xamarin | Syncfusion
description: Enable paging and use its properties. Usage and advantages of on demand paging. Options to customize the appreance of the SfDataPager.
platform: xamarin
control: SfDataGrid
documentation: ug
---

# Paging in Xamarin DataGrid (SfDataGrid)

The data grid interactively supports manipulation of data using [SfDataPager](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.html# “”) control. This provides built-in options to page data on demand when dealing with large volumes of data. `SfDataPager` can be placed above or below based on the requirement to easily manage data paging.

To use paging functionality in the data grid, add the following namespace to the project:
[Syncfusion.SfDataGrid.XForms.DataPager](http://help.syncfusion.com/cr/xamarin/sfdatagrid# “”)

There are two different modes in paging:

 * NormalPaging: NormalPaging loads the entire data collection to the `SfDataPager`.
 * OnDemandPaging: OnDemandPaging loads data to the current page dynamically in `SfDataPager`.

## Normal paging

The data grid performs paging of data using the `SfDataPager`. To enable paging, follow the procedure:

 * Create a new SfDataPager instance, and bind the data collection to the [SfDataPager.Source](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager.html#Syncfusion_SfDataGrid_XForms_DataPager_SfDataPager_Source) property based on which [SfDataPager.PagedSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager.html#Syncfusion_SfDataGrid_XForms_DataPager_SfDataPager_PagedSource) is created internally. 
 * Bind the `PagedSource` property to the [ItemsSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_ItemsSource) of the data grid. 
 * Set the number of rows to be displayed on a page by setting the [SfDataPager.PageSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager.html#Syncfusion_SfDataGrid_XForms_DataPager_SfDataPager_PageSize) property.
 * Set the number of buttons that should be displayed in view by setting the [SfDataPager.NumericButtonCount](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager.html#Syncfusion_SfDataGrid_XForms_DataPager_SfDataPager_NumericButtonCount) property.

N> The `SfDataPager.PageSize` property should not be assigned with value 0.

The following code example illustrates using `SfDataPager` with the data grid control:

{% tabs %}
{% highlight xaml %}

<local:SamplePage x:Class="SampleBrowser.Paging"
                  xmlns="http://xamarin.com/schemas/2014/forms"
                  xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
                  xmlns:local="clr-namespace:SampleBrowser;assembly=SampleBrowser"
                  xmlns:sfgrid="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms"
                  xmlns:sfPager="clr-namespace:Syncfusion.SfDataGrid.XForms.DataPager;
                                 assembly=Syncfusion.SfDataGrid.XForms">

  <local:SamplePage.BindingContext>
      <local:DataPagerViewModel x:Name="viewModel" />
  </local:SamplePage.BindingContext>
  
  <local:SamplePage.ContentView>
    <Grid> 
      <Grid.RowDefinitions>
        <RowDefinition Height="Auto" />
        <RowDefinition Height="*" />
      </Grid.RowDefinitions>

      <sfPager:SfDataPager x:Name ="dataPager"
                           Grid.Row="0"           
                           PageSize="15" 
                           HeightRequest ="50"
                           NumericButtonCount="20"
                           Source="{Binding Info}">
           
        <sfPager:SfDataPager.HeightRequest>
          <OnPlatform x:TypeArguments="x:Double"
                      iOS="50"
                      Android="50"
                      WinPhone="70"/>
        </sfPager:SfDataPager.HeightRequest>
      </sfPager:SfDataPager>
       
      <sfgrid:SfDataGrid x:Name="dataGrid"
                         Grid.Row="1"
                         AutoGenerateColumns="true"
                         ColumnSizer="Star"
                         SelectionMode="Single"
                         ItemsSource="{Binding PagedSource, Source={x:Reference dataPager}}"  
                         >
      </sfgrid:SfDataGrid>
    </Grid> 
  </local:SamplePage.ContentView>
</local:SamplePage>

{% endhighlight %}
{% highlight c# %}

public partial class MainPage : ContentPage
{
    SfDataGrid sfGrid = new SfDataGrid();
    SfDataPager sfPager = new SfDataPager();
    ViewModel viewModel = new ViewModel();
    public MainPage()
    {
        InitializeComponent();
        sfPager.PageSize = 15;  //Setting the number of rows in a page        
        sfPager.Source = viewModel.Info;  //Setting data source to SfDataPager
        sfGrid.ItemsSource = sfPager.PagedSource;  //Setting ItemsSource to SfDataGrid
        sfGrid.ColumnSizer = ColumnSizer.Star;

        Grid myGrid = new Grid();
        myGrid.HorizontalOptions = LayoutOptions.FillAndExpand;

        myGrid.RowDefinitions = new RowDefinitionCollection
        {
          new RowDefinition { Height = 50 },
          new RowDefinition {},    
        };
        myGrid.Children.Add(sfPager, 0, 0);
        myGrid.Children.Add(sfGrid, 0, 1);
        this.Content = myGrid;
    }
}

{% endhighlight %}
{% endtabs %}

The following screenshot shows the outcome upon execution of the above code:

![DataGrid with paging](SfDataGrid_images/Paging_img1.jpeg)

N> The `SfDataPager` provides scrolling animation while tapping the [FirstPageButton](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.NavigationButtons.html) or [LastPageButton](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.NavigationButtons.html).

## OnDemandPaging	

In normal Paging, data collection is entirely loaded initially to the `SfDataPager`. However, the control also allows loading the data for the current page dynamically by setting the [SfDataPager.UseOnDemandPaging](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager.html#Syncfusion_SfDataGrid_XForms_DataPager_SfDataPager_UseOnDemandPaging) to `true`.

To load current page item dynamically, hook the [OnDemandLoading](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager.html) event. In the `OnDemandLoading` event, use the[LoadDynamicItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager.html#Syncfusion_SfDataGrid_XForms_DataPager_SfDataPager_LoadDynamicItems_System_Int32_System_Collections_IEnumerable_) method to load data for the corresponding page in the `SfDataPager`.

The `OnDemandLoading` event is triggered when the pager moves to the corresponding page. It contains the following event arguments:

 * [StartIndex](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.OnDemandLoadingEventArgs.html#Syncfusion_SfDataGrid_XForms_DataPager_OnDemandLoadingEventArgs_StartIndex): Displays the corresponding page start index.
 * [PageSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.OnDemandLoadingEventArgs.html#Syncfusion_SfDataGrid_XForms_DataPager_OnDemandLoadingEventArgs_PageSize): Displays the number of items to be loaded for that page.

To load data for the DataPager control dynamically, follow the code example:

{% highlight c# %}
private void OnDemandPageLoading(object sender, OnDemandLoadingEventArgs args)
{
   sfDataPager.LoadDynamicItems(args.StartIndex, source.Skip(args.StartIndex).Take(args.PageSize));
}
{% endhighlight %}


N>In on demand paging, you should not assign a value for the `Source` property. Also you have to define an integer value for `PageCount` property to generate the required numeric buttons in the view.

When using `OnDemandPaging`, `SfDataPager.PagedSource` loads only the current page data. Upon navigation to another page, `OnDemandLoading` event is fired which loads another set of data, but maintains the previous page data also. When you navigate to the previous page again, OnDemandLoading event is not fired, and the required data maintained in the cache is loaded. However, for further performance enhancement if you do not want to maintain the previous page data, call [Syncfusion.Data.PagedCollectionView.ResetCache()](https://help.syncfusion.com/cr/xamarin/Syncfusion.Data.PagedCollectionView.html#Syncfusion_Data_PagedCollectionView_ResetCache) in `OnDemandLoading` event. ResetCache method call resets the cache except the current page.

To use ResetCache method, follow the code example:

{% highlight c# %}
private void OnDemandPageLoading(object sender, OnDemandLoadingEventArgs args)
{
  sfDataPager.LoadDynamicItems(args.StartIndex, source.Skip(args.StartIndex).Take(args.PageSize));
  (sfDataPager.PagedSource as PagedCollectionView).ResetCache();
}
{% endhighlight %}

## Numeric button shapes

The `SfDataPager` allows you to change the shape of the buttons using the [SfDataPager.ButtonShape](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager.html#Syncfusion_SfDataGrid_XForms_DataPager_SfDataPager_ButtonShape) property. 

{% tabs %}
{% highlight xaml %}
<sfDataPager:SfDataPager x:Name="sfDataPager"
                         ButtonShape="Rectangle"
                         PageCount="10"
                         PageSize="10"
                         Source="{Binding OrdersInfo}">
</sfDataPager:SfDataPager>
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        this.sfDataPager.ButtonShape = ButtonShape.Rectangle;
    }
}
{% endhighlight %}
{% endtabs %}

![DataGrid with rectangular pager buttons](SfDataGrid_images/RectangularPagerButtons.png)

## Generating numeric buttons

The `SfDataPager` allows you to choose the generation mode of numeric buttons using the [SfDataPager.NumericButtonsGenerateMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager.html#Syncfusion_SfDataGrid_XForms_DataPager_SfDataPager_NumericButtonsGenerateMode) property. The numeric buttons can either be generated in view automatically or by specifying directly in the [SfDataPager.NumericButtonCount](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager.html#Syncfusion_SfDataGrid_XForms_DataPager_SfDataPager_NumericButtonCount) property. 

{% tabs %}
{% highlight xaml %}
<sfDataPager:SfDataPager x:Name="sfDataPager"
                         NumericButtonsGenerateMode="Auto"
                         PageCount="10"
                         PageSize="10"
                         Source="{Binding OrdersInfo}">
</sfDataPager:SfDataPager>
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        dataPager.NumericButtonsGenerateMode = NumericButtonsGenerateMode.Auto;
    }
}
{% endhighlight %}
{% endtabs %}

N> The size of the `SfDataPager` is adjusted automatically based on the available screen size if the view couldn't hold the numeric buttons specified in the `NumericButtonCount` property.

## AppearanceManager

The data grid allows changing the appearance by writing a style class overriding from the `AppearanceManager`, and assigning it to the [SfDataPager.AppearanceManager](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.SfDataPager.html#Syncfusion_SfDataGrid_XForms_DataPager_SfDataPager_AppearanceManager) property.
  
To apply custom style, follow the code example:

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:sfgrid="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms"
             xmlns:local="clr-namespace:SfDataGrid_Sample;assembly=SfDataGrid_Sample"
             xmlns:sfDataPager="clr-namespace:Syncfusion.SfDataGrid.XForms.DataPager;assembly=Syncfusion.SfDataGrid.XForms"
             x:Class="SfDataGrid_Sample.Page1">

  <ContentPage.Resources>
    <ResourceDictionary>
      <local:CustomAppearance x:Key="customAppearance"/>
    </ResourceDictionary>
  </ContentPage.Resources>

  <ContentPage.BindingContext>
    <local:ViewModel x:Name="viewModel" />
  </ContentPage.BindingContext>
  
  <Grid>
    <Grid.RowDefinitions>
      <RowDefinition Height="Auto" />
      <RowDefinition Height="*"/>
    </Grid.RowDefinitions>

    <sfgrid:SfDataGrid x:Name="dataGrid" Grid.Row="1"
                       AutoGenerateColumns="True" />

    <sfDataPager:SfDataPager x:Name="sfDataPager"
                         Grid.Row="0"
                         PageCount="10"
                         PageSize="10"
                         NumericButtonCount="10"
                         AppearanceManager="{StaticResource customAppearance}"
                         Source="{Binding OrdersInfo}">
    </sfDataPager:SfDataPager>
  </Grid>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        this.dataGrid.ItemsSource = sfDataPager.PagedSource;
        // Apply the custom appearance to SfDataPager
        this.sfDataPager.AppearanceManager = new CustomAppearance();
    }
}
{% endhighlight %}
{% endtabs %}

{% highlight c# %}
//Custom Appearance class
public class CustomAppearance: AppearanceManager
{
	public override Color GetNumericButtonSelectionBackgroundColor()
    {
        return Color.FromRgb(255, 0, 0);
    }

    public override Color GetNumericButtonSelectionForegroundColor()
    {
        return Color.FromRgb(0, 255, 0);
    }

	public override Color GetNumericButtonBackgroundColor()
    {
        return Color.FromRgb(0, 0, 255);
    }

	public override Color GetNumericButtonForegroundColor()
    {
        return Color.FromRgb(82, 82, 82);
    }

    public override Color GetNavigationButtonBackgroundColor()
    {
        return Color.FromRgb(34, 34, 34);
    }
    public override Color GetPagerButtonBorderColor()
    {
        return Color.Black;
    }

}
{% endhighlight %}

The following picture shows the customize appearance of data pager:

![DataGrid with customized pager appearance](SfDataGrid_images/datapagerappearence.png)

### Numeric button border color

Based on the requirement, customize the numeric button border color by overriding the [GetPagerButtonBorderColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataPager.AppearanceManager.html#Syncfusion_SfDataGrid_XForms_DataPager_AppearanceManager_GetPagerButtonBorderColor_Syncfusion_SfDataGrid_XForms_DataPager_ButtonShape_) method.

To customize the numeric button border color, follow the code example:

{% tabs %}
{% highlight xaml %}
 <Grid>
    <Grid.RowDefinitions>
      <RowDefinition Height="Auto" />
      <RowDefinition Height="*"/>
    </Grid.RowDefinitions>
    <sfgrid:SfDataGrid x:Name="dataGrid" Grid.Row="1"
                       AutoGenerateColumns="True" />

    <sfDataPager:SfDataPager x:Name="sfDataPager"
                         Grid.Row="0"
                         PageCount="10"
                         PageSize="10"
                         NumericButtonCount="10"
                         AppearanceManager="{StaticResource customAppearance}"
                         Source="{Binding OrdersInfo}">
    </sfDataPager:SfDataPager>
  </Grid>
{% endhighlight %}
{% highlight c# %}
 this.dataGrid.ItemsSource = sfDataPager.PagedSource;
 // Apply the custom appearance to SfDataPager
this.sfDataPager.AppearanceManager = new CustomAppearance();
{% endhighlight %}
{% endtabs %}

{% highlight c# %}
public class CustomAppearance : AppearanceManager
{
    public override Color GetPagerButtonBorderColor()
    {
        return Color.Black;
    }
}
{% endhighlight %}

![DataPager with customized border color](SfDataGrid_images/DataPagerBorderColor.png)

### Limitations
1. UI Filtering is not supported. You can code in application level to filter the data.
2. Data processing operations (Sorting, Grouping) are done only in the current page. 
3. Deleting is not supported. You can code to delete row in application level. 
4. Only the navigated pages are exported when `OnDemandPaging’ is enabled, if the navigated page cache is cleared then the corresponding page will not be exported.

## See also

[How to have different page size in SfDataPager with SfDataGrid when the device is in horizontal and vertical orientation mode](https://www.syncfusion.com/kb/9299)
