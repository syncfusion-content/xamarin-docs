---

layout: post
title: Appearance and Styling in Syncfusion Rating control for Xamarin.Forms
description: Learn how to change the Appearance and Styling of rating control
platform: Xamarin
control: Rating
documentation: ug

---

# Appearance and Styling

## Item Size

The `ItemSize` property sets the size of the rating items. 

N> By default, property value is 50.

{% tabs %}

{% highlight C# %}

	rating.ItemSize=20;

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" ItemSize="20" />
	
{% endhighlight %}

{% endtabs %}

![](images/layoutSize.jpg)
 
## Item Spacing

The `ItemSpacing` property sets the spacing between the rating items. 

N> By default, property value is 5.

{% tabs %}

{% highlight C# %}

	rating.ItemSpacing=20;

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" ItemSpacing="20" />
	
{% endhighlight %}

{% endtabs %}

![](images/layoutSpace.jpg)
 
## Number of Items

The `ItemCount` property sets the number of rating items to be displayed. 

N> The default property value is 5.

{% tabs %}

{% highlight C# %}

	rating.ItemCount=4;

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" ItemCount="4" />
	
{% endhighlight %}

{% endtabs %}

![](images/four star.jpg)
 
## Read Only

SfRating control provides support for changeable or unchangeable values for Rating control. This is achieved by the ReadOnly property. When this property is set to True, the Rating value becomes unchangeable. By default, this property value is set to False.

{% tabs %}

{% highlight C# %}

	rating.ReadOnly=true;

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" ReadOnly="true" />
	
{% endhighlight %}

{% endtabs %}

![](images/readOnly.jpg)

## Rating Settings

{% tabs %}

{% highlight C# %}

	SfRatingSettings  ratingSettings = new SfRatingSettings();
	ratingSettings.RatedFill = Color.FromHex("#fbd10a");
	ratingSettings.UnRatedFill = Color.FromHex("#cdcccb");
	ratingSettings.RatedStrokeThickness = 0;
	ratingSettings.UnRatedStrokeThickness = 0;

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="ratingSettings" RatedFill="Red" UnRatedFill="Blue" RatedStrokeThickness="0" UnRatedStrokeThickness="0" />
	
{% endhighlight %}

{% endtabs %}

After adding Rating settings , add the Rating Settings instance to Rating instance.

{% tabs %}

{% highlight C# %}

	rating.RatingSettings=ratingSettings;

{% endhighlight%}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" RatingSettings="ratingSettings" />
	
{% endhighlight %}

{% endtabs %}
 
### Rated Fill

The `RatedFill` property fills the rated area with the specified solid color in the SfRating control.

{% tabs %}

{% highlight C# %}

	ratingSettings.RatedFill = Color.FromHex("#fbd10a");
           
{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="ratingSettings" RatedFill="Red" />
	
{% endhighlight %}

{% endtabs %}

![](images/ratedFill.jpg)

### Rated Stroke

The RatedStroke property sets the stroke for the rated area with the specified solid color in the SfRating control.

{% tabs %}

{% highlight C# %}

	ratingSettings.RatedStroke=Color.GREEN;

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="ratingSettings" RatedStroke="Green" />
	
{% endhighlight %}

{% endtabs %}

![](images/ratedStroke.jpg)
 
### Rated Stroke Thickness

The `RatedStrokeThickness` property sets the stroke thickness for the rated area with the specified value in the SfRating control.

{% tabs %}

{% highlight C# %}

	ratingSettings.RatedStrokeThickness=3;

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="ratingSettings" RatedStrokeThickness="3" />
	
{% endhighlight %}

{% endtabs %}

![](images/ratedStrokeThickness.jpg)
 
### UnRated Fill

The `UnRatedFill` property fills the unrated area with the specified solid color in the SfRating control.

{% tabs %}

{% highlight C# %}

	ratingSettings.UnRatedFill=Color.GRAY;

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="ratingSettings" UnRatedFill="Gray" />
	
{% endhighlight %}

{% endtabs %}

![](images/unRatedFill.jpg)

### UnRated Stroke

The `UnRatedStroke` property sets the stroke for the unrated area with the specified solid color in the SfRating control.

{% tabs %}

{% highlight C# %}

	ratingSettings.UnRatedStroke=Color.BLACK;

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="ratingSettings" UnRatedStroke="Black" />
	
{% endhighlight %}

{% endtabs %}

![](images/unRatedStroke.jpg)

### UnRated Stroke Thickness

The `UnRatedStrokeThickness` property sets the stroke thickness for the unrated area with the specified value in the SfRating control.

{% tabs %}

{% highlight C# %}

	ratingSettings.UnRatedStrokeThickness=3;

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="ratingSettings" UnRatedStrokeThickness="3" />
	
{% endhighlight %}

{% endtabs %}

![](images/unRatedStrokeThickness.jpg)
