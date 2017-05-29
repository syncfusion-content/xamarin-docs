---

layout: post
title: Appearance and Styling in Syncfusion Rating control for Xamarin.Forms
description: Learn how to change the Appearance and Styling of rating control
platform: Xamarin
control: Rating
documentation: ug

---

# Appearance and Styling

SfRating control provides support to customize the Size, Item count and space between rating items.

## Set Size

The `ItemSize` property sets the size of the rating items. 

N> By default, property value is 50.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" ItemSize="20" />
	
{% endhighlight %}

{% highlight C# %}

	rating.ItemSize=20;

{% endhighlight %}

{% endtabs %}

![](images/layoutSize.jpg)

## Set Number of Items

The `ItemCount` property sets the number of rating items to be displayed. 

N> The default property value is 5.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" ItemCount="4" />
	
{% endhighlight %}

{% highlight C# %}

	rating.ItemCount=4;

{% endhighlight %}

{% endtabs %}

![](images/four star.jpg)
 
## Set Space between Items

The `ItemSpacing` property sets the spacing between the rating items. 

N> By default, property value is 5.

{% tabs %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" ItemSpacing="20" />
	
{% endhighlight %}

{% highlight C# %}

	rating.ItemSpacing=20;

{% endhighlight %}

{% endtabs %}

![](images/layoutSpace.jpg) 


## Rating Settings

This section explains various Rating settings available in SfRating control. 

{% tabs %}

{% highlight xaml %}

     <rating:SfRating  x:Name="rating" Value="3">
     <rating:SfRating.RatingSettings>
     <rating:SfRatingSettings RatedFill="Red" UnRatedFill="Blue" RatedStrokeWidth="0" UnRatedStrokeWidth="0" />
     </rating:SfRating.RatingSettings>
     </rating:SfRating>
	
{% endhighlight %}

{% highlight C# %}

     SfRating rating= new SfRating();
     SfRatingSettings  ratingSettings = new SfRatingSettings();
	 ratingSettings.RatedFill = Color.FromHex("#fbd10a");
	 ratingSettings.UnRatedFill = Color.FromHex("#cdcccb");
	 ratingSettings.RatedStrokeThickness = 0;
	 ratingSettings.UnRatedStrokeThickness = 0;
     rating.RatingSettings=ratingSettings;

{% endhighlight %}

{% endtabs %}

 
