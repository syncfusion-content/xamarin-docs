---
layout: post
title: Getting started | SfPullToRefresh | Xamarin | Syncfusion
description: Getting started with SfPullToRefresh.
platform: xamarin
control: SfPullToRefresh
documentation: ug
---

# Getting Started

This section provides a quick overview for working with SfPullToRefresh for Xamarin.Forms.

## Assembly deployment

After installing Essential Studio for Xamarin, you can find all the required assemblies in the installation folders,

{Syncfusion Essential Studio Installed location}\Essential Studio\{{ site.releaseversion }}\Xamarin\lib

Eg: C:\Program Files (x86)\Syncfusion\Essential Studio\{{ site.releaseversion }}\Xamarin\lib

N> Assemblies can be found in unzipped package location in Mac

### SfPullToRefresh for Xamarin.Forms

The following list of assemblies need to be added as reference from the lib folder to use SfPullToRefresh in your application.

<table>
<tr>
<th>Project</th>
<th>Required assemblies</th>
</tr>
<tr>
<td>PCL</td>
<td>pcl\Syncfusion.Core.XForms.dll<br/>pcl\Syncfusion.SfPullToRefresh.XForms.dll<br/></td>
</tr>
<tr>
<td>Android Renderer</td>
<td>pcl\Syncfusion.SfPullToRefresh.XForms.dll<br/>android\Syncfusion.SfPullToRefresh.XForms.Android.dll<br/></td>
</tr>
<tr>
<td>iOS Renderer</td>
<td>pcl\Syncfusion.SfPullToRefresh.XForms.dll<br/>ios-unified\Syncfusion.SfPullToRefresh.XForms.iOS.dll<br/></td>
</tr>
<tr>
<td>UWP Renderer</td>
<td>pcl\Syncfusion.Core.XForms.dll<br/>pcl\Syncfusion.SfPullToRefresh.XForms.dll<br/>uwp\Syncfusion.SfPullToRefresh.XForms.UWP.dll<br/></td>
</tr>
</table>

N> When there is a mismatch of Xamarin NuGet packages between your sample and SfPullToRefresh assemblies, an error `Could not load type Xamarin.Forms.ElementTemplate` will occur. Please refer the `ReadMe` to know the software requirements of Syncfusion controls.

N> When there is a mismatch between Syncfusion NuGet packages among your projects, `System.IO.FileLoadException` will occur. To overcome this exception, install the same version of SfPullToRefresh assemblies in all your projects. 


## Launching the SfPullToRefresh on each platform

To use SfPullToRefresh inside an application, each platform application must initialize the SfPullToRefresh renderer. This initialization step varies from platform to platform and is discussed in the following sections.

### Android

The Android launches the SfPullToRefresh without any initialization and is enough to only initialize the Xamarin.Forms Framework to launch the application.

### iOS

To launch the SfPullToRefresh in iOS, you need to call the `SfPullToRefreshRenderer.Init()` in the `FinishedLaunching` overridden method of the AppDelegate class after the Xamarin.Forms Framework initialization and before the LoadApplication is called, as demonstrated in the following code example:

{% highlight c# %}
public override bool FinishedLaunching(UIApplication app, NSDictionary options)
{
    …
    global::Xamarin.Forms.Forms.Init ();
    SfPullToRefreshRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %} 

### Universal Windows Platform (UWP)

To launch the SfPullToRefresh in UWP, you need to call the `SfPullToRefreshRenderer.Init()` in the `MainPage` constructor before the LoadApplication is called, as demonstrated in the following code example:

{% highlight c# %}
public MainPage()
{
    …
    SfPullToRefreshRenderer.Init();
    LoadApplication (new App ());
    …
}
{% endhighlight %}

## Create a sample with SfPullToRefresh 

This section explains how to create a SfPullToRefresh and configure it. 
 
You can download the entire source code of this demo for Xamarin.Forms from [here](http://files2.syncfusion.com/Xamarin.Forms/Samples/DataGrid_GettingStartedForms.zip).

## Creating the project

Create a new BlankApp (Xamarin.Forms.Portable) application in Xamarin Studio or Visual Studio for Xamarin.Forms.

## Adding SfPullToRefresh in Xamarin.Forms 

1. Add the required assembly references to the pcl and renderer projects as discussed in the [Assembly deployment](#assembly-deployment) section.

2. Import SfPullToRefresh control namespace `Syncfusion.SfPullToRefresh.XForms`.

3. Set the any `View` as `PullableContent` of the `SfPullToRefresh`.


{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage x:Class="XamarinForms.SfPullToRefreshPage"
             Title="SfPullToRefreshPage"
             xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:XamarinForms;assembly=XamarinForms"
             xmlns:syncfusion="clr-namespace:Syncfusion.SfPullToRefresh.XForms;assembly=Syncfusion.SfPullToRefresh.XForms">
        <syncfusion:SfPullToRefresh x:Name="pullToRefresh"
                                    PullingThershold="120"
                                    RefreshContentHeight="30"
                                    RefreshContentThreshold="30"
                                    RefreshContentWidth="30">
            <syncfusion:SfPullToRefresh.PullableContent>
                    <Label x:Name="Month" TextColor="White" HorizontalTextAlignment="Center" VerticalTextAlignment="Center" />
            </syncfusion:SfPullToRefresh.PullableContent>
        </syncfusion:SfPullToRefresh>
</ContentPage>

{% endhighlight %}
{% highlight c# %}
using Syncfusion.SfPullToRefresh.XForms;
using Xamarin.Forms;

public partial class SfPullToRefreshPage : ContentPage
{
    Random random = new Random();
    string[] monthsno = new string[] { "1", "2", "3", "4", "5", "6", "7", "8", "9", "10", "11", "12" };
    string[] monthsname = new string[] { "January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December" };
    public SfPullToRefreshPage()
    {
        InitializeComponent();
        Month.Text = monthsno[1]+" month is "+ monthsname[1].ToString();
        pullToRefresh.Pulling += PullToRefresh_Pulling;
        pullToRefresh.Refreshing += PullToRefresh_Refreshing;
    }
    private void PullToRefresh_Refreshing(object sender, EventArgs args)
    {
        pullToRefresh.IsRefreshing = true;
        Device.StartTimer(new TimeSpan(0, 0, 2), () =>
        {
            int number = random.Next(0, 11);
            new MonthData(monthsname[number], monthsname[number]);
            Month.Text = monthsno[number] + " month is " + monthsname[number].ToString();
            pullToRefresh.IsRefreshing = false;
            return false;
        });
    }
    private void PullToRefresh_Pulling(object sender, PullingEventArgs args)
    {
        args.Cancel = false;
        var progress = args.Progress;
    }
}

Model class:

public class MonthData : INotifyPropertyChanged
{
    private string month_SNo;
    private string monthName;
    public MonthData(string month_sno, String month)
    {
        Month_SNo = month_sno;
        MonthName = month;
    }

    public string Month_SNo
    {
        get
        {
            return month_SNo;
        }
        set
        {
            this.month_SNo = value;
            RaisePropertyChanged("Month_SNo");
        }
    }
    public string MonthName
    {
        get
        {
            return monthName;
        }
        set
        {
            this.monthName = value;
            RaisePropertyChanged("MonthName");
        }
    }
    #region INotifyPropertyChanged implementation

    public event PropertyChangedEventHandler PropertyChanged;
    private void RaisePropertyChanged(String Name)
    {
        if (PropertyChanged != null)
            this.PropertyChanged(this, new PropertyChangedEventArgs(Name));
    }

    #endregion
}

{% endhighlight %}
{% endtabs %}

