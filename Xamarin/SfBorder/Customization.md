---
layout: post
title: Various customization in Syncfusion border control for Xamarin.Forms
description: Learn how to customize the border control
platform: Xamarin
control: SfBorder
documentation: ug
---

# Customization

The border control supports customizing the border color, width, corner radius, background color, and more. The border can be customized using the following properties.

## Border color

You can customize the color of the border using the `BorderColor` property.

{% tabs %}
{% highlight xaml %}

<border:SfBorder x:Name="border" BorderColor = "Red"  CornerRadius="20" BorderWidth="3">
 <Label Text="James Williamson" 
 TextColor="Black"/>
</border:SfBorder>

{% endhighlight %}
{% highlight c# %}

SfBorder border = new SfBorder();
border.CornerRadius = 20;
border.BorderColor = Color.Red;
border.BorderWidth = 3;
Label label = new Label();
label.Text = "James Williamson";
label.TextColor = Color.Black;
border.Content = label;
this.Content = border;

{% endhighlight %}
{% endtabs %}

![bordercolor](images/Xamarin_Forms_BorderColor.png)

## Background color

The background color of the border control can be customized using the `BackgroundColor` property.

{% tabs %}
{% highlight xaml %}

<border:SfBorder x:Name="border" BorderColor = "Red" BackgroundColor= "Green" CornerRadius="20" BorderWidth="3">
 <Label Text="James Williamson" 
 TextColor="Black"/>
</border:SfBorder>

{% endhighlight %}
{% highlight c# %}

SfBorder border = new SfBorder();
border.CornerRadius = 20;
border.BorderColor = Color.Red;
border.BorderWidth = 3;
Label label = new Label();
label.Text = "James Williamson";
label.TextColor = Color.Black;
border.Content = label;
border.BackgroundColor = Color.Green;
this.Content = border;

{% endhighlight %}
{% endtabs %}

![backgroundcolor](images/Xamarin_Forms_BackgroundColor.png)

## Border width

You can customize the thickness of the border using the `BorderWidth` property.

{% tabs %}
{% highlight xaml %}

<border:SfBorder x:Name="border" BorderColor = "Red" CornerRadius="20" BorderWidth="12">
 <Label Text="James Williamson" 
 TextColor="Black"/>
</border:SfBorder>

{% endhighlight %}
{% highlight c# %}

SfBorder border = new SfBorder();
border.CornerRadius = 20;
border.BorderColor = Color.Red;
border.BorderWidth = 12;
Label label = new Label();
label.Text = "James Williamson";
label.TextColor = Color.Black;
border.Content = label;
this.Content = border;


{% endhighlight %}
{% endtabs %}

![borderwidth](images/Xamarin_Forms_BorderWidth.png)

## Corner radius

You can customize the corner radius of the border on four sides using the `CornerRadius` property with type as `Thickness`.

{% tabs %}
{% highlight xaml %}

<border:SfBorder x:Name="border" BorderColor = "Red" CornerRadius="0,10,10,0" BorderWidth="12">
 <Label Text="James Williamson" 
 TextColor="Black"/>
</border:SfBorder>

{% endhighlight %}
{% highlight c# %}

SfBorder border = new SfBorder();
border.CornerRadius =  new Thickness (0,10,10,0);
border.BorderColor = Color.Red;
border.BorderWidth = 12;
Label label = new Label();
label.Text = "James Williamson";
label.TextColor = Color.Black;
border.Content = label;
this.Content = border;

{% endhighlight %}
{% endtabs %}

![cornerradius](images/Xamarin_Forms_CornerRadius.png)

## Adding circular image

You can add the any view inside the border control by adding inside the Content property of Border Control. The below code demonstrate how to apply border using `CornerRadius` property for the circular image.

{% tabs %}
{% highlight xaml %}

<Grid HeightRequest="100" WidthRequest="100" HorizontalOptions="Center" VerticalOptions="Center">
    <border:SfBorder BorderColor="Black" HorizontalOptions="Center" VerticalOptions="Center" CornerRadius="50">
    <Image Source="plus.jpeg" />
    </border:SfBorder>
</Grid>

{% endhighlight %}
{% highlight c# %}

Grid grid = new Grid();
grid.HeightRequest = 100;
grid.WidthRequest = 100;
grid.HorizontalOptions = LayoutOptions.Center;
grid.VerticalOptions = LayoutOptions.Center;
SfBorder border = new SfBorder();
border.BorderColor = Color.Black;
border.HorizontalOptions = LayoutOptions.Center;
border.VerticalOptions = LayoutOptions.Center;
border.CornerRadius = 50;
Image image = new Image();
image.Source = "plus.jpeg";
border.Content = image;
grid.Children.Add(border);
this.Content = grid;

{% endhighlight %}
{% endtabs %}

![circularimage](images/Xamarin_Forms_CircularImage.png)


