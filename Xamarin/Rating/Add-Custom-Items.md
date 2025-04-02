---

layout: post
title: Custom View in Xamarin Rating control | Syncfusion
description: Learn here all about Custom View support in Syncfusion Xamarin Rating (SfRating) control, its elements and more.
platform: Xamarin
control: Rating 
documentation: ug

---

# Custom View in Xamarin Rating (SfRating)

[`SfRating`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html) Items control provides support to add custom views.

N> To use custom views in Xamarin.Forms UWP platform, you need to set [`ItemCount`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_ItemCount) value.

## Add SfRating items

To customize the view of rating items, create and set custom view as [`SelectedView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingItem.html#Syncfusion_SfRating_XForms_SfRatingItem_SelectedView) and [`UnSelectedView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingItem.html#Syncfusion_SfRating_XForms_SfRatingItem_UnSelectedView) of [`SfRatingItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingItem.html). Refer to the following code snippet to create a custom view.

{% tabs %}

{% highlight xaml %}

    <rating:SfRating EnableCustomView="true">
        <rating:SfRating.Items>
            <rating:SfRatingItem/>                
        </rating:SfRating.Items>
    </rating:SfRating>

{% endhighlight %}

{% highlight C# %}

SfRating rating= new SfRating();
SfRatingItem ratingItem = new SfRatingItem();
rating.Items = ratingItem;
rating.EnableCustomView = true;

{% endhighlight %}

{% endtabs %}

## Set selected view

The [`SelectedView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingItem.html#Syncfusion_SfRating_XForms_SfRatingItem_SelectedView) property is used to apply the given [`SelectedView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingItem.html#Syncfusion_SfRating_XForms_SfRatingItem_SelectedView)  to selected rating item.

{% tabs %}

{% highlight xaml %}

    <rating:SfRatingItem>
        <rating:SfRatingItem.SelectedView>
            <Image Source="Angry_selected.png"/>
        </rating:SfRatingItem.SelectedView>
    </rating:SfRatingItem>

{% endhighlight %}

{% highlight C# %}

ratingItem.SelectedView = new Image() { Source = "Angry_selected.png", Aspect = Aspect.Fill };

{% endhighlight %}

{% endtabs %}

## Set unselected view
 
The [`UnSelectedView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingItem.html#Syncfusion_SfRating_XForms_SfRatingItem_UnSelectedView) property is used to apply the given [`UnSelectedView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingItem.html#Syncfusion_SfRating_XForms_SfRatingItem_UnSelectedView) to unselected rating item.

{% tabs %}

{% highlight xaml %}

        <rating:SfRatingItem>
            <rating:SfRatingItem.UnSelectedView>
                <Image Source="Angry_Unselected.png"/>
            </rating:SfRatingItem.UnSelectedView>
        </rating:SfRatingItem>

{% endhighlight %}

{% highlight C# %}

ratingItem.UnSelectedView = new Image() { Source = "Angry_Unselected.png", Aspect = Aspect.Fill };

{% endhighlight %}

{% endtabs %}

## Add Items

The [`Items`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_Items) property is used to hold the collection of [`SfRatingItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingItem.html). 

N> [`SfRatingItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRatingItem.html) keeps both selected and unselected view respectively.

{% highlight C# %}

	ObservableCollection<SfRatingItem> ratingItemList = new ObservableCollection<SfRatingItem>();
	ratingItemList.Add(ratingItem);
	rating.Items = ratingItemList;

{% endhighlight %}

## Enable custom items

When the [`EnableCustomView`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfRating.XForms.SfRating.html#Syncfusion_SfRating_XForms_SfRating_EnableCustomView) property is enabled, the custom items added in the rating items will be displayed.

{% tabs %}

{% highlight xaml %}

    <rating:SfRating x:Name="rating" EnableCustomView="True" ItemCount="5">
        <rating:SfRating.Items>
            <collection:ObservableCollection x:TypeArguments="rating:SfRatingItem">
                <rating:SfRatingItem>
                    <rating:SfRatingItem.SelectedView>
                        <Image Source="Angry_selected.png"/>
                    </rating:SfRatingItem.SelectedView>
                    <rating:SfRatingItem.UnSelectedView>
                        <Image Source="Angry_Unselected.png"/>
                    </rating:SfRatingItem.UnSelectedView>
                </rating:SfRatingItem>
                <rating:SfRatingItem>
                    <rating:SfRatingItem.SelectedView>
                        <Image Source="UnHappy_selected.png"/>
                    </rating:SfRatingItem.SelectedView>
                    <rating:SfRatingItem.UnSelectedView>
                        <Image Source="UnHappy_Unselected.png"/>
                    </rating:SfRatingItem.UnSelectedView>
                </rating:SfRatingItem>
                <rating:SfRatingItem>
                    <rating:SfRatingItem.SelectedView>
                        <Image Source="Neutral_selected.png"/>
                    </rating:SfRatingItem.SelectedView>
                    <rating:SfRatingItem.UnSelectedView>
                        <Image Source="Neutral_Unselected.png"/>
                    </rating:SfRatingItem.UnSelectedView>
                </rating:SfRatingItem>
                <rating:SfRatingItem>
                    <rating:SfRatingItem.SelectedView>
                        <Image Source="Happy_selected.png"/>
                    </rating:SfRatingItem.SelectedView>
                    <rating:SfRatingItem.UnSelectedView>
                        <Image Source="Happy_Unselected.png"/>
                    </rating:SfRatingItem.UnSelectedView>
                </rating:SfRatingItem>
                <rating:SfRatingItem>
                    <rating:SfRatingItem.SelectedView>
                        <Image Source="Excited_selected.png"/>
                    </rating:SfRatingItem.SelectedView>
                    <rating:SfRatingItem.UnSelectedView>
                        <Image Source="Excited_Unselected.png"/>
                    </rating:SfRatingItem.UnSelectedView>
                </rating:SfRatingItem>
            </collection:ObservableCollection>
        </rating:SfRating.Items>
    </rating:SfRating>

{% endhighlight %}

{% highlight C# %}

SfRating rating;
public MainPage()
{
    InitializeComponent();
    rating = new SfRating();
    rating.EnableCustomView = true;
    rating.ItemCount = 5;
    SfRatingItem angry = new SfRatingItem();
    angry.SelectedView = new Image() { Source = "Angry_selected.png" };
    angry.UnSelectedView = new Image() { Source = "Angry_Unselected.png" };
    SfRatingItem unhappy = new SfRatingItem();
    unhappy.SelectedView = new Image() { Source = "UnHappy_selected.png" };
    unhappy.UnSelectedView = new Image() { Source = "UnHappy_Unselected.png" };
    SfRatingItem neutral = new SfRatingItem();
    neutral.SelectedView = new Image() { Source = "Neutral_selected.png" };
    neutral.UnSelectedView = new Image() { Source = "Neutral_Unselected.png" };
    SfRatingItem happy = new SfRatingItem();
    happy.SelectedView = new Image() { Source = "Happy_selected.png" };
    happy.UnSelectedView = new Image() { Source = "Happy_Unselected.png" };
    SfRatingItem excited = new SfRatingItem();
    excited.SelectedView = new Image() { Source = "Excited_selected.png" };
    excited.UnSelectedView = new Image() { Source = "Excited_Unselected.png" };
    ObservableCollection<SfRatingItem> ratingItemList = new ObservableCollection<SfRatingItem>();
    customItems.Add(angry);
    customItems.Add(unhappy);
    customItems.Add(neutral);
    customItems.Add(happy);
    customItems.Add(excited);
    rating.Items = ratingItemList;
    this.Content = rating;
}

{% endhighlight %}

{% endtabs %}

![Add custom view in Xamarin.Forms](images/CustomviewItems.png)
 

![Custom view SfRating](images/CustomviewItems.png)
