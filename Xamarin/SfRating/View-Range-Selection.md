---

layout: post
title: Range selection in Syncfusion SfRating for Xamarin.Forms
description: Perform range selection with custom views in rating control
platform: Xamarin
control: Rating
documentation: ug

---

# View Range Selection

When using CustomView in SfRating, Only one item will be rated. If you need to change the view of all rated CustomView items, Use the `EnableViewRangeSelection` boolean property.

N> The EnableViewRangeSelection property is used only for CustomViews. 

{% tabs %}

{% highlight xaml %}

	<rating:SfRating x:Name="rating" EnableCustomView="True" ItemCount="5" EnableViewRangeSelection="True" />
	
{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainPage()
{
    InitializeComponent();
    -------

    rating.EnableCustomView = true;
    rating.EnableViewRangeSelection = true;
    
    -------
}

{% endhighlight %}

{% endtabs %}

![SfRating EnableViewRangeSelection](images/enableviewrangeselection.png)
