---
layout: post
title: Syncfusion ParallaxView customization in Xamarin.Forms
description: How to customize the scrolling speed of the content added as a background view and content orientation.
platform: xamarin.forms
control: SfParallaxView
documentation: ug
---

## Customize the parallax view

### Speed

The `Speed` value denotes the scrolling speed of the `Content` added as a background view. Based on the speed value, the background view will scroll along with the foreground view.

{% highlight xaml %}

     <parallax:SfParallaxView Source="{x:Reference Name = listview}" x:Name="parallaxview" Speed="0.5" >
            <parallax:SfParallaxView.Content>
                <Image BackgroundColor="Transparent" Source="{Binding Image}" HorizontalOptions="Fill" VerticalOptions="Fill" Aspect="AspectFill" />
            </parallax:SfParallaxView.Content>
     </parallax:SfParallaxView>

{% endhighlight %}

### Orientation 

The `Orientation` of the content scrolling can be customized to vertical or horizontal using this property's value.

{% highlight xaml %}

        <Grid>
          <parallax:SfParallaxView Source="{x:Reference Name = listview}" x:Name="parallaxview" Orientation="Horizontal" >
            <parallax:SfParallaxView.Content>
               
                . . .

            </parallax:SfParallaxView.Content>
          </parallax:SfParallaxView>
     
        <list:SfListView x:Name="listview" Orientation="Horizontal" ItemsSource="{Binding Items}" BackgroundColor="Transparent" ItemSize="100">
               
                    . . .

        </list:SfListView>
        </Grid>
        
{% endhighlight %}