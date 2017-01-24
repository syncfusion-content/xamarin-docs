---
layout: post
title: Getting Started with syncfusion SfPullToRefresh control for Xamarin.Forms 
description:  A quick tour to initial users on Syncfusion SfPullToRefresh control for Xamarin.Forms platform
platform: Xamarin.Forms 
control: PullToRefresh
documentation: ug
---


# Getting Started

This section explains you the steps to configure a SfPullToRefresh control in a real-time scenario and also provides a walk-through on some of the customization features available in PullToRefresh control.

## Reference Essential Studio Components in your solution

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and UWP projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.

Components/syncfusionessentialstudio-version/lib/pcl/

Alternatively if you had downloaded Essential Studio from Syncfusion.com or through the Xamarin store web interface then all assembly references need to be added manually.

After installing Essential Studio for Xamarin, all the required assemblies can be found in the installation folders, typically

{Syncfusion Installed location}\Essential Studio\syncfusionessentialstudio-version\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\lib

Or after downloading through the Xamarin store web interface, all the required assemblies can be found in the below folder

{Download location}\syncfusionessentialstudio-version\lib

You can then add the assembly references to the respective projects as shown below

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>PCL</td>
<td>pcl\Syncfusion.SfPullToRefresh.XForms.dll</td>
</tr>
<tr>
<td>Android</td>
<td>android\Syncfusion.SfPullToRefresh.Android.dll<br/>android\Syncfusion.SfPullToRefresh.XForms.Android.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>iOS-unified\Syncfusion.SfPullToRefresh.iOS.dll<br/>iOS-unified\Syncfusion.SfPullToRefresh.XForms.iOS.dll<br/>iOS-unified\Syncfusion.SfPullToRefresh.XForms.dll</td>
</tr>
<tr>
<td>UWP</td>
<td>uwp\Syncfusion.SfInput.UWP.dll<br/>uwp\Syncfusion.SfShared.UWP.dll<br/>uwp\Syncfusion.SfAutoComplete.XForms.dll<br/>uwp\Syncfusion.SfAutoComplete.XForms.UWP.dll</td>
</tr>
</table>

# Initialization

## Create your first SfPullToRefresh in Xamarin.Forms

Refer to the following code to add the SfPullToRefresh control:


{% tabs %}

{%highlight Xaml%}

    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
        xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
        xmlns:Syncfusion="clr-namespace:Syncfusion.SfPullToRefresh.XForms;assembly=Syncfusion.SfPullToRefresh.XForms">

            <Grid x:Name="LayoutRoot">
                    <Syncfusion:SfPullToRefresh />
            </Grid> 
    </ContentPage>

{%endhighlight%}

{% highlight c# %}

    SfPullToRefresh pullToRefresh = new SfPullToRefresh();
    this.Content = pullToRefresh;

{% endhighlight %}

{% endtabs %}


## Customizing a simple SfPullToRefresh sample

To develop an application with Xamarin PullToRefresh is simple. The following steps explains how to create and configure its properties.


* Create the `pullableContent` for the `SfPullToRefresh`

You can set the `pullableContent` for the `SfPullToRefresh` by adding the desired UIElement.

{% tabs %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name="pullToRefresh" PullingThershold="150" >
        <syncfusion:SfPullToRefresh.PullableContent>
            <Grid BackgroundColor="#039be5" Name="controlView" >
            </Grid>
        </syncfusion:SfPullToRefresh.PullableContent>
    </syncfusion:SfPullToRefresh>


{%endhighlight%}
{% endtabs %}

## Events

The pulling event will be notified whenever the swipe gesture is started. This event will notify the listener each and every time until the refresh content height exceeds. When we release the gesture from pullable content, Refreshing event will be triggered. Now user can proceed to fetching the data from web or database. Once the data is fetched, we should call Refresh to method to complete all animations.

There are three built-in events in the PullToRefresh control namely:

1. `Pulling`
2. `Refreshing`
3. `Refreshed`

### Pulling

`Pulling` event is triggered when we start pulling down the pullableContent. It is triggered as long as the pointer or finger is pressed and the progress is less than 100 and not equal to 0 . The arguments for the event are:

* SfPullToRefresh
* Progress

{% tabs %}

{% highlight c# %}
   pulltorefresh.PullingEvent +=pullToRefresh_ Pulling;

   void pullToRefresh_ Pulling(object sender,SfPullToRefresh.PullingEventArgs args) 
		{ 
		
	
		
		}
   		
{% endhighlight %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name="pullToRefresh" PullingEvent="pullToRefresh_Pulling" />

{%endhighlight%}

{% endtabs %}

### Refreshing

`Refreshing` event is triggered once the content is pulled through the PullingThreshold or Progress reaches 100. This event is triggered till the Refresh() method is called.

{% tabs %}

{% highlight c# %}

    pullToRefresh.RefreshingEvent+= pullToRefresh_Refreshing;
   
    void pullToRefresh_Refreshing(object sender)
        {

        }


{% endhighlight %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name="pullToRefresh" RefreshingEvent="pullToRefresh_Refreshing" />

{%endhighlight%}


{% endtabs %}

### Refreshed

`Refreshed` event is triggered once the refreshing and all the animations associated with the control are completed.

{% tabs %}


{% highlight c# %}

    pullToRefresh.RefreshedEvent += Pull_pullToRefreshedEvent;
    void Pull_pullToRefreshedEvent (object sender)
		{

         Device.StartTimer(new TimeSpan(0, 0, 2), () =>
				{
                      pulltorefresh.Refresh();
					  return false;
				  });
				
		}

{% endhighlight %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name=" pullToRefresh" RefreshedEvent="Pull_pullToRefreshedEvent" />

{%endhighlight%}

{% endtabs %}