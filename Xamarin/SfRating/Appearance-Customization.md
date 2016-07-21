---

layout: post
title: Appearance and Styling in Syncfusion Rating control for Xamarin.Forms
description: Learn how to change the Appearance and Styling of rating control
platform: Xamarin
control: Rating
documentation: ug

---

# Appearance Customization

This section explains about the various appearance customizations available in SfRating control.
 
## Set Fill Color

SfRating control has support to set the fill color for the selected and unselected items.

### Selected Items

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

### Unselected Items

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

## Set Stroke Color

SfRating control has support to set the stroke color for the selected and unselected items.

### Selected Items

The RatedStroke property sets the stroke for the rated area with the specified solid color for the selected items in the SfRating control.

{% tabs %}

{% highlight C# %}

	ratingSettings.RatedStroke=Color.GREEN;

{% endhighlight %}

{% highlight xaml %}

	<rating:SfRating x:Name="ratingSettings" RatedStroke="Green" />
	
{% endhighlight %}

{% endtabs %}

![](images/ratedStroke.jpg)

### Unselected Items

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
 
## Set Stroke Thickness

SfRating control has support to set the stroke thickness for the selected and unselected items.

### Selected Items

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


### Unselected Items

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
