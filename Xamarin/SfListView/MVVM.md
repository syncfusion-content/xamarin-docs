---
layout: post
title: Working with ListView in MVVM
description: Describes how to use ListView in different cases of MVVM.
platform: xamarin
control: SfListView
documentation: ug
---

# MVVM

## Commands

### Tap command

The [TapCommand](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~TapCommand.html) will be triggered whenever tapping the item and passing the [ItemTappedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemTappedEventArgs.html) as parameter.

{% tabs %}
{% highlight c# %}

listView.TapCommand = viewModel.TappedCommand;

public class CommandViewModel
{
    private Command<Object> tappedCommand;

    public Command<object> TappedCommand
    {
        get { return tappedCommand; }
        set { tappedCommand = value; }
    }

    public CommandViewModel()
    {            
        TappedCommand = new Command<object>(TappedCommandMethod);
    }

    private void TappedCommandMethod(object obj)
    {
        if ((obj as Syncfusion.ListView.XForms.ItemTappedEventArgs).ItemData == viewModel.InboxInfo[0])
            viewModel.InboxInfo.Remove(e.ItemData as ListViewInboxInfo)
    }   
}

{% endhighlight %}
{% endtabs %}

### Hold command

The [HoldCommand](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~HoldCommand.html) will be triggered whenever long pressing the item and passing the [ItemHoldingEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemHoldingEventArgs.html) as parameter.
 
{% tabs %}
{% highlight c# %}

listView.HoldCommand = viewModel.HoldCommand;

public class CommandViewModel
{
    private Command<Object> holdingCommand;

    public Command<object> HoldingCommand
    {
        get { return holdingCommand; }
        set { holdingCommand = value; }
    }

    public CommandViewModel()
    {
        HoldingCommand = new Command<object>(HoldingCommandMethod);
    }

    private void HoldingCommandMethod(object obj)
    {
        if ((obj as Syncfusion.ListView.XForms.ItemHoldingEventArgs).ItemData == viewModel.InboxInfo[3])
            viewModel.InboxInfo.Remove(e.ItemData as ListViewInboxInfo);
    }
}

{% endhighlight %}
{% endtabs %}

## ListView with Prism Framework

The SfListView allows the user to work with prism for MVVM Framework. Steps to be followed:

1. Replace your application to prism application in App.xaml file.
2. Inherit App.xaml.cs from prism application instead of your application.
3. Create a prism namespace library reference in xaml file of the ContentPage.
4. Connect view and view model instead of binding context by registering them.

{% tabs %}
{% highlight c# %}
public partial class App : PrismApplication
{
    public App(IPlatformInitializer initializer = null) : base(initializer) { }

    protected override void OnInitialized()
    {
        InitializeComponent();

    }

    protected override void RegisterTypes()
    {
        Container.RegisterTypeForNavigation<MainPage, MainPageViewModel>();
    }
}

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<prism:PrismApplication xmlns="http://xamarin.com/schemas/2014/forms"
                        xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
                        xmlns:prism="clr-namespace:Prism.Unity;assembly=Prism.Unity.Forms"
                        x:Class="ListViewPrism.App">
</prism:PrismApplication>

{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:prism="clr-namespace:Prism.Mvvm;assembly=Prism.Forms"
             xmlns:local="clr-namespace:ListViewPrism;assembly=ListViewPrism"
             xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
             x:Class="ListViewPrism.Views.MainPage"
             Title="MainPage">
    <StackLayout HorizontalOptions="FillAndExpand" VerticalOptions="FillAndExpand">
        <syncfusion:SfListView x:Name="listView" ItemSize="70" ItemSpacing="0,0,5,0"
                             AutoFitMode="Height"
                             ItemsSource="{Binding ContactsInfo,}" IsStickyHeader="True" 
                             AllowSwiping="True" IsStickyGroupHeader="True" GroupHeaderSize="50">
        </syncfusion:SfListView>
    </StackLayout>
</ContentPage>    
{% endhighlight %}
{% endtabs %}

For more details, refer to [https://xamgirl.com/prism-in-xamarin-forms-step-by-step-part-1](https://xamgirl.com/prism-in-xamarin-forms-step-by-step-part-1).

You can download the entire source code of this demo [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/ListViewPrism116483729).