---
layout: post
title: Getting Started with syncfusion SfPullToRefresh control for Xamarin.Forms 
description:  A quick tour to initial users on Syncfusion SfPullToRefresh control for Xamarin.Forms platform
platform: Xamarin.Forms 
control: PullToRefresh
documentation: ug
---


# Getting Started

This section explains you the steps to configure a SfPulloRefresh control in a real-time scenario and also provides a walk-through on some of the customization features available in PullToRefresh control.

## Reference Essential Studio Components in your solution

If you had acquired Essential Studio components through the Xamarin component store interface from within your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and Windows Phone projects through the Component manager, you will still need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside of your solution folder.

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
<td>iOS (Classic)</td>
<td>ios\Syncfusion.SfPullToRefresh.iOS.dll<br/>ios\Syncfusion.SfPullToRefresh.XForms.iOS.dll<br/>ios\Syncfusion.SfPullToRefresh.XForms.dll</td>
</tr>
<tr>
<td>iOS (Unified)</td>
<td>ios-unified\Syncfusion.SfPullToRefresh.iOS.dll<br/>ios-unified\Syncfusion.SfPullToRefresh.XForms.iOS.dll<br/>ios-unified\Syncfusion.SfPullToRefresh.XForms.dll</td>
</tr>
<tr>
<td>WindowsPhone</td>
<td>wp8\Syncfusion.SfPullToRefresh.XForms.dll<br/>wp8\Syncfusion.SfPullToRefresh.XForms.WinPhone.dll<br>wp8\Syncfusion.SfPullToRefresh.WP8.dll</td>
</tr>
<tr>
<td>WindowsPhone 8.1</td>
<td>wp81\Syncfusion.SfPullToRefresh.XForms.dll<br/>wp81\Syncfusion.SfPullToRefresh.XForms.WinPhone.dll<br>wp81\Syncfusion.SfPullToRefresh.WP.dll</td>
</tr>
<tr>
<td>WinRT</td>
<td>winrt\Syncfusion.SfPullToRefresh.XForms.dll<br/>winrt\Syncfusion.SfPullToRefresh.XForms.WinRT.dll<br>wp81\Syncfusion.SfPullToRefresh.WinRT.dll</td>
</tr>
</table>

# Intialization

## Create your first SfPullToRefresh in Xamarin.Forms

Refer to the following code to add the SfPullToRefresh control:


{% tabs %}

{%highlight Xaml%}

    <Page
    x:Class="PullToRefresh.MainPage"
    xmlns:syncfusion="using:Syncfusion.UI.Xaml.PullToRefresh">

    <Grid x:Name="LayoutRoot">
        <syncfusion:SfPullToRefresh />
    </Grid> 
    
    </Page>

{%endhighlight%}

{% highlight c# %}

    SfPullToRefresh pullToRefresh = new SfPullToRefresh();

{% endhighlight %}

{% endtabs %}


## Customizing a simple SfPullToRefresh sample

To develop an application with Xamarin PullToRefresh is simple. The following steps explains how to create and configure its properties.


* Create the `PullableContent` for the `SfPullToRefresh`

You can set the `PullableContent` for the `SfPullToRefresh` by adding the desired UIElement.

{% tabs %}

{%highlight Xaml%}

    <syncfusion:SfPullToRefresh x:Name="pullToRefresh" PullingThreshold="150" >
        <syncfusion:SfPullToRefresh.PullableContent>
            <Grid Background="#039be5" Name="controlView" >
            </Grid>
        </syncfusion:SfPullToRefresh.PullableContent>
    </syncfusion:SfPullToRefresh>


{%endhighlight%}
{% endtabs %}
