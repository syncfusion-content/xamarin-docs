---
layout: post
title: Customization in Xamarin Cards control | Syncfusion<sup>&reg;</sup>
description: Learn about Customization support in Syncfusion<sup>&reg;</sup> Essential Studio<sup>&reg;</sup> Xamarin Cards control, its elements and more.
platform: xamarin
control: Cards
documentation: ug
---

# Customization in Xamarin Cards

### ShowSwipedCard

ShowSwipedCard can be enabled to show the swiped cards at the edge of card layout.

{% tabs %} 

{% highlight xaml %}

<cards:SfCardLayout ShowSwipedCard="true">
</cards:SfCardLayout>
 
{% endhighlight %}

{% highlight C# %}

SfCardLayout cardLayout = new SfCardLayout()
{
  ShowSwipedCard = true
};

{% endhighlight %}

{% endtabs %}

![ShowSwipedCard in Xamarin.Forms SfCardLayout](cardlayout-customization_images/showswipedcard.png)

### VisibleCardIndex

VisibleCardIndex is used when given index of the card to be displayed in front of the card layout.

{% tabs %} 

{% highlight xaml %}

<cards:SfCardLayout VisibleCardIndex="1">
</cards:SfCardLayout>
 
{% endhighlight %}

{% highlight C# %}

SfCardLayout cardLayout = new SfCardLayout()
{
  VisibleCardIndex = 1
};

{% endhighlight %}

{% endtabs %}

![VisibleCardIndex in Xamarin.Forms SfCardLayout](cardlayout-customization_images/showswipedcard.png)

### SwipeDirection

The SwipeDirection property indicates the swiping direction (left or right).

{% tabs %} 

{% highlight xaml %}

<cards:SfCardLayout SwipeDirection="Right">
</cards:SfCardLayout>
 
{% endhighlight %}

{% highlight C# %}

SfCardLayout cardLayout = new SfCardLayout()
{
    SwipeDirection = CardSwipeDirection.Right
};


{% endhighlight %}

{% endtabs %}

![SwipeDirection in Xamarin.Forms SfCardLayout](cardlayout-customization_images/swipedirection.png)

You can find the complete getting started sample from this [link](https://github.com/SyncfusionExamples/Getting-started-sample-of-cards).

## Customization in CardView

You can customize the border color, thickness, and card corner radius by using the following properties:

[BorderColor](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Cards.SfCardView.html#Syncfusion_XForms_Cards_SfCardView_BorderColor) - Used to customize the card view border color.

[BorderWidth](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Cards.SfCardView.html#Syncfusion_XForms_Cards_SfCardView_BorderWidth) - Used to customize the card view border thickness.

[CornerRadius](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Cards.SfCardView.html#Syncfusion_XForms_Cards_SfCardView_CornerRadius) - Used to customize the card view corner radius.

{% tabs %} 

{% highlight xaml %}

    <StackLayout  HorizontalOptions="Center" VerticalOptions="Center">
        <cards:SfCardView BorderColor="Black" BorderWidth="5" CornerRadius="30,0,30,0" BackgroundColor="LightPink"  >
            <StackLayout Padding="10, 10, 0, 0" >
             <Label  Text="New York" FontSize="25" />
            <Label Text="Mon 3.00PM, Sunny" TextColor="Gray"/>
            <StackLayout Orientation="Horizontal">
                <Label Text="31°" FontSize="70" Padding="0, 0, 10,0"/>
                <Image  Source="Sun.png" HeightRequest="100" WidthRequest="100"/>
            </StackLayout>
        </StackLayout>
     </cards:SfCardView>
  </StackLayout>

{% endhighlight %}

{% highlight C# %}

        StackLayout mainStack = new StackLayout()
            {
                HorizontalOptions = LayoutOptions.Center,
                VerticalOptions = LayoutOptions.Center,
                Children =
                {
                    new SfCardView(){
                    Content =  new StackLayout()
                    {
                        Padding = new Thickness(10, 10, 0, 0),
                        Children =
                        {
                            new Label(){Text = "New York" , FontSize = 25},
                            new Label(){Text = "Mon 3.00PM, Sunny" , TextColor = Color.Gray},
                            new StackLayout()
                            {
                                Orientation  = StackOrientation.Horizontal,
                                Children =
                                {
                                    new Label(){Text = "31°" , FontSize = 70, Padding = new Thickness(0,0,10,0) },
                                    new Image(){Source = "Sun.png", HeightRequest = 100, WidthRequest = 100}
                                }
                            }
                        }
                    },
                    BorderColor = Color.Black,
                    BorderWidth = 5,
                    CornerRadius = new Thickness(30, 0, 30, 0),
                    BackgroundColor = Color.LightPink
                    }
                }
            };
           
{% endhighlight %}

{% endtabs %}

![Card customization in Xamarin.Forms SfCardLayout](cardview-customization_images/card_Customization.PNG)

### Indicator customization

Indicators are used to indicate the state or level of something.

{% tabs %} 

{% highlight xaml %}

    <cards:SfCardView IndicatorColor="Cyan" HeightRequest="300" IndicatorThickness="12" IndicatorPosition="Left" >
            <Label  Text="SfCardView" VerticalTextAlignment="Center" HorizontalTextAlignment="Center"/>
        </cards:SfCardView>

{% endhighlight %}

{% highlight C# %}

SfCardView cardView = new SfCardView() 
{     
    Content = new Label() 
    { 
        Text = "SfCardView", 
        HorizontalTextAlignment = TextAlignment.Center, 
        VerticalTextAlignment =  TextAlignment.Center
    },
    IndicatorThickness = 12,
    HeightRequest = 300,
    IndicatorPosition = IndicatorPosition.Left,
    IndicatorColor = Color.Cyan
};
           

{% endhighlight %}

{% endtabs %}

![Indicator in Xamarin.Forms SfCardLayout](cardview-customization_images/indicator.png)

### FadeOutOnSwiping

FadeOutOnSwiping can be enabled when the card view needs to be faded with respect to swiping.

{% tabs %} 

{% highlight xaml %}

    <cards:SfCardView FadeOutOnSwiping="true"/>
 
{% endhighlight %}

{% highlight C# %}

SfCardView cardView = new SfCardView()
{
  FadeOutOnSwiping = true
};

{% endhighlight %}

{% endtabs %}

N> This property won't work when adding the SfCardView as a child of SfCardLayout.

## Shadow Effect

The `CardView` control provides shadow effect support. To enable shadow effect, set the `HasShadow` property to `true`.

You can customize the color of shadow using the `ShadowColor` property.

{% tabs %} 

{% highlight xaml %}

<cards:SfCardView HeightRequest="300" HasShadow="True" ShadowColor="Red">
    <Label  Text="LightGray" BackgroundColor="LightGray"/>
</cards:SfCardView>


{% endhighlight %}

{% highlight C# %}

 SfCardView sfCardView = new SfCardView() 
 { 
   Content = new Label() { Text = "LightGray", BackgroundColor = Color.LightGray },
   HasShadow = true,
   ShadowColor = Color.Red
 };


{% endhighlight %}

{% endtabs %}

N> This property will not work when adding the `SfCardView` as a child of `SfCardLayout`.


## See also

[How to remove cards from card view collection in Xamarin.Forms](https://support.syncfusion.com/kb/article/10208/how-to-remove-cards-from-card-view-collection-in-xamarinforms-cardlayout)

[How to add multicolored stack of cards in Xamarin.Forms](https://support.syncfusion.com/kb/article/10212/how-to-add-multicolored-stack-of-cards-in-xamarinforms)

[How to set shadow effect to the cards in Xamarin.Forms](https://support.syncfusion.com/kb/article/10204/how-to-set-shadow-effect-to-the-cards-in-xamarin-forms)

[How to add cards to the ListView in Xamarin.Forms](https://support.syncfusion.com/kb/article/10203/how-to-add-cards-to-the-listview-in-xamarin-forms)

[How to set the border color and width of a card within the SfCardLayout](https://support.syncfusion.com/kb/article/10239/how-to-set-the-border-color-and-width-of-a-card-within-the-cardlayout)

[How to reuse the dismissed cards in Xamarin.Forms SfCardView](https://support.syncfusion.com/kb/article/10201/how-to-reuse-the-dismissed-cards-in-xamarin-forms-sfcardview)
