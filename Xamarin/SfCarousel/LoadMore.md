---
layout : post
title : LoadMore in Syncfusion Carousel control in Xamarin.Forms.
description : Learn how to set the LoadMore in Carousel for Xamarin.Forms.
platform : Xamarin
control : Carousel
documentation : ug
---

# LoadMore

Virtualization can be achieved by using the Load more concept. This support is used to handle the numerous items in the carousel control. A particular items are maintained in the view port based on the `LoadMoreItemsCount` property. The LoadMore view is added after the last item in the collection of carousel view. When tapping the LoadMore view, the next set of items in the collection can be added to the carousel.

The following properties are used to achieve this support:

*	`AllowLoadMore`

*	`LoadMoreItemsCount`

*	`LoadMoreView`

## AllowLoadMore

By enabling the `AllowLoadMore` property, the LoadMore support works in the carousel view. 

N>The default value of the `AllowLoadMore` property is false.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCarousel 
      x:Name="carousel"
      AllowLoadMore="True" />

{% endhighlight %}

{% highlight c# %}

SfCarousel carousel = new SfCarousel();

//Enable load more in SfCarousel

carousel.AllowLoadMore = true;

{% endhighlight %}

{% endtabs %}

## LoadMoreItemsCount

Number of items can be maintained in the carousel control by using the `LoadMoreItemsCount` property. By using the `LoadMoreItemsCount` property, numerous items can be separated. 

N>The default value of the `LoadMoreItemsCount` property is 3.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCarousel 
      x:Name="carousel"  
      LoadMoreItemsCount="5"/>

{% endhighlight %}

{% highlight c# %}

SfCarousel carousel = new SfCarousel();
carousel.LoadMoreItemsCount = 5;

{% endhighlight %}

{% endtabs %}

## LoadMoreView

Custom view can be passed instead of the LoadMore label by using the `LoadMoreView` property. 

{% tabs %}

{% highlight xaml %}

<syncfusion:SfCarousel.LoadMoreView>
      <Grid
      BackgroundColor="#FFFFFFFF">
        <Label
        Text="Load More..."
        FontSize="14"
        TextColor="#FF000000"
        FontAttributes="Bold"
        HorizontalTextAlignment="Center"
        VerticalTextAlignment="Center"
        HorizontalOptions="Center"
        VerticalOptions="Center" /> 
    </Grid>
</syncfusion:SfCarousel.LoadMoreView>

{% endhighlight %}

{% highlight c# %}

SfCarousel carousel = new SfCarousel();
Grid grid = new Grid();
grid.BackgroundColor = Color.White;
Label label = new Label();
label.Text = "Load More...";
label.FontSize = 14;
label.TextColor = Color.Black;
label.FontAttributes = FontAttributes.Bold;
label.HorizontalOptions = LayoutOptions.Center;
label.VerticalOptions = LayoutOptions.Center;
label.HorizontalTextAlignment = TextAlignment.Center;
label.VerticalTextAlignment = TextAlignment.Center;
grid.Children.Add(label);
carousel.LoadMoreView = grid;

{% endhighlight %}

{% endtabs %}

