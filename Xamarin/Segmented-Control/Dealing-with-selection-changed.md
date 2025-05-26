---
layout: post
title: Dealing with selection in Xamarin Segmented Control | Syncfusion<sup>&reg;</sup>
description: Learn how to handle selection change in Syncfusion<sup>&reg;</sup> Xamarin Segmented Control (SfSegmentedControl).
platform: Xamarin
control: SegmentedControl
documentation: ug
---

# Dealing with Selection Changed in Xamarin Segmented Control

The selection changed event is triggered when there's a transition from one segment item to another within the segmented control. It can be managed in two ways.

## User Interface

When users navigate from one item to another, the selection is updated, and the [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_SelectedIndex) value reflects the new item index. The segmented control provides a [`SelectionChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_SelectionChanged) event, which is triggered during selection change with the [`SelectionChangedEventArgs`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SelectionChangedEventArgs.html).

- [`Index`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SelectionChangedEventArgs.html#Syncfusion_XForms_Buttons_SelectionChangedEventArgs_Index): Retrieves the current index of the selected item.

{% tabs %}

{% highlight xaml %}

 <buttons:SfSegmentedControl x:Name = "segmentedControl" SelectionChanged="Handle_SelectionChanged"/>

{% endhighlight %}

{% highlight c# %}

segmentedControl.SelectionChanged += Handle_SelectionChanged;
void Handle_SelectionChanged(object sender, SelectionChangedEventArgs e)
    {
       segmentedControl.BorderColor = UIColor.Red;
    }

{% endhighlight %}

{% endtabs %}

## Programmatically Setting the Selected Index
Users can programmatically set the default selection value. The selection updates based on the provided [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_SelectedIndex) index.

{% tabs %}

{% highlight xaml %}

 <buttons:SfSegmentedControl SelectedIndex="2"/>

{% endhighlight %}

{% highlight c# %}

segmentedControl.SelectedIndex = 2;

{% endhighlight %}

{% endtabs %}

![Selection change illustration](images/Selection-changed/selectionchange.png)

## Event to Command

The SegmentedControl event can be converted into commands using [`Behaviors`](https://learn.microsoft.com/en-us/xamarin/xamarin-forms/app-fundamentals/behaviors/). To achieve this, create a command in the ViewModel class and use [`Behaviors`](https://learn.microsoft.com/en-us/xamarin/xamarin-forms/app-fundamentals/behaviors/) to link it to the SegmentedControl event.

{% tabs %}

{% highlight xaml %}

     <buttons:SfSegmentedControl 
            x:Name="Segment" 
            SelectionTextColor= "White"
            HeightRequest="80"
            VisibleSegmentsCount="5"
            Color="Transparent" 
            BorderColor="#929292"
            SelectedIndex="0" 
            FontColor="#929292"
            BackgroundColor="Transparent"
            ItemsSource="{Binding ItemCollection,Mode=TwoWay}">
    <buttons:SfSegmentedControl.Behaviors>
        <local:EventToCommandBehavior Command="{Binding SelectionChangedCommand}" EventName="SelectionChanged"/>
    </buttons:SfSegmentedControl.Behaviors>
    </buttons:SfSegmentedControl>

{% endhighlight %}

{% highlight c# %}

    public class ViewModel
    {
    public Command SelectionChangedCommand
    {
        get;
        set;
    }
    public ViewModel()
    {
        SelectionChangedCommand = new Command<Syncfusion.XForms.Buttons.SelectionChangedEventArgs>(SelectionChanged);
        ItemCollection = new ObservableCollection<SfSegmentItem>
                    {
                        new SfSegmentItem() {  Text = "Once"},
                        new SfSegmentItem() {  Text = "Daily"},
                        new SfSegmentItem() {  Text = "Weekly"},
                        new SfSegmentItem() {  Text = "Monthly"},
                        new SfSegmentItem() {  Text = "Yearly"},
                    };
    }

    private void SelectionChanged(Syncfusion.XForms.Buttons.SelectionChangedEventArgs obj)
    {
        Application.Current.MainPage.DisplayAlert("Notification", "The Selected Index: " + obj.Index, "Ok");
    }

    private ObservableCollection<SfSegmentItem> itemCollection = new ObservableCollection<SfSegmentItem>();

    public ObservableCollection<SfSegmentItem> ItemCollection
    {
        get { return itemCollection; }
        set { itemCollection = value; }
    }
    }

{% endhighlight %}
{% endtabs %}

Download the complete source code from GitHub [here](https://github.com/SyncfusionExamples/xamarin.forms-segmentedcontrol-with-event-to-command-behavior).

For more information about event-to-command behavior in Xamarin.Forms, refer to [this link](https://learn.microsoft.com/en-us/samples/xamarin/xamarin-forms-samples/behaviors-eventtocommandbehavior/).
