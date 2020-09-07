---
layout: post
title: PullToRefresh in Xamrin.Forms ListView | Syncfusion
description: Describes about the pull to refresh integration into SfListView.
platform: xamarin
control: SfListView
documentation: ug
---

# PullToRefresh

The [SfPullToRefresh](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPullToRefresh.XForms.SfPullToRefresh.html) refreshing control allows interacting and refreshing the loaded view. When the SfListView is loaded inside the `SfPullToRefresh`, it refreshes the item when performing the pull-to-refresh action.

Refer [control dependencies](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfpulltorefresh) section to get the list of assemblies or NuGet package needs to be added as reference to use the SfPullToRefresh control.

Refer [initializing pull-to-refresh](https://help.syncfusion.com/xamarin/sfpulltorefresh/getting-started#launching-the-sfpulltorefresh-on-each-platform) to launch pull-to-refresh on each platform.

## SfListView inside the SfPullToRefresh 

The SfListView supports refreshing the data in view when performing the pull-to-refresh action at runtime by loading it directly into the [SfPullToRefresh.PullableContent](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPullToRefresh.XForms.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_XForms_SfPullToRefresh_PullableContent) of the [SfPullToRefresh](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPullToRefresh.XForms.SfPullToRefresh.html).

N> You should load the SfListView as first children of `PullableContent` for the `SfPullToRefresh`.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:pulltoRefresh="clr-namespace:Syncfusion.SfPullToRefresh.XForms;assembly=Syncfusion.SfPullToRefresh.XForms"
             xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms" >
 <pullToRefresh:SfPullToRefresh x:Name="pullToRefresh"
                               ProgressBackgroundColor="#428BCA" RefreshContentHeight="50" 
                               RefreshContentWidth="50" TransitionMode="Push" IsRefreshing="False">
  <pullToRefresh:SfPullToRefresh.PullableContent>
    <syncfusion:SfListView x:Name="listView" ItemSize="120"
                           SelectionMode="None">
    </syncfusion:SfListView>
  </pullToRefresh:SfPullToRefresh.PullableContent>
 </pullToRefresh:SfPullToRefresh>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
public ListViewPullToRefresh()
{
   InitializeComponent();
   //Initializing the PullToRefresh control.
   SfPullToRefresh pullToRefresh = new SfPullToRefresh();
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

### Loading data when refreshing

To refresh the data in view at runtime, use the [SfPullToRefresh.Refreshing](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPullToRefresh.XForms.SfPullToRefresh.html) event. The `Refreshing` event gets triggered once the progress bar meets 100 %. The data can be added into the underlying collection, and the data gets updated in view once the `Refreshing` event gets completed.

{% tabs %}
{% highlight c# %}
pullToRefresh.Refreshing += PullToRefresh_Refreshing;

private async void PullToRefresh_Refreshing(object sender, EventArgs args)
{
   pullToRefresh.IsRefreshing = true;
   await Task.Delay(2000);
 
   for (int i = 0; i < 3; i++)
   {
      var blogsCount = pullToRefreshViewModel.BlogsInfo.Count;
      var item = new ListViewBlogsInfo()
      {
         BlogTitle = pullToRefreshViewModel.BlogsTitle[blogsTitleCount - blogsCount],
         BlogAuthor = pullToRefreshViewModel.BlogsAuthors[blogsAuthorCount - blogsCount],
         BlogCategory = pullToRefreshViewModel.BlogsCategory[blogsCategoryCount - blogsCount],
         ReadMoreContent = pullToRefreshViewModel.BlogsReadMoreInfo[blogsReadMoreCount - blogsCount],
      };
      pullToRefreshViewModel.BlogsInfo.Insert(0, item);
   }
   pullToRefresh.IsRefreshing = false;
}
{% endhighlight %}
{% endtabs %}

Run the application to render the following output. 
Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/Load-xamarin.forms-listview-inside-pulltorefresh).

![Pull to refresh data in listview](SfListView_images/SfListView-PullToRefresh.png)

## SfListView inside the SfPullToRefresh with ScrollView 

The SfListView allows loading as a [SfPullToRefresh.PullableContent](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPullToRefresh.XForms.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_XForms_SfPullToRefresh_PullableContent) of the [SfPullToRefresh](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPullToRefresh.XForms.SfPullToRefresh.html) with ScrollView and refresh the data in view at runtime.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:pulltoRefresh="clr-namespace:Syncfusion.SfPullToRefresh.XForms;assembly=Syncfusion.SfPullToRefresh.XForms"
             xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms" >
 <ScrollView>
   <pulltoRefresh:SfPullToRefresh x:Name="pullToRefresh" 
                               ProgressBackgroundColor="#428BCA" 
                               TransitionMode="SlideOnTop" 
                               IsRefreshing="False">
     <pulltoRefresh:SfPullToRefresh.PullableContent>
            <syncfusion:SfListView x:Name="listView" 
                                   ItemSize="120" 
                                   AutoFitMode="Height" 
                                   SelectionMode="None">
            </syncfusion:SfListView>
    </pulltoRefresh:SfPullToRefresh.PullableContent>
  </pulltoRefresh:SfPullToRefresh>
 </ScrollView>
</ContentPage>
{% endhighlight %}
{% highlight c# %}

public ListViewPullToRefresh()
{
  InitializeComponent();
  //Initializing the PullToRefresh control.
  SfPullToRefresh pullToRefresh = new SfPullToRefresh();
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
		
public App()
{
  InitializeComponent();
  SfPullToRefresh pullToRefresh = new SfPullToRefresh();
  MainPage = new ContentPage { Content = new ScrollView { Content = pullToRefresh.PullableContent } };
}
		
{% endhighlight %}
{% endtabs %}

## Limitation

The horizontal ListView does not support the [SfPullToRefresh](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPullToRefresh.XForms.SfPullToRefresh.html).

## How To

### Pull-to-refresh with SearchBar at Top

When the SearchBar or any view placed above the [SfPullToRefresh](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPullToRefresh.XForms.SfPullToRefresh.html) control, pulling action does not work on the SfListView because touches directly passed to the SfListView instead of SfPullToRefresh control. You can overcome this problem by placing the SfListView inside the Grid and place that Grid as [SfPullToRefresh.PullableContent](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPullToRefresh.XForms.SfPullToRefresh.html#Syncfusion_SfPullToRefresh_XForms_SfPullToRefresh_PullableContent).

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:pulltoRefresh="clr-namespace:Syncfusion.SfPullToRefresh.XForms;assembly=Syncfusion.SfPullToRefresh.XForms"
             xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms" >
  <ContentPage.Content>
        <Grid RowSpacing="0" ColumnSpacing="0" Padding="0" Margin="0">
            <Grid.RowDefinitions>
                <RowDefinition Height="50" />
                <RowDefinition Height="*" />
            </Grid.RowDefinitions>
            <Grid.Behaviors>
                <local:SfListViewPullToRefreshBehavior />
            </Grid.Behaviors>
            <SearchBar x:Name="filterText" Placeholder="Search" FontSize="14" />
  
            <pulltoRefresh:SfPullToRefresh x:Name="pullToRefresh" Grid.Row="1"
                                           ProgressBackgroundColor="#428BCA" RefreshContentHeight="50" 
                                           RefreshContentWidth="50" TransitionMode="Push" IsRefreshing="False">
                <pulltoRefresh:SfPullToRefresh.PullableContent>
                    <Grid>
                        <syncfusion:SfListView x:Name="listView" AllowSwiping="True"
                                   AutoFitMode="Height">
                        </syncfusion:SfListView>
                    </Grid>
                </pulltoRefresh:SfPullToRefresh.PullableContent>
            </pulltoRefresh:SfPullToRefresh>
        </Grid>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
public ListViewPullToRefresh()
{
   InitializeComponent();
   //Initializing the PullToRefresh control.
   SfPullToRefresh pullToRefresh = new SfPullToRefresh();
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

   var grid = new Grid();
   var searchBar = new SearchBar() { Placeholder = "Search here to filter" };

   grid.Children.Add(searchBar);
   grid.Children.Add(pullToRefresh, 0, 1);
}
{% endhighlight %}
{% endtabs %}

Download entire source code from GitHub [here](https://github.com/SyncfusionExamples/Load-pulltorefresh-with-searchbar-at-the-top-in-xamarin.forms-listview-).

### Pull-to-refresh with Grouping

The [SfPullToRefresh](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPullToRefresh.XForms.SfPullToRefresh.html) has its pullable content as SfListView along with [SfListView.GroupHeaderTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_GroupHeaderTemplate). When refreshing the items in the listview, the newly added item loads directly into respective groups.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns:pulltoRefresh="clr-namespace:Syncfusion.SfPullToRefresh.XForms;assembly=Syncfusion.SfPullToRefresh.XForms"
             xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms" >
 <ContentPage.Content>
    <Grid RowSpacing="0" ColumnSpacing="0" Padding="0" Margin="0">
       <Grid.Behaviors>
          <local:SfListViewPullToRefreshBehavior />
       </Grid.Behaviors>
       <Grid.RowDefinitions>
          <RowDefinition Height="60"/>
          <RowDefinition Height="*"/>
       </Grid.RowDefinitions>
       <SearchBar x:Name="filterText" Placeholder="Search" FontSize="14" />
       <pulltoRefresh:SfPullToRefresh x:Name="pullToRefresh"
                                      ProgressBackgroundColor="#0065FF"
                                      RefreshContentHeight="50"
                                      PullingThreshold="150"
                                      RefreshContentWidth="50"
                                      TransitionMode="Push"
                                      IsRefreshing="False"
                                      Grid.Row="1">
           <pulltoRefresh:SfPullToRefresh.PullableContent>
             <syncfusion:SfListView x:Name="listView" ItemSize="120"
                                   AutoFitMode="Height" SelectionMode="None" AllowGroupExpandCollapse="True">
                        <syncfusion:SfListView.GroupHeaderTemplate>
                            <DataTemplate>
                                <ViewCell>
                                    <ViewCell.View>
                                        <Grid HeightRequest="150">
                                        <Label Text="{Binding Key}" TextColor="Red" BackgroundColor="#d3d3d3"/>
                                        </Grid>
                                    </ViewCell.View>
                                </ViewCell>
                            </DataTemplate>
                        </syncfusion:SfListView.GroupHeaderTemplate>
             </syncfusion:SfListView>
           </pulltoRefresh:SfPullToRefresh.PullableContent>
       </pulltoRefresh:SfPullToRefresh>
    </Grid>
  </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
public ListViewPullToRefresh()
{
   InitializeComponent();
   //Initializing the PullToRefresh control.
   SfPullToRefresh pullToRefresh = new SfPullToRefresh();
   pullToRefresh.RefreshContentHeight = 50;
   pullToRefresh.RefreshContentWidth = 50;
   pullToRefresh.TransitionMode = TransitionType.Push;
   pullToRefresh.IsRefreshing = false;

   //Initializing the SfListView control.
   var listView = new SfListView();
   listView.ItemSize = 120;
   listView.SelectionMode = SelectionMode.None;
   listView.GroupHeaderTemplate = new DataTemplate(() => 
   {
      var grid = new Grid();
      grid.HeightRequest = 150;
      var headerLabel = new Label
      {
      TextColor = Color.Red,
      BackgroundColor=Color.White
      };
      headerLabel.SetBinding(Label.TextProperty, new Binding("key"));
      grid.Children.Add(headerLabel);
      return grid;
   });

      //loading listview into pulltorefresh
      pullToRefresh.PullableContent = listView;

      var grid = new Grid();
      var searchBar = new SearchBar() { Placeholder = "Search here to filter" };

      grid.Children.Add(searchBar);
      grid.Children.Add(pullToRefresh, 0, 1);
}
{% endhighlight %}
{% endtabs %}