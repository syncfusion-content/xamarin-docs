---

layout: post
title: Appearance and Styling in Syncfusion Rating control for Xamarin.Forms
description: Learn how to change the Appearance and Styling of rating control
platform: Xamarin.Forms
control: Rating
documentation: ug

---

# Appearance and Styling

## Item Size

The `ItemSize` property sets the size of the rating items. 

N> By default, property value is 50.

{% highlight C# %}

	sfRating.ItemSize=20;

{% endhighlight %}

![](images/layoutSize.jpg)
 
## Item Spacing

The `ItemSpacing` property sets the spacing between the rating items. 

N> By default, property value is 5.

{% highlight C# %}

	sfRating.ItemSpacing=20;

{% endhighlight %}

![](images/layoutSpace.jpg)
 
## Number of Items

The `ItemCount` property sets the number of rating items to be displayed. 

N> The default property value is 5.

{% highlight C# %}

	sfRating.ItemCount=4;

{% endhighlight %}

![](images/four star.jpg)
 
## Read Only

Rating control provides support for changeable or unchangeable values for Rating control. This is achieved by the ReadOnly property. When this property is set to True, the Rating value becomes unchangeable. By default, this property value is set to False.

{% highlight C# %}

	sfRating.ReadOnly=true;

{% endhighlight %}

![](images/readOnly.jpg)

## Rating Settings

{% highlight C# %}

	SfRatingSettings  sfRatingSettings = new SfRatingSettings();
	sfRatingSettings.RatedFill = Color.FromHex("#fbd10a");
	sfRatingSettings.UnRatedFill = Color.FromHex("#cdcccb");
	sfRatingSettings.RatedStrokeThickness = 0;
	sfRatingSettings.UnRatedStrokeThickness = 0;

{% endhighlight %}

After adding Rating settings , add the Rating Settings instance to Rating instance.

{% highlight C# %}

	sfRating.RatingSettings=sfRatingSettings;

{% endhighlight%}
 
### Rated Fill

The RatedFill property fills the rated area with the specified solid color in the SfRating control.

{% highlight C# %}

	sfRatingSettings.RatedFill = Color.FromHex("#fbd10a");
           
{% endhighlight %}

![](images/ratedFill.jpg)

### Rated Stroke

The RatedStroke property sets the stroke for the rated area with the specified solid color in the SfRating control.

{% highlight C# %}

	sfRatingSettings.RatedStroke=Color.GREEN;

{% endhighlight %}

![](images/ratedStroke.jpg)
 
### Rated Stroke Thickness

The RatedStrokeThickness property sets the stroke thickness for the rated area with the specified value in the SfRating control.

{% highlight C# %}

	sfRatingSettings.RatedStrokeThickness=3;

{% endhighlight %}

![](images/ratedStrokeThickness.jpg)
 
### UnRated Fill

The UnRatedFill property fills the unrated area with the specified solid color in the SfRating control.

{% highlight C# %}

	sfRatingSettings.UnRatedFill=Color.GRAY;

{% endhighlight %}

![](images/unRatedFill.jpg)

### UnRated Stroke

The UnRatedStroke property sets the stroke for the unrated area with the specified solid color in the SfRating control.

{% highlight C# %}

	sfRatingSettings.UnRatedStroke=Color.BLACK;

{% endhighlight %}

![](images/unRatedStroke.jpg)

### UnRated Stroke Thickness

The UnRatedStrokeThickness property sets the stroke thickness for the unrated area with the specified value in the SfRating control.

{% highlight C# %}

	sfRatingSettings.UnRatedStrokeThickness=3;

{% endhighlight %}

![](images/unRatedStrokeThickness.jpg)
