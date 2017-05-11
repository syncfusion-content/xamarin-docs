---
layout: post
title: Styles | SfPullToRefresh | Xamarin | Syncfusion
description: How to customize the SfPullToRefresh Control Styles.
platform: xamarin
control: SfPullToRefresh
documentation: UG
---

# Features

## PullableContent

Gets or sets the content of the refresh view. `PullableContent` is the main view of the `SfPullToRefresh` control on which the desired items can be placed.

{%highlight Xaml%}

  <syncfusion:SfPullToRefresh x:Name="pullToRefresh"
                                    IsRefreshing="False" 
                                    TransitionMode="SlideOnTop" 
                                    ProgressBackgroundColor="White"
                                    ProgressStrokeWidth="3" 
                                    ProgressStrokeColor="Blue"
                                    PullingThershold="120"
                                    RefreshContentHeight="30"
                                    RefreshContentThreshold="30"
                                    RefreshContentWidth="30">
            <syncfusion:SfPullToRefresh.PullableContent>
                    <Label x:Name="Monthlabel" TextColor="White" HorizontalTextAlignment="Center" VerticalTextAlignment="Start" />
            </syncfusion:SfPullToRefresh.PullableContent>
        </syncfusion:SfPullToRefresh>

{%endhighlight%}

## TransitionMode

The `TransitionMode` property specifies the mode of the animations. It has the following two modes:

* `SlideOnTop`
* `Push`

The default transition is `SlideOnTop` that draws the RefreshContent on top of the `PullableContent`.

{% tabs %}

{% highlight c# %}

    pullToRefresh.TransitionMode = TransitionType.SlideOnTop;

{% endhighlight %}


{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name="pullToRefresh" TransitionMode="SlideOnTop" />

{%endhighlight%}

{% endtabs %}

![](overview_images/SlideOnTop.png)

The following code example shows how to set `TransitionMode` as `Push` to SfPullToRefresh. This transition moves the refresh content and main content simultaneously.

{% tabs %}

{% highlight c# %}

    pullToRefresh.TransitionMode = TransitionType.Push;

{% endhighlight %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name=" pullToRefresh" TransitionMode="Push" />

{%endhighlight%}

{% endtabs %}

![](overview_images/Push.png)

## RefreshContentThreshold

Gets or sets the refresh content threshold value that indicates progress indicator starting position in view

{% tabs %}

{% highlight c# %}

    pullToRefresh.RefreshContentThreshold = 50d;

{% endhighlight %}

{% endtabs %} 

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfPullToRefresh x:Name="pullToRefresh" RefreshContentThreshold="50"/>

{%endhighlight%} 

{% endtabs %}

## PullingThershold

Gets or sets the value for the refresh content threshold, this indicate progress indicator maximum pulling position in view.

{% tabs %}

{% highlight c# %}

    pullToRefresh.PullingThershold = 200d;

{% endhighlight %}

{% endtabs %} 

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfPullToRefresh x:Name="pullToRefresh" PullingThreshold="200"/>

{%endhighlight%} 

{% endtabs %}


## IsRefreshing

Get or set the state for refreshing the view. View will get refresh while `IsRefreshing` property is set `true` and View refreshing will be stopped when you set `IsRefreshing` is `false`.
 
{% tabs %}

{% highlight c# %}

    pullToRefresh.IsRefreshing = true;

{% endhighlight %}

{% endtabs %} 

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfPullToRefresh x:Name="pullToRefresh" IsRefreshing = "True"/>

{%endhighlight%} 

{% endtabs %}

## ProgressBackgroundColor

Get or set the background color to the progress indicator.

{% tabs %}

{% highlight c# %}

    pullToRefresh.ProgressBackgroundColor = Color.White;

{% endhighlight %}

{% endtabs %} 

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfPullToRefresh x:Name="pullToRefresh" ProgressBackgroundColor = "White"/>

{%endhighlight%} 

{% endtabs %}

## ProgressStrokeColor

Get or set the color to the progress indicator stroke 

{% tabs %}

{% highlight c# %}

    pullToRefresh.ProgressStrokeColor = Color.Blue;

{% endhighlight %}

{% endtabs %} 

{% tabs %}

{% highlight xaml %}

    <syncfusion:SfPullToRefresh x:Name="pullToRefresh" ProgressStrokeColor = "Blue"/>

{%endhighlight%} 

{% endtabs %}

## ProgressStrokeWidth

Get or set the width to the progress indicator stroke. 

{% tabs %}

{% highlight c# %}

    pullToRefresh.ProgressStrokeWidth = 5d;

{% endhighlight %}

{% endtabs %}

{% tabs %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name="pulltorefresh" ProgressStrokeWidth="5"/>

{%endhighlight%}

{% endtabs %}

## RefreshContentWidth

Get or set the width to the refresh content.

{% tabs %}

{% highlight c# %}

    pullToRefresh.RefreshContentWidth = 50d;

{% endhighlight %}

{% endtabs %}

{% tabs %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name="pulltorefresh" RefreshContentWidth="50"/>

{%endhighlight%}

{% endtabs %}

## RefreshContentHeight

Get or set the width to the refresh content.

{% tabs %}

{% highlight c# %}

    pullToRefresh.RefreshContentHeight = 50d;

{% endhighlight %}

{% endtabs %}

{% tabs %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name="pulltorefresh" RefreshContentHeight="50"/>

{%endhighlight%}

{% endtabs %}

## Programmatic Support 

### StartRefreshing()

StartRefreshing method is used to refresh the content without interaction in pullable content. When invoke this StartRefreshing() method,then Progress indicator will be shown. 

{% tabs %}

{% highlight C# %}

    pullToRefresh.StartRefreshing();

{% endhighlight %}

{% endtabs %}


### EndRefreshing()

EndRefreshing method is used to ends the progress animation of `SfPullToRefresh`.

{% tabs %}

{% highlight C# %}

    pullToRefresh.EndRefreshing();

{% endhighlight %}

{% endtabs %}


