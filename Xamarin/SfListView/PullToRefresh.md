---
layout: post
title: PullToRefresh in SfListView
description: Describes about the pull to refresh integration into SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# PullToRefresh 

SfListView lets you to enable the `PullToRefresh` support by loading it directly into the [PullableContent](https://help.syncfusion.com/cr/cref_files/xamarin/sfpulltorefresh/Syncfusion.SfPullToRefresh.XForms~Syncfusion.SfPullToRefresh.XForms.SfPullToRefresh~PullableContent.html). At runtime, SfListView provides support for refreshing the data in view while performing the `PullToRefresh` action.

N> You need to load the SfListView as first children of `PullableContent` for the `PulltoRefresh`.

{% tabs %}
{% highlight xaml %}
<pulltoRefresh:SfPullToRefresh x:Name="pullToRefresh"
                               ProgressBackgroundColor="#428BCA" RefreshContentHeight="50" 
                               RefreshContentWidth="50" TransitionMode="Push" IsRefreshing="False">
  <pulltoRefresh:SfPullToRefresh.PullableContent>
    <syncfusion:SfListView x:Name="listView" ItemSize="120"
                           SelectionMode="None">
    </syncfusion:SfListView>
  </pulltoRefresh:SfPullToRefresh.PullableContent>
</pulltoRefresh:SfPullToRefresh>
{% endhighlight %}
{% highlight c# %}
public ListViewPullToRefresh()
{
   InitializeComponent();
   //Initializing the PullToRefresh control.
   SfPullToRefresh pulltoRefresh = new SfPullToRefresh();
   pullToRefresh.RefreshContentHeight = 50;
   pullToRefresh.RefreshContentWidth = 50;
   pullToRefresh.TransitionMode = TransitionType.Push;
   pullToRefresh.IsRefreshing = false;
   
   //Initializing the SfListView control.
   var listView = new SfListView();
   listView.ItemSize = 120;
   listView.SelectionMode = SelectionMode.None;
   
   //loading listview into pulltorefresh
   pullToRefresh.PullableContent = listView;
}
{% endhighlight %}
{% endtabs %}

### Load the data into SfListView on pull-to-refresh

SfListView lets you to refresh the data in view at runtime by using [Refreshing](https://help.syncfusion.com/cr/cref_files/xamarin/sfpulltorefresh/Syncfusion.SfPullToRefresh.XForms~Syncfusion.SfPullToRefresh.XForms.SfPullToRefresh~Refreshing_EV.html) event. The `Refreshing` event gets triggered once the progress bar meets 100 %. You can add the data into the underlying collection and the data gets updated in view once the `Refreshing` event gets completed.

{% highlight c# %}

pullToRefresh.Refreshing += PullToRefresh_Refreshing;

private async void PullToRefresh_Refreshing(object sender, EventArgs args)
{
   pullToRefresh.IsRefreshing = true;
   await Task.Delay(2000);
 
   for (int i = 0; i < 3; i++)
   {
      var blogsCount = pulltoRefreshViewModel.BlogsInfo.Count;
      var item = new ListViewBlogsInfo()
      {
         BlogTitle = pulltoRefreshViewModel.BlogsTitle[blogsTitleCount - blogsCount],
         BlogAuthor = pulltoRefreshViewModel.BlogsAuthers[blogsAuthorCount - blogsCount],
         BlogCategory = pulltoRefreshViewModel.BlogsCategory[blogsCategoryCount - blogsCount],
         ReadMoreContent = pulltoRefreshViewModel.BlogsReadMoreInfo[blogsReadMoreCount - blogsCount],
      };
      pulltoRefreshViewModel.BlogsInfo.Insert(0, item);
   }
   pullToRefresh.IsRefreshing = false;
}

{% endhighlight %}

Now run the application to render the following output. You can also download the entire source code of this demo from [here](http://files2.syncfusion.com/Xamarin.Forms/Samples/ListView_PullToRefresh.zip).

![](SfListView_images/SfListView-PullToRefresh.png)

## Limitations

SfListView does not support for `PullToRefresh` when [Orientation](https://help.syncfusion.com/cr/cref_files/xamarin/sflistview/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~Orientation.html) is `Horizontal`.