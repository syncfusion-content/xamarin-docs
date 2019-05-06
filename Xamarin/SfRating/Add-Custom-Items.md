---

layout: post
title: Adding Custom items in Syncfusion Rating control for Xamarin.Forms
description: Learn how to add the Custom Items in rating control
platform: Xamarin
control: Rating 
documentation: ug

---

# Custom Views

SfRating Items control provides support to add custom views.

## Add SfRating Items

The SfRating Items control is configured entirely in C# code. Add the SfRating Items control with a required optimal name by using the included namespace.

{% highlight C# %}

SfRating rating= new SfRating();

SfRatingItem item = new SfRatingItem();

{% endhighlight %}

## Set Selected View
 
The `SelectedView` property is used to apply the given SelectedView to selected rating item.

{% highlight C# %}

item.SelectedView = new Image() { Source = "Angry_selected.png", Aspect = Aspect.Fill };

{% endhighlight %}

## Set UnSelected View
 
The `UnSelectedView` property is used to apply the given UnSelectedView to unselected rating item.

{% highlight C# %}

item.UnSelectedView = new Image() { Source = "Angry_Unselected.png", Aspect = Aspect.Fill };

{% endhighlight %}

## Add Items

The `Items` property is used to hold the collection of SfRatingItem. 

N> SfRatingItem keeps both selected and unselected view respectively.

{% highlight C# %}

	ObservableCollection<SfRatingItem> customItems = new ObservableCollection<SfRatingItem>();
	customItems.Add(item);
	rating.Items = customItems;

{% endhighlight %}

## Enable Custom Items

When `EnableCustomItems` property is enabled, it will display the custom items added in the rating items. 


{% highlight C# %}
	
	SfRating rating= new SfRating();
	SfRatingItem item = new SfRatingItem();
        	item.SelectedView = new Image() { Source = "Angry_selected.png", Aspect = Aspect.Fill };
        	item.UnSelectedView = new Image() { Source = "Angry_Unselected.png", Aspect = Aspect.Fill };
	SfRatingItem item1 = new SfRatingItem();
		item1.SelectedView = new Image() { Source = "UnHappy_selected.png", Aspect = Aspect.Fill };
		item1.UnSelectedView = new Image() { Source = "UnHappy_Unselected.png", Aspect = Aspect.Fill };
	SfRatingItem item2 = new SfRatingItem();
		item2.SelectedView = new Image() { Source = "Neutral_selected.png", Aspect = Aspect.Fill };
		item2.UnSelectedView = new Image() { Source = "Neutral_Unselected.png", Aspect = Aspect.Fill };
	SfRatingItem item3 = new SfRatingItem();
		item3.SelectedView = new Image() { Source = "Happy_selected.png", Aspect = Aspect.Fill };
		item3.UnSelectedView = new Image() { Source = "Happy_Unselected.png", Aspect = Aspect.Fill };
	SfRatingItem item4 = new SfRatingItem();
		item4.SelectedView = new Image() { Source = "Excited_selected.png", Aspect = Aspect.Fill };
		item4.UnSelectedView = new Image() { Source = "Excited_Unselected.png", Aspect = Aspect.Fill };
	ObservableCollection<SfRatingItem> customItems = new ObservableCollection<SfRatingItem>();
            customItems.Add(item);
            customItems.Add(item1);
            customItems.Add(item2);
            customItems.Add(item3);
            customItems.Add(item4);
	rating.Items = customItems;
	rating.EnableCustomView = true;

{% endhighlight %}

![Add custom view in Xamarin.Forms](images/CustomviewItems.png)
 




 
