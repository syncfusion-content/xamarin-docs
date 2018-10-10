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

## Event to command

The ListView event can be converted into commands using [Behaviors](https://developer.xamarin.com/guides/xamarin-forms/behaviors/). To achieve this, create a command in the ViewModel class and associate it to the ListView event using `Behaviors`.

{% tabs %}
{% highlight xaml %}
<listView:SfListView x:Name="listView" ItemsSource="{Binding contactsinfo}">
    <listView:SfListView.Behaviors>
        <local:EventToCommandBehavior EventName="SelectionChanged" Command="{Binding SelectionChangedCommand}"/>
    </listView:SfListView.Behaviors>
</listView:SfListView>
{% endhighlight %}
{% highlight c# %}
public class ContactsViewModel
{
    public Command<ItemSelectionChangedEventArgs> selectionChangedCommand;

    public Command<ItemSelectionChangedEventArgs> SelectionChangedCommand
    {
        get { return selectionChangedCommand; }
        set { selectionChangedCommand = value; }
    }

    public ContactsViewModel()
    {
        SelectionChangedCommand = new Command<Syncfusion.ListView.XForms.ItemSelectionChangedEventArgs>(OnSelectionChanged);
    }

    private void OnSelectionChanged(ItemSelectionChangedEventArgs obj)
    {
        App.Current.MainPage.DisplayAlert("Alert", (obj.AddedItems[0] as Contacts).ContactName + " is selected", "OK");
    }
}
{% endhighlight %}
{% endtabs %}

You can download the entire source code of this demo [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/EventToCommand-343190546).

For more information regarding the event to command behavior in Xamarin.Forms, you can refer [this](https://developer.xamarin.com/samples/xamarin-forms/Behaviors/EventToCommandBehavior/) link.

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

You can download the entire source code of this demo [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/ListViewWithprism-154406465).

## Binding properties in MVVM pattern

### Binding ItemsSource

ListView support to bind the [ItemsSource](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemsSource.html) property to populate the list view items from view model.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:MVVM"
             xmlns:syncfusion="clr-namespace:Syncfusion.ListView.XForms;assembly=Syncfusion.SfListView.XForms"
             x:Class="MVVM.MainPage">
    <ContentPage.BindingContext>
        <local:BookInfoRepository/>
    </ContentPage.BindingContext>
</ContentPage>
<syncfusion:SfListView x:Name="listView" ItemsSource="{Binding BookInfoCollection}"/>
{% endhighlight %}
{% highlight c# %}
listView.SetBinding(SfListView.ItemsSourceProperty, new Binding("BookInfoCollection", BindingMode.OneWay));
{% endhighlight %}
{% endtabs %}


{% tabs %}
{% highlight c# %}
//ViewModel.cs
public class BookInfoRepository : INotifyPropertyChanged
{
    private ObservableCollection<BookInfo> bookInfoCollection;
    public event PropertyChangedEventHandler PropertyChanged;

    public ObservableCollection<BookInfo> BookInfoCollection
    {
        get { return bookInfoCollection; }
        set 
             { 
                 this.bookInfoCollection = value;
         this.OnPropertyChanged("BookInfoCollection");
              }
    }

    public void OnPropertyChanged(string name)
    {
        if (this.PropertyChanged != null)
            this.PropertyChanged(this, new PropertyChangedEventArgs(name));
    }

    public BookInfoRepository()
    {
        GenerateNewBookInfo();
    }

    private void GenerateNewBookInfo()
    {
        BookInfoCollection = new ObservableCollection<BookInfo>();
        BookInfoCollection.Add(new BookInfo() { BookName = "Machine Learning Using C#", BookDescription = "You’ll learn several different approaches to applying machine learning"});
        BookInfoCollection.Add(new BookInfo() { BookName = "Object-Oriented Programming in C#", BookDescription = "Object-oriented programming is the de facto programming paradigm"});
        BookInfoCollection.Add(new BookInfo() { BookName = "C# Code Contracts", BookDescription = "Code Contracts provide a way to convey code assumptions"});
    }
}
{% endhighlight %}
{% endtabs %}

### Binding SelectedItem

ListView support to select the items through binding the [SelectedItem](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~SelectedItem.html) property from view model by implementing the `INotifyPropertyChanged` interface that gives the call back notification to UI.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" 
                       SelectedItem="{Binding SelectedItem}"
                       ItemsSource="{Binding BookInfoCollection}"/>
{% endhighlight %}
{% highlight c# %}
listView.SetBinding(SfListView.SelectedItemProperty, new Binding("SelectedItem", BindingMode.TwoWay));
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
//ViewModel.cs
public class BookInfoRepository : INotifyPropertyChanged
{
    private object selectedItem;
    public object SelectedItem
    {
        get { return this.selectedItem; }
        set
        {
            this.selectedItem = value;
            this.OnPropertyChanged("SelectedItem");
        }
    }
    public BookInfoRepository()
    {
        SelectedItem = BookInfoCollection[2];
    }
}
{% endhighlight %}
{% endtabs %}

You can download the entire sample [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/MVVMSelectedItem315636739).

### Binding SelectedItems

ListView support to select multiple items through binding the [SelectedItems](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~SelectedItems.html) property from view model with ObservableCollection<object> type. Set the [SelectionMode](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~SelectionMode.html) property as `Multiple`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView"
                        SelectionMode="Multiple"
                        SelectedItems="{Binding SelectedItems}"
                        ItemsSource="{Binding BookInfoCollection}"/>
{% endhighlight %}
{% highlight c# %}
listView.SelectionMode = SelectionMode.Multiple;
listView.SetBinding(SfListView.SelectedItemsProperty, new Binding("SelectedItems", BindingMode.TwoWay));
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
//ViewModel.cs
public class BookInfoRepository : INotifyPropertyChanged
{
    public event PropertyChangedEventHandler PropertyChanged;
    private ObservableCollection<object> selectedItems;

    public ObservableCollection<object> SelectedItems
    {
        get { return this.selectedItems; }
        set
        {
            this.selectedItems = value;
            this.OnPropertyChanged("SelectedItems");
        }
    }

    public void OnPropertyChanged(string name)
    {
        if (this.PropertyChanged != null)
            this.PropertyChanged(this, new PropertyChangedEventArgs(name));
    }

    public BookInfoRepository()
    {
        SelectedItems = new ObservableCollection<object>();
        SelectedItems.Add(BookInfoCollection[1]);
        SelectedItems.Add(BookInfoCollection[2]);
    }
}
{% endhighlight %}
{% endtabs %}

You can download the entire sample [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/MVVMSelectedItems739377311).

### Binding SelectionChanged event

In ListView, the [SelectionChanged](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~SelectionChanged_EV.html) event is raised once the selection process has been completed. MVVM for the `SelectionChanged` event can be achieved by binding through the event to command converter. 

Refer [event to command](https://www.syncfusion.com/kb/7523/how-to-turn-events-into-commands-with-behaviors-in-sflistview) knowledge base to create the command for event using behavior.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" 
                       ItemsSource="{Binding BookInfoCollection}">
    <syncfusion:SfListView.Behaviors>
        <local:EventToCommandBehavior EventName="SelectionChanged" Command="{Binding SelectedItem}" 
                                          Converter="{StaticResource EventArgs}"/>
    </syncfusion:SfListView.Behaviors>
</syncfusion:SfListView>
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
//ViewModel.cs
public class BookInfoRepository : INotifyPropertyChanged
{
    private Command<ItemSelectionChangedEventArgs> selectedItem

    public Command<ItemSelectionChangedEventArgs> SelectedItem
    {
        get { return this.selectedItem; }
        set
        {
            this.selectedItem = value;
            this.OnPropertyChanged("SelectedItem");
        }
    }

    public BookInfoRepository()
    {
        selectedItem = new Command<ItemSelectionChangedEventArgs>(OnSelectionChanged);
    }

    ///<summary>
    ///Remove the selected item
    ///</summary>
    public void OnSelectionChanged(ItemSelectionChangedEventArgs obj)
    {
        var eventArgs = obj as ItemSelectionChangedEventArgs;
        var item= eventArgs.AddedItems[0];
        this.bookInfoCollection.Remove(this.BookInfoCollection.FirstOrDefault(x => x == item));
    }
}
{% endhighlight %}
{% endtabs %}

You can download the entire sample [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/MVVMSelectionChanged598843483).

### Binding SelectionChanging event

In ListView, the [SelectionChanging](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~SelectionChanging_EV.html) event will be raised when selecting an item at the execution time. MVVM for the `SelectionChanging` event can be achieved by binding through the event to command converter.

Refer [event to command](https://www.syncfusion.com/kb/7523/how-to-turn-events-into-commands-with-behaviors-in-sflistview) knowledge base to create the command for event using behavior.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" 
                       ItemsSource="{Binding BookInfoCollection}">
    <syncfusion:SfListView.Behaviors>
        <local:EventToCommandBehavior EventName="SelectionChanging" Command="{Binding SelectedItem}" 
                                          Converter="{StaticResource EventArgs}"/>
    </syncfusion:SfListView.Behaviors>
</syncfusion:SfListView>
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
//ViewModel.cs
public class BookInfoRepository : INotifyPropertyChanged
{
    private Command<ItemSelectionChangingEventArgs> selectedItem

    public Command<ItemSelectionChangingEventArgs> SelectedItem
    {
        get { return this.selectedItem; }
        set
        {
            this.selectedItem = value;
            this.OnPropertyChanged("SelectedItem");
        }
    }

    public BookInfoRepository()
    {
        selectedItem = new Command<ItemSelectionChangingEventArgs>(OnSelectionChanging);
    }

    ///<summary>
    ///To disable the selection for particular item
    ///</summary>
    public void OnSelectionChanging(ItemSelectionChangingEventArgs obj)
    {
        var eventArgs = obj as ItemSelectionChangingEventArgs;
        if (eventArgs.AddedItems.Count > 0 && eventArgs.AddedItems[0] == this.BookInfoCollection[0])
            eventArgs.Cancel = true;
    }
}
{% endhighlight %}
{% endtabs %}

You can download the entire sample [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/MVVMSelectionChanging964295010).

N> Similarly, you can bind the [ItemTapped](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTapped_EV.html), [ItemDoubleTapped](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemDoubleTapped_EV.html), and [ItemHolding](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemHolding_EV.html) event.

### Handling ItemTapped action

ListView supports binding the [TapCommand](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~TapCommand.html) property with the item taped action from view model, where you can write navigation or any other action code in the execution. When defining the command, [ItemTappedEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemTappedEventArgs.html) will be passed as command parameter which has item information in execution. 

You can define the command parameter for `TapCommand` using [TappedCommandParameter](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~TapCommandParameter.html), where you can get the element reference passed in view model.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" 
                    TapCommand="{Binding TapCommand}"
                    ItemsSource="{Binding BookInfoCollection}"/>
{% endhighlight %}
{% highlight c# %}
listView.SetBinding(SfListView.TapCommandProperty, new Binding("TapCommand", BindingMode.OneWay));
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
//ViewModel.cs
public class BookInfoRepository : INotifyPropertyChanged
{
    private Command tapCommand;

    public Command TapCommand
    {
        get { return tapCommand; }
        protected set { tapCommand = value; }
    }

    public BookInfoRepository()
    {
        tapCommand = new Command(OnItemTapped);
    }

    ///<summary>
    ///To display tapped item content
    ///</summary>
    public void OnItemTapped(object obj)
    {
        var eventArgs = obj as Syncfusion.ListView.XForms.ItemTappedEventArgs;
        var bookName = (eventArgs.ItemData as BookInfo).BookName;
        var bookDescription = (eventArgs.ItemData as BookInfo).BookDescription;
        var display = Application.Current.MainPage.DisplayAlert(bookName, "Description:" + bookDescription, "Ok");
    }
}
{% endhighlight %}
{% endtabs %}

You can download the entire sample [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/MVVMTapCommand1058162896).

### Handling ItemHolding action

ListView supports binding the [HoldCommand](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~HoldCommand.html) property with the item holding action from view model, where you can write navigation or any other action code in the execution. When defining the command, [ItemHoldingEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ItemHoldingEventArgs.html) will be passed as command parameter which has item information in execution. 

You can define the command parameter for the `HoldCommand` using [HoldCommandParameter](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~HoldCommandParameter.html), where you can get the element reference passed in view model.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView"                     
                       HoldCommand="{Binding HoldCommand}"
                       ItemsSource="{Binding BookInfoCollection}"/>
{% endhighlight %}
{% highlight c# %}
listView.SetBinding(SfListView.HoldCommandProperty, new Binding("HoldCommand", BindingMode.OneWay));
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
//ViewModel.cs
public class BookInfoRepository : INotifyPropertyChanged
{
    private Command holdCommand;

    public Command HoldCommand
    {
        get { return holdCommand; }
        protected set { holdCommand = value; }
    }

    public BookInfoRepository()
    {
        holdCommand = new Command(OnHold);
    }

    ///<summary>
    /// Displays the item holding content
    ///</summary>
    public void OnHold(object obj)
    {
        var eventArgs = obj as Syncfusion.ListView.XForms.ItemHoldingEventArgs;           
        Application.Current.MainPage.DisplayAlert("Type Of Item :" + eventArgs.ItemType, "Item Tapped Position : + " +eventArgs.Position , "Ok");
    }
}
{% endhighlight %}
{% endtabs %}

You can download the entire sample [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/MVVMHoldCommand57192241).

### Binding button command

The contents loaded in the [ItemTemplate](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemTemplate.html) can be bound from the view model using their commands or gestures, where you can customize the loaded content or any other action code needed in the call back. You will get the BindingContext of [ListViewItem](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.ListViewItem.html) as the parameter in execution when defining the command button. 

You can also get the reference of element bound as parameter by using command parameter of loaded elements.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView" AutoFitMode="Height"
                SelectedItem="{Binding SelectedItem}"                      
                ItemsSource="{Binding BookInfoCollection}">
    <syncfusion:SfListView.ItemTemplate>
        <DataTemplate>
            <Frame HasShadow="True" Margin="5,5,5,5" >
                <Grid Padding="5">
                    <Grid.RowDefinitions>
                        <RowDefinition Height="*" />
                        <RowDefinition Height="2*" />
                    </Grid.RowDefinitions>
                    <Button x:Name="bookName" Text="{Binding BookName}" Command="{Binding Path=BindingContext.BackgroundColorCommand, Source={x:Reference listView}}" CommandParameter="{x:Reference bookName}}" BackgroundColor="Transparent" FontAttributes="Bold" FontSize="19"/>
                    <Label Grid.Row="1" Text="{Binding BookDescription}" FontSize="15" />
                </Grid>
            </Frame>
        </DataTemplate>
    </syncfusion:SfListView.ItemTemplate>
</syncfusion:SfListView>
{% endhighlight %}
{% highlight c# %}
 listView.ItemTemplate = new DataTemplate(() =>
 {
    var frame = new Frame();
    frame.HasShadow = true;
    frame.Margin = 5;
    var grid = new Grid();
    grid.Padding = 5;
    var button = new Button();
    Binding binding = new Binding();
    binding.Path = "BookName";
    button.SetBinding(Button.TextProperty, binding);
    button.Command = this.viewModel.BackgroundColorCommand;
    button.BackgroundColor = Color.Transparent;
    button.FontAttributes = FontAttributes.Bold;
    button.FontSize = 19;
    var label = new Label();
    Binding bind = new Binding();
    bind.Path = "BookDescription";
    label.SetBinding(Label.TextProperty, bind);
    label.FontSize = 15;
    grid.Children.Add(button);
    grid.Children.Add(label, 0, 1);
    frame.Content = grid;
    return frame;
 });
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
public class BookInfoRepository : INotifyPropertyChanged
{
    private Command backgroundColorCommand;

    public Command BackgroundColorCommand
    {
        get { return backgroundColorCommand; }
        protected set { backgroundColorCommand = value; }
    }

    public BookInfoRepository()
    {
        backgroundColorCommand = new Command(OnButtonTapped);
    }

    ///<summary>
    ///To display tapped item content
    ///</summary>
    public void OnButtonTapped(object obj)
    {
        var firstButton = obj as Button;
        firstButton.BackgroundColor = Color.AliceBlue;            
    }
}
{% endhighlight %}
{% endtabs %}

You can download the entire sample [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/MVVMButtonCommand201962307).

### Processing LoadMore

ListView supports binding the [LoadMoreOption](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreOption.html), [LoadMoreCommand](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~LoadMoreCommand.html), and [IsBusy](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~IsBusy.html) properties from view model to load more number of items at runtime. `LoadMoreOption` enables load more manually or automatically the items when loading the items at runtime. `LoadMoreCommand` executes to load the items form view model. The `IsBusy` property notifies that the items are populating from view model to show or hide the load more view. 

The `IsBusy` property in view model shows the busy indicator when populating the [ItemsSource](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfListView.XForms~Syncfusion.ListView.XForms.SfListView~ItemsSource.html).

{% tabs %}
{% highlight xaml %}
<syncfusion:SfListView x:Name="listView"                            
                        LoadMoreOption="Auto"
                        LoadMoreCommand="{Binding LoadMoreItemsCommand}"
                        LoadMoreCommandParameter="{Binding Source={x:Reference Name=listView}}"
                        IsBusy="{Binding IsBusy}"
                        ItemsSource="{Binding BookInfoCollection}">
{% endhighlight %}
{% highlight c# %}
listView.LoadMoreOption = LoadMoreOption.Auto;
listView.SetBinding(SfListView.LoadMoreCommandProperty, new Binding("LoadMoreItemsCommand", BindingMode.OneWay));
listView.LoadMoreCommandParameter = listView;
listView.SetBinding(SfListView.IsBusyProperty, new Binding("IsBusy", BindingMode.OneWay));
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
public class ViewModel:INotifyPropertyChanged
{
    private bool isBusy;
    public bool IsBusy
    {
        get { return isBusy; }
        set
        {
            this.isBusy = value;
            RaisePropertyChanged("IsBusy");
        }
    }
    private int totalItems = 22;
    public Command<object> LoadMoreItemsCommand { get; set; }

    public ViewModel()
    {
        BookInfoCollection = new ObservableCollection<BookInfo>();
        AddBookInfos(0, 3);
        LoadMoreItemsCommand = new Command<object>(LoadMoreItems);
    }

    private bool CanLoadMoreItems(object obj)
    {
        if (BookInfoCollection.Count >= totalItems)
            return false;
        return true;
    }

    private async void LoadMoreItems(object obj)
    {
        var listview = obj as Syncfusion.ListView.XForms.SfListView;
        try
        {
            IsBusy = true;

            await Task.Delay(1000);

            var index = BookInfoCollection.Count;
            var count = index + 3 >= totalItems ? totalItems - index : 3;
            AddBookInfos(index, 3);

        }
        catch
        {

        }
        finally
        {
            IsBusy = false;
        }
    }

    private void AddBookInfos(int index, int count)
    {
        int bookNameCount = 0;
        int bookDescriptionCount = 0;
        for (int i = index; i < index + count; i++)
        {
            if (bookNameCount == 11)
                bookNameCount = 0;
            if (bookDescriptionCount == 11)
                bookDescriptionCount = 0;
            BookInfoCollection.Add(new BookInfo() { BookName = bookNames[bookNameCount] , BookDescription =  bookDescription[bookDescriptionCount] });
            bookNameCount++;
            bookDescriptionCount++;
        }
    }
}
{% endhighlight %}
{% endtabs %}

You can download the entire sample [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/MVVMButtonCommand201962307).