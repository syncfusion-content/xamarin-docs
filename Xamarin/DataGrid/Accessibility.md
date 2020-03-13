---
layout: post
title: Accessibility | SfDataGrid | Xamarin | Syncfusion
description: Set AutomationId to SfDataGrid for automation framework to find and interact with control inner elements.
platform: xamarin
control: SfDataGrid
documentation: UG
---

# AutomationId in Xamarin.Forms DataGrid

SfDataGrid and SfDataPager support built-in [AutomationId](https://docs.microsoft.com/en-gb/dotnet/api/xamarin.forms.element.automationid?view=xamarin-forms#Xamarin_Forms_Element_AutomationId) for all their inner elements. These `AutomationId` values allow the automation framework to find and interact with the inner elements when the test scripts are run. A unique `AutomationId` is maintained for each inner element by prefixing the control's `AutomationId` with the inner element's Id.

## DataGrid

The below table illustrates the predefined automation values set internally which can be used to identify the SfDataGrid elements.

<table>
<tr>
<th>Element</th>
<th>Value</th>
<th>Example</th>
</tr>
<tr>
<td>Header Row</td>
<td>"Row" + RowIndex</td>
<td>Row0</td>
</tr>
<tr>
<td>Header Cell</td>
<td>"R" + RowIndex + "C" + ColumnIndex + " " + CellValue</td>
<td>R0C2 Customer Name</td>
</tr>
<tr>
<td>Row</td>
<td>"Row" + RowIndex</td>
<td>Row4</td>
</tr>
<tr>
<td>Grid Cell</td>
<td>"R" + RowIndex + "C" + ColumnIndex + " " + CellValue</td>
<td>R4C2 Thomas</td>
</tr>
<tr>
<td>Group Header</td>
<td>"Row" + RowIndex</td>
<td>Row5</td>
</tr>
<tr>
<td>LoadMore View</td>
<td>"LOAD MORE ITEMS"</td>
<td>LOAD MORE ITEMS</td>
</tr>
</table>

The following screenshots illustrate the `AutomationId` values of grid cells, rows, and other inner elements of SfDataGrid.

![Automation Id format for Row and Cell element](SfDataGrid_images/AutomationId_DataGrid.png)

![Automation Id format for LoadMoreView](SfDataGrid_images/AutomationId_LoadMoreItems.png)

The following code snippet demonstrates how to set the `AutomationId` to data grid.

{% tabs %}
{% highlight xaml %}

<syncfusion:SfDataGrid x:Name="dataGrid"
                        ItemsSource="{Binding OrdersInfo,Mode=TwoWay}"
                        AutomationId="SyncfusionGrid"
                        AllowGroupExpandCollapse="True">

                <sfgrid:SfDataGrid.GroupColumnDescriptions>
                    <sfgrid:GroupColumnDescription ColumnName="OrderID" />
                </sfgrid:SfDataGrid.GroupColumnDescriptions>
                
                <sfgrid:SfDataGrid.CaptionSummaryRow>
                    <sfgrid:GridGroupSummaryRow Title="Total Count of OrderId:{OrderID}"
                           ShowSummaryInRow="True">
                        <sfgrid:GridGroupSummaryRow.SummaryColumns>
                            <sfgrid:GridSummaryColumn Name="OrderID"
                                      MappingName="OrderID"
                                      Format="{}{Count}"
                                      SummaryType="CountAggregate" />
                        </sfgrid:GridGroupSummaryRow.SummaryColumns>
                    </sfgrid:GridGroupSummaryRow>
                </sfgrid:SfDataGrid.CaptionSummaryRow>
                          
    </syncfusion:SfDataGrid>

{% endhighlight %}

{% highlight c# %}

ViewModel viewModel = new ViewModel();
SfDataGrid dataGrid = new SfDataGrid();
dataGrid.ItemsSource = viewModel.OrderInfoCollection;
dataGrid.AutomationId = "SyncfusionGrid";
dataGrid.AllowGroupExpandCollapse = true;

this.sfGrid.GroupColumnDescriptions.Add(new GroupColumnDescription()
            {
                ColumnName = "OrderID",
            });

GridGroupSummaryRow summaryRow = new GridGroupSummaryRow();
summaryRow.Title = "Total Count of OrderId:{OrderID}";
summaryRow.ShowSummaryInRow = true;
summaryRow.SummaryColumns.Add(new GridSummaryColumn()
            {
                Name = "OrderID",
                MappingName = "OrderID",
                Format = "{Count}",
                SummaryType = SummaryType.CountAggregate
            });
sfGrid.CaptionSummaryRow = summaryRow;

{% endhighlight %}
{% endtabs %}

Refer to the following code snippet to access the inner elements of data grid from the automation script.

{% tabs %}
{% highlight c# %}

[Test]
[Description("SfDataGrid Automation Id")]
public void SfDataGrid_AutomationId()
{
   // To enter edit mode for the grid cell at fourth row and second column.
   App.DoubleTap("SyncfusionGrid R4C1 California");

   // To tap group expand and collapse icon
   App.Tap("SyncfusionGrid Row5");

   // To apply sorting 
   App.Tap("SyncfusionGrid R2C1 State Name");

   // To click LoadMoreView for loading more items
   App.Tap("SyncfusionGrid LOAD MORE ITEMS");
}

{% endhighlight %}
{% endtabs %}

## DataPager

The below table illustrates the predefined automation values set internally which can be used to identify the SfDataPager elements.

<table>
<tr>
<th>Element</th>
<th>Value</th>
</tr>
<tr>
<td>First page button</td>
<td>"FirstPage"</td>
</tr>
<tr>
<td>Previous page button</td>
<td>"PreviousPage"</td>
</tr>
<tr>
<td>Numeric buttons</td>
<td>
"NumericButton" + NumericButtonIndex <br/>
Example : NumericButton3
</td>
</tr>
<tr>
<td>Next page button</td>
<td>"NextPage"</td>
</tr>
<tr>
<td>Last page button</td>
<td>"LastPage"</td>
</tr>
</table>

The following screenshot illustrates the `AutomationId` values of the pager buttons in SfDataPager.

![Automation Id format for Pager](SfDataGrid_images/AutomationId_Pager.png)

The following code snippet demonstrates how to set `AutomationId` to dataPager.

{% tabs %}
{% highlight xaml %}

<Grid> 
      <Grid.RowDefinitions>
        <RowDefinition Height="*" />
        <RowDefinition Height="Auto" />
      </Grid.RowDefinitions>
      <sfPager:SfDataPager x:Name ="dataPager"
                           Grid.Row="1"           
                           PageSize="10" 
                           HeightRequest ="50"
                           NumericButtonCount="20"
                           Source="{Binding OrdersInfo}"
                           AutomationId="SyncfusionPager">
      </sfPager:SfDataPager>
       
      <sfgrid:SfDataGrid x:Name="dataGrid"
                         Grid.Row="0"
                         ItemsSource="{Binding PagedSource, Source={x:Reference dataPager}}" >                   
      </sfgrid:SfDataGrid>
</Grid> 
                      
{% endhighlight %}

{% highlight c# %}

SfDataGrid sfGrid = new SfDataGrid();
SfDataPager sfPager = new SfDataPager();
ViewModel viewModel = new ViewModel();
sfPager.PageSize = 15; 
sfPager.Source = viewModel.Info; 
sfGrid.ItemsSource = sfPager.PagedSource;  
sfPager.AutomationId = "SyncfusionPager";

Grid gridLayout = new Grid();
gridLayout.HorizontalOptions = LayoutOptions.FillAndExpand;
gridLayout.RowDefinitions = new RowDefinitionCollection
        {
          new RowDefinition { },
          new RowDefinition { Height = 50 },    
        };
gridLayout.Children.Add(sfGrid, 0, 0);
gridLayout.Children.Add(sfPager, 0, 1);

this.Content = gridLayout;

{% endhighlight %}
{% endtabs %}

Refer to the following code snippet to access the inner elements of data pager from automation script.

{% tabs %}
{% highlight c# %}

[Test]
[Description("SfDataPager Automation Id")]
public void SfDataPager_AutomationId()
{
   // To tap the first page numeric button
   App.Tap("SyncfusionPager FirstPage");

   // To tap the previous page numeric button
   App.Tap("SyncfusionPager PreviousPage");

   // To tap the next page numeric button
   App.Tap("SyncfusionPager NextPage");

   // To tap the next last page numeric button
   App.Tap("SyncfusionPager LastPage");

   // To tap the second numeric button
   App.Tap("SyncfusionPager NumericButton2");
}

{% endhighlight %}
{% endtabs %}
