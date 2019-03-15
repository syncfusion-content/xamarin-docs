---
layout: post
title: Fit the center view within the Syncfusion doughnut series hole.
description: Fit the view of center view within the doughnut series hole.
platform: xamarin
control: Chart
documentation: ug
---

## Fit the view of doughnut center view within the doughnut hole. 

The [`DoughnutSizeConverter`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DoughnutSizeConverter.html) is the converter class, which is used to fit the view size by binded this class with Width and Height of the image. 

The following code will helps to fit the image size based on the doughnut series [`InnerRadius`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DoughnutSeries~InnerRadius.html), The [`Percentage`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DoughnutSizeConverter~Percentage.html) property of [`DoughnutSizeConverter`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfChart.XForms~Syncfusion.SfChart.XForms.DoughnutSizeConverter.html) class  is used to scale the view with in the series hole.

{% highlight xaml %}

…
<chart:SfChart.Resources>

         <chart:DoughnutSizeConverter Percentage="85" x:Key="imageSizeConverter"/>

</chart:SfChart.Resources>

…


  <chart:SfChart.Series>
                <chart:DoughnutSeries x:Name="doughnutSeries" ItemsSource="{Binding DoughnutSeriesData}">
<chart:DoughnutSeries.CenterView>
<Image Source="Person.png" HeightRequest="{Binding InnerRadius, Converter={StaticResource imageSizeConverter}}" WidthRequest="{Binding InnerRadius, Converter={StaticResource imageSizeConverter}}"  HorizontalOptions="Center" VerticalOptions="Center" >
</Image>
                  </chart:DoughnutSeries.CenterView>
  </chart:SfChart.Series>

…

{% endhighlight %}

#### Fit the label of center view in doughnut series. 

By the same way we can fix the label size by binding the converter to FontSize of the label. And set the Converter parameter as same label by below code. 

{% highlight xaml %}

…
<chart:DoughnutSeries.CenterView>

<Label x:Name="Center_Text" Text="{Binding BindingContext.CenterText }"  FontSize="{Binding InnerRadius, Converter={StaticResource centerViewSizeConverter},ConverterParameter={x:Reference Center_Text}}" HorizontalTextAlignment="Center"/>

</chart:DoughnutSeries.CenterView>

… 

{% endhighlight %}
