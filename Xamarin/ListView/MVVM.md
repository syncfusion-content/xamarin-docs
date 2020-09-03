---
layout: post
title: Working with Xamarin.Forms ListView in MVVM | Syncfusion
description: This topic describes about how to use Syncfusion xamarin.Forms ListView with commands, prism, event to command behaavior and different cases of MVVM.
platform: xamarin
control: SfListView
documentation: ug
---

# Working with MVVM in Xamarin ListView (SfListView)

## Commands

### Tap command

The [TapCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_TapCommand) will be triggered whenever tapping the item and passing the [ItemTappedEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemTappedEventArgs.html) as parameter.

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
            viewModel.InboxInfo.Remove((obj as Syncfusion.ListView.XForms.ItemTappedEventArgs).ItemData as ListViewInboxInfo)
    }   
}

{% endhighlight %}
{% endtabs %}

### Hold command

The [HoldCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_HoldCommand) will be triggered whenever long pressing the item and passing the [ItemHoldingEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemHoldingEventArgs.html) as parameter.
 
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
            viewModel.InboxInfo.Remove((obj as Syncfusion.ListView.XForms.ItemHoldingEventArgs).ItemData as ListViewInboxInfo);
    }
}

{% endhighlight %}
{% endtabs %}

N> When Command is binded to ItemTemplate, it must also define `Source` property with its root element as reference. Only then it executes the property in the ViewModel of type Command.

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

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/Load-xamarin.forms-listview-with-event-to-command-behavior).

For more information regarding the event to command behavior in Xamarin.Forms, you can refer [this](https://developer.xamarin.com/samples/xamarin-forms/Behaviors/EventToCommandBehavior/) link.

## Binding command of inner ListView to Model Command?

You can bind command of Button inside ItemTemplate to the command in Model by specifying Source property with its root element as reference to execute the binded property of type command.

{% tabs %}
{% highlight xaml %}
<listView:SfListView x:Name="listView" ItemsSource="{Binding ContactInfo}">
     <listView:SfListView.ItemTemplate>
        <DataTemplate>
           <ViewCell>
                <ViewCell.View>
                   <StackLayout>
                        <listView:SfListView x:Name="list1" ItemsSource="{Binding ContactDetails}" TapCommand="{Binding NavigateToSelectModelsCommand}" TapCommandParameter="{Binding}">
                            <listView:SfListView.ItemTemplate>
                                 <DataTemplate>
                                      <ViewCell>
                                          <ViewCell.View>
                                               <StackLayout BackgroundColor="Teal" >
                                                    <Label Text="{Binding ContactName} "/>
                                                    <Label Text="{Binding ContactNumber}"/>
                                                    <StackLayout HeightRequest="1" BackgroundColor="Gray"/>
                                                </StackLayout>
                                           </ViewCell.View>
                                       </ViewCell>
                                 </DataTemplate>
                            </listView:SfListView.ItemTemplate>
                        </listView:SfListView>
                    </StackLayout>
                </ViewCell.View>
            </ViewCell>
        </DataTemplate>
    </listView:SfListView.ItemTemplate>
</listView:SfListView>

{% endhighlight %}
{% highlight c# %}

public class ContactInfo_NestedListView
{
    public Command<Object> NavigateToSelectModelsCommand { get; private set; }

    public ContactInfo_NestedListView()
    {
       NavigateToSelectModelsCommand = new Command<Object>(NavigateToSelectModels, CanNavigate);
    }
    private bool CanNavigate(object argument)
    {
            return true;
    }
    private void NavigateToSelectModels(object model)
    {
       var customer = model as ContactInfo_NestedListView;
            
       App.Current.MainPage.DisplayAlert("Message", "Tapped customer group value :" + customer.location, "OK");
    }
}
{% endhighlight %}
{% endtabs %}

## Binding command of Button inside the ItemTemplate of Xamarin.Forms ListView to ViewModel Command?

You can bind command of Button inside ItemTemplate to the command in ViewModel by specifying Source property with its root element as reference to execute the binded property of type command.

{% tabs %}
{% highlight xaml %}
<Syncfusion:SfListView x:Name="listView" ItemsSource="{Binding contactsinfo}" >
    <Syncfusion:SfListView.ItemTemplate>
        <DataTemplate>
            <ViewCell>
                <Grid >
                    <Button Text="Delete" Command="{Binding Path=BindingContext.DeleteCommand, Source={x:Reference listView}}" CommandParameter="{x:Reference listView}"/>
                </Grid>
            </ViewCell>
        </DataTemplate>
    </Syncfusion:SfListView.ItemTemplate>
</Syncfusion:SfListView>
{% endhighlight %}
{% highlight c# %}
namespace ListViewSample 
{
    public class ContactsViewModel : INotifyPropertyChanged
    {
        public Command<object> DeleteCommand { get; set; }
         
        public ContactsViewModel()
        {
            DeleteCommand = new Command<object>(OnTapped);
        }

        private void OnTapped(object obj)
        {
            var contact = obj as Contacts;
            contactsInfo.Remove(contact);
            App.Current.MainPage.DisplayAlert("Message","Item Deleted :" +contact.ContactName,"Ok");
        }
    }
}        
{% endhighlight %}
{% endtabs %}

You can download the sample from GitHub [here](https://github.com/SyncfusionExamples/How-bind-a-Command-of-Button-inside-the-ItemTemplate-of-Xamarin.Forms-ListView-to-ViewModel-Command).

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
                             ItemsSource="{Binding ContactsInfo}" IsStickyHeader="True" 
                             AllowSwiping="True" IsStickyGroupHeader="True" GroupHeaderSize="50">
        </syncfusion:SfListView>
    </StackLayout>
</ContentPage>    
{% endhighlight %}
{% endtabs %}

For more details, refer to [https://xamgirl.com/prism-in-xamarin-forms-step-by-step-part-1](https://xamgirl.com/prism-in-xamarin-forms-step-by-step-part-1).

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/Using-xamarin.forms-listview-in-prism).

## ListView with MVVMCross

The SfListView allows users work with MVVMCross Framework. Follow the below steps to work withMVVMCross Framework:

1. Inherit App.cs from MvxApplication instead of your application.
{% tabs %}
{% highlight c# %}
public class CoreApp : MvvmCross.Core.ViewModels.MvxApplication
{
    public override void Initialize()
    {

    }
}
{% endhighlight %}
{% endtabs %}

2. Inherit ViewModel from the MvxViewModel.
{% tabs %}
{% highlight c# %}
public class MvxFormsViewModel : MvxViewModel
{
    public MvxFormsViewModel()
    {

    }
}
{% endhighlight %}
{% endtabs %}

3. Connect view and view model instead of binding context by registering them.
{% tabs %}
{% highlight c# %}
public class CoreApp : MvvmCross.Core.ViewModels.MvxApplication
{
    public override void Initialize()
    {
        CreatableTypes()
            .EndingWith("Service")
            .AsInterfaces()
            .RegisterAsLazySingleton();

        RegisterNavigationServiceAppStart<ViewModels.MvxFormsViewModel>();
    }
}
{% endhighlight %}
{% endtabs %}

4. Derive MainActivity and AppDelegate from MvxFormsAppCompatActivity and MvxFormsApplicationDelegate for initializing renderer.
{% tabs %}
{% highlight c# %}
public class MainActivity : MvxFormsAppCompatActivity
{
    protected override void OnCreate(Bundle bundle)
    {
        base.OnCreate(bundle);
        TabLayoutResource = Resource.Layout.Tabbar;
        ToolbarResource = Resource.Layout.Toolbar;
    }
}

public partial class AppDelegate : MvxFormsApplicationDelegate
{
    public override UIWindow Window { get; set; }

    public override bool FinishedLaunching(UIApplication app, NSDictionary options)
    {
        SfListViewRenderer.Init();
    }
}
{% endhighlight %}
{% endtabs %}

For more details, refer to this [documentation](https://www.mvvmcross.com/documentation/getting-started/mvvmcross-overview).

You can download the entire source code of this demo in the following link: [Source code](https://github.com/SyncfusionExamples/listview_MVVMCross).

## Binding properties in MVVM pattern

### Binding ItemsSource

ListView support to bind the [ItemsSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_ItemsSource) property to populate the list view items from view model.

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

ListView support to select the items through binding the [SelectedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_SelectedItem) property from view model by implementing the `INotifyPropertyChanged` interface that gives the call back notification to UI.

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

Download the entire sample from GitHub [here](https://github.com/SyncfusionExamples/xamarin-forms-listview-selected-item-binding).

### Binding SelectedItems

ListView support to select multiple items through binding the [SelectedItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_SelectedItems) property from view model with ObservableCollection<object> type. Set the [SelectionMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_SelectionMode) property as `Multiple`.

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

Download the entire sample from GitHub [here](https://github.com/SyncfusionExamples/xamarin.forms-listview-selecteditems-binding).

### Binding SelectionChanged event

In ListView, the [SelectionChanged](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event is raised once the selection process has been completed. MVVM for the `SelectionChanged` event can be achieved by binding through the event to command converter. 

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

Download the entire sample from GitHub [here](https://github.com/SyncfusionExamples/Xamarin-forms-listview-selected-item-binding-selectionchanged-event-).

### Binding SelectionChanging event

In ListView, the [SelectionChanging](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event will be raised when selecting an item at the execution time. MVVM for the `SelectionChanging` event can be achieved by binding through the event to command converter.

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

Download the entire sample from GitHub [here](https://github.com/SyncfusionExamples/Xamarin-forms-listview-selected-item-binding-selectionchanging-event).

N> Similarly, you can bind the [ItemTapped](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html), [ItemDoubleTapped](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html), and [ItemHolding](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html) event.

### Handling ItemTapped action

ListView supports binding the [TapCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_TapCommand) property with the item taped action from view model, where you can write navigation or any other action code in the execution. When defining the command, [ItemTappedEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemTappedEventArgs.html) will be passed as command parameter which has item information in execution. 

You can define the command parameter for `TapCommand` using [TappedCommandParameter](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_TapCommandParameter), where you can get the element reference passed in view model.

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

Download the entire sample from GitHub [here]https://github.com/SyncfusionExamples/xamarin-forms-listview-itemtapped-mvvm).

### Handling ItemHolding action

ListView supports binding the [HoldCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_HoldCommand) property with the item holding action from view model, where you can write navigation or any other action code in the execution. When defining the command, [ItemHoldingEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ItemHoldingEventArgs.html) will be passed as command parameter which has item information in execution. 

You can define the command parameter for the `HoldCommand` using [HoldCommandParameter](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_HoldCommandParameter), where you can get the element reference passed in view model.

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

Download the entire sample from GitHub [here](https://github.com/SyncfusionExamples/Xamarin-forms-listview-itemholding-).

### Binding button command

The contents loaded in the [ItemTemplate](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_ItemTemplate) can be bound from the view model using their commands or gestures, where you can customize the loaded content or any other action code needed in the call back. You will get the BindingContext of [ListViewItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.ListViewItem.html) as the parameter in execution when defining the command button. 

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

Download the entire sample from GitHub [here](https://github.com/SyncfusionExamples/Xamarin-forms-listview-viewmodel-binding-button-command).

### Processing LoadMore

ListView supports binding the [LoadMoreOption](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LoadMoreOption), [LoadMoreCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_LoadMoreCommand), and [IsBusy](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_IsBusy) properties from view model to load more number of items at runtime. `LoadMoreOption` enables load more manually or automatically the items when loading the items at runtime. `LoadMoreCommand` executes to load the items form view model. The `IsBusy` property notifies that the items are populating from view model to show or hide the load more view. 

The `IsBusy` property in view model shows the busy indicator when populating the [ItemsSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.ListView.XForms.SfListView.html#Syncfusion_ListView_XForms_SfListView_ItemsSource).

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

You can download the entire sample from GitHub [here](https://github.com/SyncfusionExamples/xamarin-listview-loadmore).

## See also

[How to bind command from ViewModel to external ItemTemplate of Xamarin.Forms ListView](https://www.syncfusion.com/kb/11029)                                                                                                                                        
[Working with ListView in Reactive MVVM](https://www.syncfusion.com/kb/9319/)
[Working with SfListView and Prism for Xamarin.Forms](https://www.syncfusion.com/kb/8763/)                                                                                                                                                             
[How to navigate page from ViewModel using button in ListViewItem](https://www.syncfusion.com/kb/7520/)                                                                                                                                                                                                                            
[How to turn Events into Commands with Behaviors in SfListView](https://www.syncfusion.com/kb/7523/)          
[How to handle touch interaction using MR.Gesture in Xamarin.Forms ListView (SfListView)](https://www.syncfusion.com/kb/11351)                                                                                                                                                                                                                                                                                                                                                  
[How to update ListView on property change in Xamarin.Forms (SfListView)](https://www.syncfusion.com/kb/11419)                                                                                                                                                                          
[How to show time in Xamarin.Forms ListView (SfListView)](https://www.syncfusion.com/kb/11438/)                                                                                                                                                                     
[How to filter Xamarin.Forms ListView (SfListView) using MVVM](https://www.syncfusion.com/kb/11478/)                                                                                                                                                                                                                                                        
[How to use ListView events using Prism Framework in Xamarin.Forms (SfListView)](https://www.syncfusion.com/kb/11681/)                                                                                                                                                                                                                                                                                          
[How to work with Prism using the EventToCommandBehavior in Xamarin.Forms ListView (SfListView)](https://www.syncfusion.com/kb/11680/)                                                                                                                                                                                                                                              
[How to make navigation for a corresponding tapped item named page in Xamarin.Forms ListView (SfListView)](https://www.syncfusion.com/kb/11668/)                                                                                                                                                                                                                        