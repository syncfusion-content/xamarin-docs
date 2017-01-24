---
layout: post
title: Concepts and Features | PullToRefresh | Xamarin.Forms | Syncfusion
description: concepts and features
platform: Xamarin.Forms
control: PullToRefresh
documentation: ug
--- 

# Concepts and Features

## PullingThreshold

Gets or sets the threshold value from the edges for easy panning from the edges. The default value of TouchThreshold is 3 times the RefreshContentHeight.

{% tabs %}

{% highlight c# %}

    pullToRefresh.PullingThershold = 225d;

{% endhighlight %}

{% endtabs %} 

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfPullToRefresh x:Name="pullToRefresh" PullingThreshold="225"/>

{%endhighlight%} 

{% endtabs %}


## PullableContent

PullableContent is the main view of the PullToRefresh control on which the desired items can be placed.

{%highlight Xaml%}

   <syncfusion:SfPullToRefresh  x:Name="pullToRefresh" TransitionMode="Push" PullingThershold="250">
        <syncfusion:SfPullToRefresh.PullableContent>                 
             <Grid BackgroundColor="#039be5">
                <Grid.RowDefinitions>
					<RowDefinition/>
					<RowDefinition/>
				</Grid.RowDefinitions>
				<Label FontSize="25" TextColor="White" HorizontalTextAlignment="Center" VerticalTextAlignment="Center" Text = "Temperature"/>
				<Label FontSize="35"  TextColor="White" HorizontalTextAlignment="Center" VerticalTextAlignment="Start" x:Name="tempLabel" Grid.Row="1" Text = "{Binding Temp}"/>
			</Grid>
		</syncfusion:SfPullToRefresh.PullableContent>
   </syncfusion:SfPullToRefresh>

{%endhighlight%}


## RefreshContentHeight

`RefreshContentHeight` sets the height of the refresh content.

{% tabs %}

{% highlight c# %}

    pullToRefresh.RefreshContentHeight = 200d;

{% endhighlight %}

{% endtabs %}

{% tabs %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name="pulltorefresh" RefreshContentHeight="200"/>

{%endhighlight%}

{% endtabs %}



## Refresh ()

Refresh method is used to Refresh the `pullableContent` and also hides the `RefreshContent`.

{% highlight c# %}

    pullToRefresh.Refresh();

{% endhighlight %}

## Transition

The Transition property specifies the animations for the RefreshContent. Transition property has the following two options:

* `SlideOnTop`
* `Push`

The default transition is `SlideOnTop`. That draws the `RefreshContent` on top of the `pullableContent`.

{% tabs %}

{% highlight c# %}

    pullToRefresh.Transition = Transition.SlideOnTop;

{% endhighlight %}


{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name="pullToRefresh" Transition="SlideOnTop" />

{%endhighlight%}

{% endtabs %}

![](overview_images/img1.png)


The following code example shows how to set `Transition` as `Push` to SfPullToRefresh. This transition moves the refresh content and main content simultaneously.

{% tabs %}

{% highlight c# %}

    pullToRefresh.Transition = Transition.Push;

{% endhighlight %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name=" pullToRefresh" Transition="Push" />

{%endhighlight%}

{% endtabs %}

## PullDirection

PullDirection property specifies the position of the transition to take place.PullDirection property has the following two options:
* `Top`
* `Bottom`

The default PullDirection is `Top`. That draws the `RefreshContent` on top of the `pullableContent`.

{% tabs %}

{% highlight C# %}

    pullToRefresh.PullDirection=PullDirection.Top;


{% endhighlight %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name=" pullToRefresh" PullDirection="Top" />

{%endhighlight%}


{% endtabs %}


The following code example shows how to set `PullDirection` as `Bottom` to SfPullToRefresh.That draws the `RefreshContent` on Bottom of the `pullableContent`.

{% tabs %}

{% highlight C# %}

    pullToRefresh.PullDirection=PullDirection.Bottom;

{% endhighlight %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name=" pullToRefresh" PullDirection="Bottom" />

{%endhighlight%}

{% endtabs %}


## StartRefreshing()

StartRefreshing method is used to refresh the content without interaction in pullable content.When invoke this StartRefreshing() method,then Progress indicator will be shown with progress value. 

{% tabs %}

{% highlight C# %}

    pullToRefresh.StartRefreshing();

{% endhighlight %}

{% endtabs %}


## EndRefreshing()

EndRefreshing method is used to stop or end up the animation of refreshing method.

{% tabs %}

{% highlight C# %}

    pullToRefresh.EndRefreshing();

{% endhighlight %}

{% endtabs %}


## IsRefreshing()

IsRefreshing property indicates pulltorefresh state is in refreshing state or not.It returns the boolean value either true or false.
 
{% tabs %}

{% highlight C# %}

    if(pullToRefresh.IsRefreshing())
     {

     }


{% endhighlight %}

{% endtabs %}


## Progress

progress property specifies progress value set by the user for progress indicator.
 
{% tabs %}

{% highlight C# %}

    pullToRefresh.Progress = 10;

{% endhighlight %}


{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name=" pullToRefresh" Progress="10" />

{%endhighlight%}


{% endtabs %}
