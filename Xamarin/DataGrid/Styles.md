---
layout: post
title: Styles in Xamarin DataGrid control | Syncfusion
description: Learn here all about Styles support in Syncfusion Xamarin DataGrid (SfDataGrid) control, its elements and more.
platform: xamarin
control: SfDataGrid
documentation: UG
---

# Styles in Xamarin DataGrid (SfDataGrid)

The data grid applies style for all of its elements by setting desired values to the style properties in [SfDataGrid.GridStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_GridStyle) or writing a Style class overriding from [DataGridStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html), and assigning it to the [SfDataGrid.GridStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_GridStyle) property.

To apply style in xaml, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid" ItemsSource="{Binding OrdersInfo}" >
    <syncfusion:SfDataGrid.GridStyle>
        <syncfusion:DefaultStyle HeaderBackgroundColor="{Binding BackgroundColor}" HeaderForegroundColor="White"
                                 RowBackgroundColor="Black" RowForegroundColor="White"
                                 SelectionBackgroundColor="LightSkyBlue" SelectionForegroundColor="White"
                                 CaptionSummaryRowBackgroundColor="Black" CaptionSummaryRowForegroundColor="White"
                                 GridCellBorderColor="{Binding BorderColor}" LoadMoreViewBackgroundColor="Gray"
                                 LoadMoreViewForegroundColor="Black" AlternatingRowColor="Yellow"/>
    </syncfusion:SfDataGrid.GridStyle>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
    public Mainpage()
    {
        InitializeComponent();
        this.dataGrid.GridStyle.HeaderBackgroundColor = Color.FromRgb(15, 15, 15);
        this.dataGrid.GridStyle.HeaderForegroundColor = Color.FromRgb(255, 255, 255);
        this.dataGrid.GridStyle.RowBackgroundColor = Color.FromRgb(43, 43, 43);
        this.dataGrid.GridStyle.RowForegroundColor = Color.FromRgb(255, 255, 255);
        this.dataGrid.GridStyle.SelectionBackgroundColor = Color.FromRgb(42, 159, 214);
        this.dataGrid.GridStyle.SelectionForegroundColor = Color.FromRgb(255, 255, 255);
        this.dataGrid.GridStyle.CaptionSummaryRowBackgroundColor = Color.FromRgb(02, 02, 02);
        this.dataGrid.GridStyle.CaptionSummaryRowForegroundColor = Color.FromRgb(255, 255, 255);
        this.dataGrid.GridStyle.GridCellBorderColor = Color.FromRgb(81, 83, 82);
        this.dataGrid.GridStyle.LoadMoreViewBackgroundColor = Color.FromRgb(242, 242, 242);
        this.dataGrid.GridStyle.LoadMoreViewForegroundColor = Color.FromRgb(34, 31, 31);
        this.dataGrid.GridStyle.AlternatingRowColor = Color.Yellow;
    }
}
{% endhighlight %}
{% endtabs %}

To apply custom style, follow the code example:

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms"
             xmlns:local ="clr-namespace:DataGridSample;assembly=DataGridSample"
             x:Class="DataGridSample.Sample">

    <ContentPage.Resources>
        <ResourceDictionary>
            <local:Dark x:Key="dark" />
        </ResourceDictionary>
    </ContentPage.Resources>

    <syncfusion:SfDataGrid x:Name="dataGrid"
                GridStyle="{StaticResource dark}"
                ItemsSource="{Binding OrdersInfo}" />
</ContentPage> 
{% endhighlight %}
{% highlight c# %}
//Apply custom style to SfDataGrid from code
SfDataGrid dataGrid = new SfDataGrid();
dataGrid.GridStyle = new Dark ();
{% endhighlight %}
{% endtabs %}

{% highlight c# %}
//Custom style class
public class Dark : DataGridStyle
{
    public Dark ()
    {
    }

    public override Color GetHeaderBackgroundColor()
    {
        return Color.FromRgb (15, 15, 15);
    }

    public override Color GetHeaderForegroundColor()
    {
        return Color.FromRgb (255, 255, 255);
    }

    public override Color GetRecordBackgroundColor ()
    {
        return Color.FromRgb (43, 43, 43);
    }

    public override Color GetRecordForegroundColor ()
    {
        return Color.FromRgb (255, 255, 255);
    }

    public override Color GetSelectionBackgroundColor ()
    {
        return Color.FromRgb (42, 159, 214);
    }

    public override Color GetSelectionForegroundColor ()
    {
        return Color.FromRgb (255, 255, 255);
    }

    public override Color GetCaptionSummaryRowBackgroundColor ()
    {
        return Color.FromRgb (02, 02, 02);
    }

    public override Color GetCaptionSummaryRowForeGroundColor ()
    {
        return Color.FromRgb (255, 255, 255);
    }

    public override Color GetBorderColor ()
    {
        return Color.FromRgb (81, 83, 82);
    }

    public override Color GetLoadMoreViewBackgroundColor ()
    {
        return Color.FromRgb(242, 242, 242);
    }

    public override Color GetLoadMoreViewForegroundColor ()
    {
        return Color.FromRgb(34, 31, 31);
    }
    
    public override Color GetAlternatingRowBackgroundColor()
    {
        return Color.Yellow;
    }
} 
{% endhighlight %}

The following picture shows the grid loaded in a different style:

![DataGrdi with style customized](SfDataGrid_images/Style.png)

N> Xamarin.Forms.Style which has specified target type, that will not be applied to the internal components used in the SfDataGrid.

## Set datagrid style from application resources

You can write custom style for the properties in [SfDataGrid.GridStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_GridStyle) class using application resource. To consume the custom style, set style target type as `DataGrid`, setter property as `GridStyle` and use custom style as static resource for the setter value. By consuming custom style like this will commonly change the `GridStyle` of all the DataGrid used in the application.

To apply custom style from application resources, follow the code example:

{% highlight xaml %}
<Application.Resources>
    <ResourceDictionary>
        <!--Global Styles-->
        <Color x:Key="NavigationPrimary">#2196F3</Color>
        <Style TargetType="NavigationPage">
            <Setter Property="BarBackgroundColor" Value="{StaticResource NavigationPrimary}" />
            <Setter Property="BarTextColor" Value="White" />
        </Style>

        <syncfusion:DefaultStyle x:Key="customStyle" 
                                 CurrentCellBorderColor="Green" 
                                 CaptionSummaryRowForegroundColor="BlueViolet"
                                 AlternatingRowColor="Yellow"
                                 SelectionBackgroundColor="LightBlue"
                                 SelectionForegroundColor="Black"
                                 StackedHeaderBackgroundColor="Teal"
                                 StackedHeaderForegroundColor="White"/>

        <Style TargetType="syncfusion:SfDataGrid">
            <Setter Property="GridStyle" Value="{StaticResource customStyle}"/>
        </Style>
    </ResourceDictionary>
</Application.Resources>
{% endhighlight %}

## Set datagrid style from page resources

You can write custom style for the properties in [SfDataGrid.GridStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_GridStyle) class using page resource and consume the custom style as static resource to the `GridStyle` property for the required DataGrid used in that page. 

To apply custom style from page resources, follow the code example:

{% highlight xaml %}
<ContentPage.Resources>
    <ResourceDictionary>
        <syncfusion:DefaultStyle x:Key="customStyle"
                                 CurrentCellBorderColor="Green"
                                 CaptionSummaryRowForegroundColor="BlueViolet"
                                 AlternatingRowColor="Yellow"
                                 SelectionBackgroundColor="LightBlue"
                                 SelectionForegroundColor="Black"
                                 StackedHeaderBackgroundColor="Teal"
                                 StackedHeaderForegroundColor="White"/>
    </ResourceDictionary>
</ContentPage.Resources>

<ContentPage.Content>
    <syncfusion:SfDataGrid x:Name="dataGrid1"
                           SelectionMode="Single"
                           AllowDraggingColumn="True"
                           AutoGenerateColumns="False"
                           ItemsSource="{Binding OrdersInfo}"
                           GridStyle="{StaticResource customStyle}"/>
</ContentPage.Content>
{% endhighlight %}

## Applying alternate row style

The SfDataGrid applies the alternative row style by setting desired color to the [AlternatingRowColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html#Syncfusion_SfDataGrid_XForms_DataGridStyle_AlternatingRowColor) property in `DataGrid.GridStyle` or by writing a Style class deriving from [DataGridStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html), and assigning it to the [SfDataGrid.GridStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_GridStyle) property.

To customize the alternate row style in xaml, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid" ItemsSource="{Binding OrdersInfo}" >
    <syncfusion:SfDataGrid.GridStyle>
        <syncfusion:DefaultStyle AlternatingRowColor="{Binding RowColor}"/>
    </syncfusion:SfDataGrid.GridStyle>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
    public Mainpage()
    {
        InitializeComponent();
        this.dataGrid.GridStyle.AlternatingRowColor = Color.Gray;
    }
}
{% endhighlight %}
{% endtabs %}

To apply alternate row style, follow the code example:

{% highlight c# %}
//Apply alternative row style
dataGrid.GridStyle = new CustomStyle ();

// Custom style class
public class CustomGridStyle : DataGridStyle
{
    public CustomGridStyle()
    {   
    }

    public override Color GetAlternatingRowBackgroundColor()
    {
        return Color.Gray;
    }   
}
{% endhighlight %}

![DataGrid with alternate row style](SfDataGrid_images/AlternateRowStyle.png)

## Customizing the alternation count

The data grid customizes the alternate row count for applying the alternate row style using the [SfDataGrid.AlternationCount](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_AlternationCountProperty) property.

To set the alternate row count, follow the code example:

{% highlight c# %}

//Apply alternative row count
dataGrid.AlternationCount = 3;

{% endhighlight %}

![DataGrid with alternate row style with alternation count customized](SfDataGrid_images/AlernationCount.png)

## Border customization

The data grid customizes the grid borders to vertical, horizontal, both, or none. Set desired value to [GridLinesVisibility](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html#Syncfusion_SfDataGrid_XForms_DataGridStyle_GridLinesVisibility) property in [SfDataGrid.GridStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_GridStyle) or override the [DataGridStyle.GetGridLinesVisibility](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html#Syncfusion_SfDataGrid_XForms_DataGridStyle_GetGridLinesVisibility) method to customize borders in the data grid.

{% highlight c# %}
//Apply custom style to SfDataGrid from code
dataGrid.GridStyle = new CustomStyle ();
{% endhighlight %}

{% highlight c# %}
//Custom Style class
public class CustomStyle : DataGridStyle
{
    public CustomStyle ()
    {
    }
    public override GridLinesVisibility GetGridLinesVisibility()
    {
       return base.GetGridLinesVisibility();
    }
}
{% endhighlight %}

Following are the list of options available to customize the grid borders:

 * Both
 * Horizontal
 * Vertical
 * None

### Both

The [GridLinesVisibility.Both](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridLinesVisibility.html) displays the data grid with both horizontal and vertical borders.

To customize the grid lines visibility in xaml, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid" ItemsSource="{Binding OrdersInfo}" >
    <syncfusion:SfDataGrid.GridStyle>
        <syncfusion:DefaultStyle GridLinesVisibility="Both"/>
    </syncfusion:SfDataGrid.GridStyle>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
    public Mainpage()
    {
        InitializeComponent();
        this.dataGrid.GridStyle.GridLinesVisibility = Syncfusion.SfDataGrid.XForms.GridLinesVisibility.Both;
    }
}
{% endhighlight %}
{% endtabs %}

To customize the grid lines visibility by writing a custom style, follow the code example:

{% highlight c# %}
public override GridLinesVisibility GetGridLinesVisibility()
{
    return GridLinesVisibility.Both;
} 
{% endhighlight %}

The following screenshot shows the outcome upon execution of the above code:

![DataGrid with both horizontal and vertical borders lines](SfDataGrid_images/BorderCustomization_Both.png)

### Horizontal

The [GridLinesVisibility.Horizontal](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridLinesVisibility.html) allows displays the data grid with horizontal border only.

To customize the grid lines visibility in xaml, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid" ItemsSource="{Binding OrdersInfo}" >
    <syncfusion:SfDataGrid.GridStyle>
        <syncfusion:DefaultStyle GridLinesVisibility="Horizontal"/>
    </syncfusion:SfDataGrid.GridStyle>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
    public Mainpage()
    {
        InitializeComponent();
        this.dataGrid.GridStyle.GridLinesVisibility = Syncfusion.SfDataGrid.XForms.GridLinesVisibility.Horizontal;
    }
}
{% endhighlight %}
{% endtabs %}

To customize the grid lines visibility by writing a custom style, follow the code example:

{% highlight c# %}
public override GridLinesVisibility GetGridLinesVisibility()
{
    return GridLinesVisibility.Horizontal;
} 
{% endhighlight %}

The following screenshot shows the outcome upon execution of the above code:

![DataGrid with horizonal border lines](SfDataGrid_images/BorderCustomization_Horizontal.png)

### Vertical

The [GridLinesVisibility.Vertical](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridLinesVisibility.html) displays the data grid with vertical border only.

To customize the grid lines visibility in xaml, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid" ItemsSource="{Binding OrdersInfo}" >
    <syncfusion:SfDataGrid.GridStyle>
        <syncfusion:DefaultStyle GridLinesVisibility="Vertical"/>
    </syncfusion:SfDataGrid.GridStyle>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
    public Mainpage()
    {
        InitializeComponent();
        this.dataGrid.GridStyle.GridLinesVisibility = Syncfusion.SfDataGrid.XForms.GridLinesVisibility.Vertical;
    }
}
{% endhighlight %}
{% endtabs %}

To customize the grid lines visibility by writing a custom style, follow the code example:

{% highlight c# %}
public override GridLinesVisibility GetGridLinesVisibility()
{
    return GridLinesVisibility.Vertical;
} 
{% endhighlight %}

The following screenshot shows the outcome upon execution of the above code:

![DataGrid with vertical border lines](SfDataGrid_images/BorderCustomization_Vertical.png)

### None

[GridLinesVisibility.None](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridLinesVisibility.html) allows you to display the data grid without borders.

To customize the grid lines visibility in xaml, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid" ItemsSource="{Binding OrdersInfo}" >
    <syncfusion:SfDataGrid.GridStyle>
        <syncfusion:DefaultStyle GridLinesVisibility="None"/>
    </syncfusion:SfDataGrid.GridStyle>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
    public Mainpage()
    {
        InitializeComponent();
        this.dataGrid.GridStyle.GridLinesVisibility = Syncfusion.SfDataGrid.XForms.GridLinesVisibility.None;
    }
}
{% endhighlight %}
{% endtabs %}

To customize the grid lines visibility by writing a custom style, follow the code example:

{% highlight c# %}
public override GridLinesVisibility GetGridLinesVisibility()
{
    return GridLinesVisibility.None;
} 
{% endhighlight %}

The following screenshot shows the outcome upon execution of the above code:

![DataGrid with no border lines](SfDataGrid_images/BorderCustomization_None.png)

## Header border color customization

The data grid customizes the header border color for different [DataGridStyle.GridLinesVisibility](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html#Syncfusion_SfDataGrid_XForms_DataGridStyle_GridLinesVisibility) by setting desired color to the [HeaderCellBorderColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html#Syncfusion_SfDataGrid_XForms_DataGridStyle_HeaderCellBorderColor) property in `SfDataGrid.GridStyle` or by writing a custom style class deriving from [DataGridStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html), and assigning it to the [SfDataGrid.GridStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_GridStyle) property. Override the [GetHeaderBorderColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html#Syncfusion_SfDataGrid_XForms_DataGridStyle_GetHeaderBorderColor) method in the custom style to customize color of the column header and row header.

To customize the header border color in xaml, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid" ItemsSource="{Binding OrdersInfo}" >
    <syncfusion:SfDataGrid.GridStyle>
        <syncfusion:DefaultStyle HeaderCellBorderColor="{Binding BorderColor}"/>
    </syncfusion:SfDataGrid.GridStyle>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
    public Mainpage()
    {
        InitializeComponent();
        this.dataGrid.GridStyle.HeaderCellBorderColor = Color.Red;
    }
}
{% endhighlight %}
{% endtabs %}

To customize the header border color by writing a custom style, follow the code example:

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms"
             xmlns:local ="clr-namespace:DataGridSample;assembly=DataGridSample"
             x:Class="DataGridSample.Sample">

    <ContentPage.Resources>
        <ResourceDictionary>
            <local:CustomStyle x:Key="customStyle" />
        </ResourceDictionary>
    </ContentPage. mResources>

    <syncfusion:SfDataGrid x:Name="dataGrid"
                GridStyle="{StaticResource customStyle}"
                ItemsSource="{Binding OrdersInfo}" />
</ContentPage> 
{% endhighlight %}
{% highlight c# %}
//Applying custom style to SfDataGrid from code to customize header border color
SfDataGrid dataGrid = new SfDataGrid();
dataGrid.GridStyle = new customStyle ();
{% endhighlight %}
{% endtabs %}

 {% highlight c# %}
//Custom style class
public class CustomStyle : DataGridStyle
{
    Public CustomStyle()
    {
        
    }
    
    Public override color GetHeaderBorderColor()
    {
        return Color.Red;
    } 
}
{% endhighlight %}

The following screenshot shows the final outcome upon execution of the above code:
![DataGrid with header border customization](SfDataGrid_images/HeaderBorderCustomization_Both.png)

## Summary row border customization

SfDataGrid allows you to show or hide the vertical border lines in summary rows when [ShowSummaryInRow](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridSummaryRow.html#Syncfusion_SfDataGrid_XForms_GridSummaryRow_ShowSummaryInRow) is false. Set desired value to [SummaryVerticalLineVisibility](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html#Syncfusion_SfDataGrid_XForms_DataGridStyle_SummaryVerticalLineVisibility) property in [SfDataGrid.GridStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_GridStyle) or override the [DataGridStyle.GetSummaryVerticalLineVisibility](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html#Syncfusion_SfDataGrid_XForms_DataGridStyle_GetSummaryVerticalLineVisibility) method to customize summary row borders in SfDataGrid.

To customize the summary vertical line visibility in xaml, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid" ItemsSource="{Binding OrdersInfo}" >
    <syncfusion:SfDataGrid.GridStyle>
        <syncfusion:DefaultStyle SummaryVerticalLineVisibility="True"/>
    </syncfusion:SfDataGrid.GridStyle>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
    public Mainpage()
    {
        InitializeComponent();
        this.dataGrid.GridStyle.SummaryVerticalLineVisibility = true;
    }
}
{% endhighlight %}
{% endtabs %}

To customize the summary vertical line visibility by writing a custom style, follow the code example:

{% highlight c# %}
//Apply custom style to SfDataGrid from code
dataGrid.GridStyle = new CustomStyle ();
{% endhighlight %}

{% highlight c# %}
//Custom Style class
public class CustomStyle : DataGridStyle
{
    public CustomStyle ()
    {
    }
    public override bool GetSummaryVerticalLineVisibility()
    {
        return true;
    }
}
{% endhighlight %}

The following screenshot shows the final outcome upon execution of the above code:
![DataGrid with summary row border customization](SfDataGrid_images/SummaryBorderCustomization.png)

## Customizing sort icons in the header

Any desired image can be loaded as the sort indicator by setting the desired image source value to the [SortDescendingIcon](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html#Syncfusion_SfDataGrid_XForms_DataGridStyle_SortDescendingIcon) and [SortAscendingIcon](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html#Syncfusion_SfDataGrid_XForms_DataGridStyle_SortAscendingIcon) in [SfDataGrid.GridStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_GridStyle) or by using the [GetHeaderSortIndicatorDown](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html#Syncfusion_SfDataGrid_XForms_DataGridStyle_GetHeaderSortIndicatorDown) and [GetHeaderSortIndicatorUp](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html#Syncfusion_SfDataGrid_XForms_DataGridStyle_GetHeaderSortIndicatorUp) overriding from the [DataGridStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html) class. To change the sort indicators, follow the code example:

To customize the sort icons in xaml, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid" ItemsSource="{Binding OrdersInfo}" >
    <syncfusion:SfDataGrid.GridStyle>
        <syncfusion:DefaultStyle SortDescendingIcon="SfDataGrid_Sample.SortDown.png"
                                 SortAscendingIcon="SfDataGrid_Sample.SortUp.png"/>
        </syncfusion:SfDataGrid.GridStyle>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
    public Mainpage()
    {
        InitializeComponent();
        this.dataGrid.GridStyle.SortDescendingIcon = ImageSource.FromResource("SfDataGrid_Sample.SortDown.png");
        this.dataGrid.GridStyle.SortAscendingIcon = ImageSource.FromResource("SfDataGrid_Sample.SortUp.png");
    }
}
{% endhighlight %}
{% endtabs %}

To customize the sort icons by writing a custom style, follow the code example:

{% highlight c# %}

//Apply custom style to SfDataGrid from code
dataGrid.GridStyle = new Custom();

public class Custom : DataGridStyle
{

    public override ImageSource GetHeaderSortIndicatorDown()
    {
        return ImageSource.FromResource("SfDataGrid_Sample.SortDown.png");
    }

    public override ImageSource GetHeaderSortIndicatorUp()
    {
        return ImageSource.FromResource("SfDataGrid_Sample.SortUp.png");
    }

}
{% endhighlight %}

The following screenshots shows the final outcome of the above code:
![DataGrid with sort icon customized](SfDataGrid_images/SortIconCustomization.png)

N> The BuildAction image must be set to EmbeddedResource in order to access the image as resource as shown in above code.

## Customizing resizing indicator

The color of the resizing indicator can be changed by setting desired color to the [ResizingIndicatorLineColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html#Syncfusion_SfDataGrid_XForms_DataGridStyle_ResizingIndicatorLineColor) property in [SfDataGrid.GridStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_GridStyle) or by using the [GetResizingIndicatorColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html#Syncfusion_SfDataGrid_XForms_DataGridStyle_GetResizingIndicatorColor) overriding from the [DataGridStyle](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.DataGridStyle.html) class. To change the color of the resizing indicator, follow the code example:

To customize the resizing indicator line color in xaml, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid" ItemsSource="{Binding OrdersInfo}" >
    <syncfusion:SfDataGrid.GridStyle>
        <syncfusion:DefaultStyle ResizingIndicatorLineColor="Blue"/>
    </syncfusion:SfDataGrid.GridStyle>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
    public Mainpage()
    {
        InitializeComponent();
        this.dataGrid.GridStyle.ResizingIndicatorLineColor = Color.Blue;
    }
}
{% endhighlight %}
{% endtabs %}

To customize the resizing indicator line color by writing a custom style, follow the code example:

{% highlight c# %}

//Apply custom style to SfDataGrid from code
dataGrid.GridStyle = new Custom();

public class Custom : DataGridStyle
{
    public override Color GetResizingIndicatorColor()
    {
        return Color.Blue;
    }
}
{% endhighlight %}

## Border width customization

SfDataGrid allows you to customize the border width of the grid cells and the header cells. 
The default border width of the grid cell and the header cell for Forms.iOS and Forms.UWP is 0.5f and 1f for Forms.Android.

Refer the below code snippet to customize the width of the grid cells and header cells in xaml.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid" ItemsSource="{Binding OrdersInfo}" >
    <syncfusion:SfDataGrid.GridStyle>
        <syncfusion:DefaultStyle GridCellBorderWidth="5"
                                 HeaderCellBorderWidth="5"/>    
        </syncfusion:SfDataGrid.GridStyle>
</syncfusion:SfDataGrid>
{% endhighlight %}
{% highlight c# %}
public partial class MainPage : ContentPage
{
    public Mainpage()
    {
        InitializeComponent();
        this.dataGrid.GridStyle.GridCellBorderWidth = 5;
        this.dataGrid.GridStyle.HeaderCellBorderWidth = 5;
    }
}
{% endhighlight %}
{% endtabs %}

Refer the below code snippet to customize the width of the grid cells and header cells using custom style.

{% highlight c# %}

     //Apply custom style to SfDataGrid from code
      dataGrid.GridStyle = new CustomStyle();


    public class CustomStyle : DataGridStyle
    {
        public CustomStyle()
        {

        }

        // Customize border width for grid cells
        public override float GetBorderWidth()
        {
            return 5;
        }

        // Customize border width for header cells
        public override float GetHeaderBorderWidth()
        {
            return 5;
        }

    }

{% endhighlight %}

## Customize border of a particular cell

SfDataGrid allows you to customize the border color and border thickness of a particular cell using the [QueryCellStyleEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.QueryCellStyleEventArgs.html). This event will be fired for each cell. Using the [Style.BorderColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.CellStyle.html#Syncfusion_SfDataGrid_XForms_CellStyle_BorderColor) and [Style.BorderThickness](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.CellStyle.html#Syncfusion_SfDataGrid_XForms_CellStyle_BorderThickness) properties through the [QueryCellStyleEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.QueryCellStyleEventArgs.html) in its `EventHandler`, you can customize borders of an individual cell.

{% highlight c# %}
this.dataGrid.QueryCellStyle += DataGrid_QueryCellStyle;
private void DataGrid_QueryCellStyle(object sender, QueryCellStyleEventArgs e)
{
    if (e.ColumnIndex == 1 && e.RowIndex == 1)
    {
        e.Style.BorderColor = Color.Red;
        e.Style.BorderThickness = new Thickness(10);
    }
    else if (e.ColumnIndex == 3 && e.RowIndex == 5)
    {
        e.Style.BorderColor = Color.Blue;
        e.Style.BorderThickness = new Thickness(0, 10, 0, 10);
    }
    e.Handled = true;
}
{% endhighlight %}

![DataGrid with border customized](SfDataGrid_images/BorderCustomization.png)

N> You can refer to our [Xamarin DataGrid](https://www.syncfusion.com/xamarin-ui-controls/xamarin-datagrid) feature tour page for its groundbreaking feature representations. You can also explore our [Xamarin.Forms DataGrid example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/DataGrid) to knows various chart types and how to easily configured with built-in support for creating stunning visual effects.

## See also

[How to apply the row background color when mouse hover on SfDataGrid in UWP](https://support.syncfusion.com/kb/article/9779)

[How to customize the expander icon for each level of group in Xamarin.Forms DataGrid(SfDataGrid)](https://support.syncfusion.com/kb/article/9600/how-to-customize-the-expander-icon-for-each-level-of-group-in-xamarin-forms)

[How to change header background dynamically in the SfDataGrid control](https://support.syncfusion.com/kb/article/7962/how-to-change-header-background-dynamically-in-the-sfdatagrid-control)

[How to load multiple SfDataGrid's to a layout](https://support.syncfusion.com/kb/article/7041/how-to-load-multiple-sfdatagrids-to-a-layout)

[How to display custom font in GridCell](https://support.syncfusion.com/kb/article/7034/how-to-display-custom-font-in-gridcell)

[How to modify the cell borders in SfDataGrid](https://support.syncfusion.com/kb/article/7234/how-to-modify-the-cell-borders-in-sfdatagrid)

[How to bind a view model property to header template](https://support.syncfusion.com/kb/article/7054/how-to-bind-a-view-model-property-to-header-template)

[How to load grid without borders](https://support.syncfusion.com/kb/article/6679/how-to-load-grid-without-borders)

[How to load a button in Header using HeaderTemplate in code-behind](https://support.syncfusion.com/kb/article/6564/how-to-load-a-button-in-header-using-headertemplate-in-code-behind)

[How to add multiple views in a grid cell in SfDataGrid](https://support.syncfusion.com/kb/article/6562/how-to-add-multiple-views-in-a-grid-cell-in-sfdatagrid)

[How to set different background color for each column header in SfDataGrid](https://support.syncfusion.com/kb/article/6708/how-to-set-different-background-color-for-each-column-header-in-xamarinforms-datagrid)

[How to display an animation while loading the data in the SfDataGrid](https://support.syncfusion.com/kb/article/6524/how-to-display-an-animation-while-loading-the-data-in-the-sfdatagrid)

[How to apply multiple selection colors in SfDataGrid](https://support.syncfusion.com/kb/article/6520/how-to-apply-multiple-selection-colors-in-xamarinforms-datagrid)