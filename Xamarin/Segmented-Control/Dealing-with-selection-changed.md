---
layout: post
title: Dealing with selection in Xamarin Segmented Control | Syncfusion
description: Learn here all about Dealing with selection changed support in Syncfusion Xamarin Segmented Control (SfSegmentedControl) and more.
platform: Xamarin
control: SegmentedControl
documentation: ug
---

# Dealing with selection changed in Xamarin Segmented Control

The selection changed event occurs when there is a change from one segment item to another in the segmented control. It can be handled by two ways.

## User interface

When users navigate from one item to another, selection is changed, so that the [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_SelectedIndex) value is updated to the new index of the item. The segmented control provides the [`SelectionChanged`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_SelectionChanged) event, which is triggered when the selection is changed with the [`SelectionChangedEventArgs`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SelectionChangedEventArgs.html).

`Index` - Gets the current index value of the selected item.

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

## Selected Index through programmatically.

Users can set the default value programmatically for the selection to be placed. The selection is updated based on the index value given for the [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfSegmentedControl.html#Syncfusion_XForms_Buttons_SfSegmentedControl_SelectedIndex). 

{% tabs %}

{% highlight xaml %}

 <buttons:SfSegmentedControl SelectedIndex="2"/>

{% endhighlight %}

{% highlight c# %}

segmentedControl.SelectedIndex = 2;

{% endhighlight %}

{% endtabs %}


![selectionchange](images/Selection-changed/selectionchange.png)

## Event to command

The SegmentedControl event can be converted into commands using [`Behaviors`](https://developer.xamarin.com/guides/xamarin-forms/behaviors/). To achieve this, create a command in the ViewModel class and use [`Behaviors`](https://developer.xamarin.com/guides/xamarin-forms/behaviors/) to associate it to the SegmentedControl event.

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

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/xamarin.forms-segmentedcontrol-with-event-to-command-behavior).

For more information about the event to command behavior in Xamarin.Forms, please refer to [this](https://developer.xamarin.com/samples/xamarin-forms/Behaviors/EventToCommandBehavior/) link.


