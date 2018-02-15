---
layout: post
title: Xamarin.Froms Chart Tooltip
description: How to enable and customize the tooltip in Essential Xamarin.Forms Chart
platform: xamarin
control: Chart
documentation: ug
---

# Tooltip

Chart provides tooltip support for all series. It is used to show the information about a segment when the segment is tapped. To enable the tooltip, set the [`EnableTooltip`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~EnableTooltipProperty.html#) property to `true`.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.Series>

	<chart:ColumnSeries ItemsSource="{Binding Data}" XBindingPath="Month" YBindingPath="Value" EnableTooltip="True"/>

</chart:SfChart.Series>

{% endhighlight %}

{% highlight c# %}

ColumnSeries column = new ColumnSeries ();

column.XBindingPath = "Month";

column.YBindingPath = "Value";

column.ItemsSource = Data;

column.EnableTooltip = true;

chart.Series.Add(column);	

{% endhighlight %}

{% endtabs %}

![](tooltip_images/tooltip1.png)

## Customizing the appearance

You can customize the appearance of the tooltip label. For customizing, add an instance of the [`ChartTooltipBehavior`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior.html#) to the [`ChartBehavior`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior.html#) collection property of chart. The following properties are used to customize the tooltip label, which are available in the `ChartTooltipBehavior`:(http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior.html#).

* [`BorderColor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~BorderColorProperty.html#)—Used to change the border color of the label.
* [`BorderWidth`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~BorderWidthProperty.html#)—Used to change the border width of the label.
* [`BackgroundColor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~BackgroundColorProperty.html#)—Used to change the background color of the label.
* [`Margin`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~MarginProperty.html#)—Used to change border thickness of the label.
* [`TextColor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~TextColorProperty.html#)—Used to change the color of the text.
* [`Font`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~FontProperty.html#)—Used to change label's font size, font family, and font weight.
* [`LabelFormat`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~LabelFormatProperty.html#)—Used to format the label.
* [`Duration`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~DurationProperty.html#)—Used to set the visible duration of label.
* [`OffsetX`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~OffsetXProperty.html#)—Used to move the label horizontally.
* [`OffsetY`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~OffsetYProperty.html#)—Used to move the label vertically.

{% tabs %} 

{% highlight xaml %}

<chart:SfChart.ChartBehaviors>

	<chart:ChartTooltipBehavior BackgroundColor="Blue" BorderWidth="3" BorderColor="Aqua" TextColor="White" Margin="5" Duration="10" Font="Times New Roman, 15"/>

	</chart:ChartTooltipBehavior>

</chart:SfChart.ChartBehaviors>


{% endhighlight %}

{% highlight c# %}

SfChart chart = new SfChart();
...

ChartTooltipBehavior tool = new ChartTooltipBehavior();
tool.BackgroundColor = Color.Blue;
tool.BorderWidth = 3;
tool.BorderColor = Color.Aqua;
tool.TextColor = Color.White;
tool.Margin = new Thickness(5, 5, 5, 5);
tool.Duration = 10;
tool.Font = Font.OfSize(“Times New Roman”,15);	
chart.ChartBehaviors.Add(tool);

{% endhighlight %}

{% endtabs %}

![](tooltip_images/tooltip2.png)

## Tooltip template

You can customize the appearance of the tooltip with your own template by using the [`TooltipTemplate`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~TooltipTemplateProperty.html#) property of the [`Series`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries.html#).

{% tabs %} 

{% highlight xaml %}

<chart:ColumnSeries ItemsSource="{Binding ColumnData}" EnableTooltip="true" 
XBindingPath="Month" YBindingPath="Value" >
              <chart:ColumnSeries.TooltipTemplate>
                  <DataTemplate>
                      <StackLayout Orientation="Horizontal">
                              <Label Text="Temperature:" />
                              <Label Text="{Binding Value}"/>
                      </StackLayout>
                  </DataTemplate>
              </chart:ColumnSeries.TooltipTemplate>
</chart:ColumnSeries>


{% endhighlight %}

{% highlight c# %}

ColumnSeries column = new ColumnSeries (); 
column.ItemsSource = viewModel.ColumnData;
column.XBindingPath = "Month";
column.YBindingPath = "Value";
column.EnableTooltip = true;

DataTemplate template = new DataTemplate (() => {
StackLayout stack = new StackLayout(){ Orientation = StackOrientation.Horizontal};
Label label = new Label(){Text="Temperature:"};
Label yValue = new Label();
yValue.SetBinding (Label.TextProperty, "Value");
stack.Children.Add(label);
stack.Children.Add(yValue);
return stack;
});

column.TooltipTemplate = template;
Chart.Series.Add (column);

{% endhighlight %}

{% endtabs %}

