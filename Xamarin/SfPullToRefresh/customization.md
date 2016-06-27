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

    pullToRefresh.PullingThreshold = 225d;

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

   <ContentPage.Content>

    	<Grid x:Name="mainGrid" HeightRequest="100" >
			<Label x:Name="label" HorizontalOptions="FillAndExpand" VerticalOptions="FillAndExpand" BackgroundColor="#039be5"/>
			<Grid x:Name="SubGrid" BackgroundColor="Transparent">
				
				<Grid.RowDefinitions>
				<RowDefinition Height = "*"/>
				<RowDefinition Height="180"/>
			</Grid.RowDefinitions>
				
			<Grid x:Name="SubGrid1" Grid.Row="0">
	        <Grid.RowDefinitions>
				<RowDefinition Height = "0.10*"/>
				<RowDefinition Height = "0.15*"/>
				<RowDefinition Height = "0.15*"/>			
	            <RowDefinition Height = "0.40*"/>
				<RowDefinition Height = "0.05*"/>			
				<RowDefinition Height = "0.25*"/>
				<RowDefinition Height = "0.10*"/>
				<RowDefinition Height = "0.20*"/>

			</Grid.RowDefinitions>
			 <Label  Grid.Row="1" Text="MorrisVille" Font="15" VerticalOptions="FillAndExpand" HorizontalOptions="FillAndExpand" HorizontalTextAlignment="Center" TextColor="White"  >
			</Label>
		
     <Image    Grid.Row="3"  VerticalOptions="FillAndExpand" Aspect="AspectFit"  HorizontalOptions="FillAndExpand"  Source="{Binding Type}"  />
    <Label x:Name="label2" Grid.Row="5" Text="{Binding Temperature, StringFormat='{0}°/12'}" FontSize="45"  VerticalOptions="FillAndExpand" HorizontalTextAlignment="Center"  HorizontalOptions="FillAndExpand" TextColor="White">
            </Label>
			 <Label   Grid.Row="7" Text="{Binding Month}" VerticalOptions="FillAndExpand" HorizontalOptions="FillAndExpand" HorizontalTextAlignment="Center"  TextColor="White"    >
        </Label> 
       
			</Grid>
				<ScrollView  HeightRequest="180"   BackgroundColor="#007aaa"  HorizontalOptions="Fill" Grid.Row="1" Orientation = "Horizontal" VerticalOptions="End"   >

          <local:ViewExt WidthRequest="720" x:Name="ExtView" >

       <local:ViewExt.ItemTemplate >
       <DataTemplate>
      
         <Grid x:Name ="grid"  VerticalOptions="FillAndExpand" >
          <Grid.RowDefinitions>
									 <RowDefinition Height ="2"/>
          <RowDefinition Height ="20"/>
									 <RowDefinition Height ="10"/>
		  <RowDefinition Height ="60"/>
									 <RowDefinition Height ="10"/>
		  <RowDefinition Height ="20"/>
									
		   </Grid.RowDefinitions>
            <Label WidthRequest="100" Grid.Row="1" HorizontalOptions="FillAndExpand" VerticalOptions="FillAndExpand" VerticalTextAlignment="Center" HorizontalTextAlignment= "Center" FontSize= "14" TextColor="White"  Text="{Binding Day}"/>
            <Image  WidthRequest="40" Grid.Row="3" HorizontalOptions="FillAndExpand" VerticalOptions="FillAndExpand"  HeightRequest="42" x:Name="movieImage" Source="{Binding Type}" />
            <Label WidthRequest="100" Grid.Row="5" HorizontalOptions="FillAndExpand" VerticalOptions="FillAndExpand" VerticalTextAlignment="Center" HorizontalTextAlignment= "Center" FontSize= "14" TextColor="White"   Text="{Binding Temperature}"/>     
             </Grid>
       
         </DataTemplate>
       </local:ViewExt.ItemTemplate>
        </local:ViewExt>     
        </ScrollView>
	</Grid> 
	</Grid>
	</ContentPage.Content>

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

Refresh method is used to Refresh the `PullableContent` and also hides the `RefreshContent`.

{% highlight c# %}

    pullToRefresh.Refresh();

{% endhighlight %}

## Transition

The Transition property specifies the animations for the RefreshContent. Transition property has the following two options:

* `SlideOnTop`
* `Push`

The default transition is `SlideOnTop`. That draws the `RefreshContent` on top of the `PullableContent`.

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

The default PullDirection is `Top`. That draws the `RefreshContent` on top of the `PullableContent`.

{% tabs %}

{% highlight C# %}

    pullToRefresh.PullDirection=PullDirection.Top;


{% endhighlight %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name=" pullToRefresh" PullDirection="Top" />

{%endhighlight%}


{% endtabs %}


The following code example shows how to set `PullDirection` as `Bottom` to SfPullToRefresh.That draws the `RefreshContent` on Bottom of the `PullableContent`.

{% tabs %}

{% highlight C# %}

    pullToRefresh.PullDirection=PullDirection.Bottom;

{% endhighlight %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name=" pullToRefresh" PullDirection="Bottom" />

{%endhighlight%}

{% endtabs %}
