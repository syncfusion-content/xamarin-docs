---
layout: post
title: Xamarin.Froms Chart Tooltip
description: How to enable and customize the tooltip in Essential Xamarin.Forms Chart
platform: xamarin
control: Chart
documentation: ug
---

# Tooltip

[`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html) provides tooltip support for all series. It is used to show information about the segment, when you tap on the segment. To enable the tooltip, you need to set [`EnableTooltip`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~EnableTooltipProperty.html#) property as `true`.

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

## Customizing appearance

You can customize the tooltip label. For customizing, you need to add an instance of [`ChartTooltipBehavior`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior.html#) to the [`ChartBehavior`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartBehavior.html#) collection property of [`SfChart`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.SfChart.html). Following properties are used to customize the tooltip label which are available in [`ChartTooltipBehavior`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior.html#).

* [`BorderColor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~BorderColorProperty.html#) – used to change the label border color
* [`BorderWidth`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~BorderWidthProperty.html#) – used to change the label border width
* [`BackgroundColor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~BackgroundColorProperty.html#) – used to change the label background color
* [`Margin`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~MarginProperty.html#) – used to change label border thickness
* [`TextColor`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~TextColorProperty.html#) – used to change the text color
* [`Font`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~FontProperty.html#) – used to change label font size, family and weight
* [`LabelFormat`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~LabelFormatProperty.html#) – used to format the label
* [`Duration`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~DurationProperty.html#) – used to set the visible duration of label
* [`OffsetX`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~OffsetXProperty.html#) – used to move the label horizontally
* [`OffsetY`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~OffsetYProperty.html#) – used to move the label vertically

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

## Tooltip Template

You can customize the appearance of the tooltip with your own template by using the [`TooltipTemplate`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries~TooltipTemplateProperty.html#) property of [`Series`](http://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartSeries.html#).

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

##Methods

You can [`show`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~Show.html) or [`hide`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~Hide.html) the chart tooltip programmatically by using the show or hide method. 

###Show method

This method is used to [`show`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~Show.html) the tooltip programmatically at the mentioned coordinator points of the chart area.

{% highlight c# %}

	tooltip.Show(pointX, pointY, true);

{% endhighlight %}

The tooltip will be shown based on the chart area where the pointX and pointY coordinates are passed. The bool value is used to decide whether the tooltip needs to be animated or not.

###Hide method

This method is used to [`hide`](https://help.syncfusion.com/cr/cref_files/xamarin/sfchart/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.ChartTooltipBehavior~Hide.html) the tooltip programmatically in the chart area. The bool value decides whether the tooltip needs to be animated or not.

{% highlight c# %}

 	tooltip.Hide(true);

{% endhighlight %}

