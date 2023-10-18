---
layout: post
title: MVVM in Xamarin TreeView control | Syncfusion
description: Learn here all about MVVM support in Syncfusion Xamarin TreeView (SfTreeView) control, its elements and more.
platform: xamarin
control: SfTreeView
documentation: ug
---

# MVVM in Xamarin TreeView (SfTreeView)

This section explains about how to work with MVVM pattern in TreeView.

## Binding properties in MVVM pattern

### Binding SelectedItem

TreeView support to select the items through binding the [SelectedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_SelectedItem) property from view model by implementing the `INotifyPropertyChanged` interface that gives the call back notification to UI.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView x:Name="treeView" 
                       SelectedItem="{Binding SelectedPlace}"
                       ChildPropertyName="States"
                       ItemsSource="{Binding CountriesInfo}"/>
{% endhighlight %}
{% highlight c# %}
treeView.SetBinding(SfTreeView.SelectedItemProperty, new Binding("SelectedPlace", BindingMode.TwoWay));
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}

// CountriesViewModel.cs
public class CountriesViewModel
{
    public CountriesViewModel()
    {
        GenerateCountriesInfo();
    }
    public ObservableCollection<Countries> CountriesInfo { get; set; }

    public object SelectedPlace { get; set; }

    private void GenerateCountriesInfo()
    {
        var australia = new Countries() { Name = "Australia" };
        var _NSW = new Countries() { Name = "New South Wales" };
        var _Sydney = new Countries() { Name = "Sydney" };
        australia.States = new ObservableCollection<Countries>();
        australia.States.Add(_NSW);
        _NSW.States = new ObservableCollection<Countries>();
        _NSW.States.Add(_Sydney);
        var usa = new Countries() { Name = "United States of America" };
        var _California = new Countries() { Name = "California" };
        var _LosAngeles = new Countries() { Name = "Los Angeles" };
        usa.States = new ObservableCollection<Countries>();
        usa.States.Add(_California);
        _California.States = new ObservableCollection<Countries>();
        _California.States.Add(_LosAngeles);
         
        this.CountriesInfo = new ObservableCollection<Countries>();
        CountriesInfo.Add(australia);
        CountriesInfo.Add(usa);

        SelectedPlace=_NSW
    }
}
{% endhighlight %}
{% endtabs %}

![Xamarin Forms TreeView with selection](TreeView_images/TreeView_SelectedItem.png)

### Binding SelectedItems

TreeView support to select multiple items through binding the [SelectedItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_SelectedItems) property from view model with `ObservableCollection<object>` type. 

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView x:Name="treeView"
                       SelectionMode="Multiple"
                       SelectedItems="{Binding SelectedCountries}"
                       ChildPropertyName="States"
                       ItemsSource="{Binding CountriesInfo}"/>
{% endhighlight %}
{% highlight c# %}
treeView.SelectionMode = SelectionMode.Multiple;
treeView.SetBinding(SfTreeView.SelectedItemsProperty, new Binding("SelectedCountries", BindingMode.TwoWay));
{% endhighlight %}
{% endtabs %}

{% tabs %}
{% highlight c# %}
// CountriesViewModel.cs
// CountriesViewModel.cs
public class CountriesViewModel
{
    public CountriesViewModel()
    {
        GenerateCountriesInfo();
    }

    public ObservableCollection<Countries> CountriesInfo { get; set; }

    public ObservableCollection<object> SelectedCountries { get; set; }

    private void GenerateCountriesInfo()
    {
        var australia = new Countries() { Name = "Australia" };
        var _NSW = new Countries() { Name = "New South Wales" };
        var _Sydney = new Countries() { Name = "Sydney" };
        var _Victoria = new Countries() { Name = "Victoria" };
        australia.States = new ObservableCollection<Countries>();
        australia.States.Add(_NSW);
        australia.States.Add(_Victoria);
        _NSW.States = new ObservableCollection<Countries>();
        _NSW.States.Add(_Sydney);
        var usa = new Countries() { Name = "United States of America" };
        var _California = new Countries() { Name = "California" };
        usa.States = new ObservableCollection<Countries>();
        usa.States.Add(_California);
      
        this.CountriesInfo = new ObservableCollection<Countries>();
        CountriesInfo.Add(australia);
        CountriesInfo.Add(usa);

        SelectedCountries = new ObservableCollection<object>();
        SelectedCountries.Add(_NSW);
        SelectedCountries.Add(_Victoria);
    }
}
{% endhighlight %}
{% endtabs %}

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/binding-selected-items-treeview-xamarin).

![Xamarin Forms TreeView with selection](TreeView_images/TreeView_Selection.png)

## Commands

### Tap command

The [TapCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_TapCommand) will be triggered whenever tapping the item and passing the [TreeViewNode](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html) as command parameter.

{% tabs %}
{% highlight c# %}

treeView.TapCommand = viewModel.TappedCommand;

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
        App.Current.MainPage.DisplayAlert("Alert", ((obj as Syncfusion.XForms.TreeView.ItemTappedEventArgs).Node.Content as Countries).Name + " is Tapped", "OK");
    }   
}
{% endhighlight %}
{% endtabs %}

### Hold command

The [HoldCommand](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_HoldCommand) will be triggered whenever an item is long pressed and passing the [TreeViewNode](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html) as command parameter.
 
{% tabs %}
{% highlight c# %}

treeView.HoldCommand = viewModel.HoldingCommand;

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
        App.Current.MainPage.DisplayAlert("Alert", ((obj as Syncfusion.XForms.TreeView.ItemTappedEventArgs).Node.Content as Countries).Name + " is Holding", "OK");
    }   
}
{% endhighlight %}
{% endtabs %}

### Expand command

The `ExpandCommand` will be triggered while expanding the node and passing the [TreeViewNode](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html) as command parameter. TreeView expands the node based on the return value of `CanExecute` method implementation of ExpandCommand. If you return false, then expand action will be canceled. `Execute` method implementation of `ExpandCommand` will get called after expanding of node.

{% tabs %}
{% highlight xaml %}

<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:Selection"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.TreeView;assembly=Syncfusion.SfTreeView.XForms"
             x:Class="Selection.MainPage">
    <ContentPage.BindingContext>
        <local:CountriesViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <syncfusion:SfTreeView x:Name="treeView"
                               ExpandCommand="ExpandingCommand"/> 
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}

/// <summary>
/// CommandViewModel class that implements [Command](https://learn.microsoft.com/en-us/dotnet/api/xamarin.forms.command?view=xamarin-forms). 
/// </summary>
public class CommandViewModel
{
    private Command<Object> expandingCommand;

    public Command<object> ExpandingCommand
    {
        get { return expandingCommand; }
        set { expandingCommand = value; }
    }

    public CommandViewModel()
    {            
        ExpandingCommand = new Command<object>(ExpandCommandAction, CanExecute);
    }

    /// <summary>
    /// CanExecute method is called before expanding of node.
    /// </summary>
    /// <returns>Handle expand action by returning true or false. </returns>
    /// <param name="obj">TreeViewNode is passed as command parameter. </param>
    public bool CanExecute(object obj)
    {
        //You can also return false to cancel the expand action.
        return true;
    }

    /// <summary>
    /// Method gets called after expanding action performed.
    /// </summary>
    /// <param name="obj">TreeViewNode is passed as command parameter. </param>
    private void ExpandCommandAction(object obj)
    {
        App.Current.MainPage.DisplayAlert("Alert", "TreeView node is expanded", "OK");
    }   
}
{% endhighlight %}
{% endtabs %}

### Collapse command

The `CollapseCommand` will be triggered while collapsing the node and passing the [TreeViewNode](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html) as command parameter. TreeView collapses the node based on the return value of `CanExecute` method implementation of CollapseCommand. If you return false, then collapse action will be canceled. `Execute` method implementation of `CollapseCommand` will be called after the node has collapsed.

{% tabs %}
{% highlight xaml %}
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:Selection"
             xmlns:syncfusion="clr-namespace:Syncfusion.XForms.TreeView;assembly=Syncfusion.SfTreeView.XForms"
             x:Class="Selection.MainPage">
    <ContentPage.BindingContext>
        <local:CountriesViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <syncfusion:SfTreeView x:Name="treeView"
                               CollapseCommand="CollapsingCommand"/> 
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight c# %}

/// <summary>
/// CommandViewModel class that implements [Command](https://learn.microsoft.com/en-us/dotnet/api/xamarin.forms.command?view=xamarin-forms). 
/// </summary>
public class CommandViewModel
{
	private Command<object> collapsingCommand;
	
	public Command<object> CollapsingCommand
	{
		get { return collapsingCommand; }
		set { collapsingCommand = value; }
	}
	
	public CommandViewModel()
	{
		CollapsingCommand = new Command<object>(CollapseCommandAction, CanExecute);
	}
    
	/// <summary>
    /// CanExecute method is called before collapsing of node. 
    /// </summary>
    /// <returns>Handle collapse action by returning true or false. </returns>
    /// <param name="obj">TreeViewNode is passed as command parameter. </param>
    public bool CanExecute(object obj)
    {
        //You can also return false to cancel the collapse action.
        return true;
    }

    /// <summary>
    /// Method gets called after collapsing action performed.
    /// </summary>
    /// <param name="obj">TreeViewNode is passed as command parameter. </param>
	private void CollapseCommandAction(object obj)
	{
		App.Current.MainPage.DisplayAlert("Alert", "TreeView node is collapsed", "OK");
	}
}
{% endhighlight %}
{% endtabs %}

## Event to command

The `TreeView` event can be converted into commands using [Behaviors](https://learn.microsoft.com/en-gb/xamarin/xamarin-forms/app-fundamentals/behaviors/). To achieve this, create a command in the ViewModel class and associate it to the TreeView event using `Behaviors`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView x:Name="treeView"
                       SelectionMode="Multiple"
                       SelectedItems="{Binding SelectedCountries}"
                       ChildPropertyName="States"
                       ItemsSource="{Binding CountriesInfo}">
    <syncfusion:SfTreeView.Behaviors>
        <local:EventToCommandBehavior EventName="SelectionChanged" Command="{Binding SelectionChangedCommand}"/>
    </syncfusion:SfTreeView.Behaviors>
</syncfusion:SfTreeView>
{% endhighlight %}
{% highlight c# %}
public class CountriesViewModel : INotifyPropertyChanged
{
    public Command<ItemSelectionChangedEventArgs> selectionChangedCommand;

    public CountriesViewModel()
    {
        SelectionChangedCommand = new Command<Syncfusion.XForms.TreeView.ItemSelectionChangedEventArgs>(OnSelectionChanged);
        GenerateCountriesInfo();
    }

    public ObservableCollection<Countries> CountriesInfo { get; set; }

    public ObservableCollection<object> SelectedCountries { get; set; }

    public Command<ItemSelectionChangedEventArgs> SelectionChangedCommand
    {
        get { return selectionChangedCommand; }
        protected set { selectionChangedCommand = value; }
    }

    private void OnSelectionChanged(ItemSelectionChangedEventArgs obj)
    {
        App.Current.MainPage.DisplayAlert("Alert", (obj.AddedItems[0] as Countries).Name + " is selected", "OK");
    }

    public event PropertyChangedEventHandler PropertyChanged;

    public void OnPropertyChanged(string name)
    {
        if (this.PropertyChanged != null)
            this.PropertyChanged(this, new PropertyChangedEventArgs(name));
    }

    private void GenerateCountriesInfo()
    {
        var australia = new Countries() { Name = "Australia" };
        var _NSW = new Countries() { Name = "New South Wales" };
        var _Victoria = new Countries() { Name = "Victoria" };
        australia.States = new ObservableCollection<Countries>();
        australia.States.Add(_NSW);
        australia.States.Add(_Victoria);
        var usa = new Countries() { Name = "United States of America" };
        var _California = new Countries() { Name = "California" };
        usa.States = new ObservableCollection<Countries>();
        usa.States.Add(_California);
      
        this.CountriesInfo = new ObservableCollection<Countries>();
        CountriesInfo.Add(australia);
        CountriesInfo.Add(usa);
    }
}
{% endhighlight %}
{% endtabs %}

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/event-to-command-treeview-xamarin).

For more information regarding the EventToCommand behavior in Xamarin.Forms, you can refer [this](https://learn.microsoft.com/en-gb/samples/xamarin/xamarin-forms-samples/behaviors-eventtocommandbehavior/) link.

## Checkbox items binding in MVVM

SfTreeView support to check multiple items through binding the [CheckedItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TreeView.SfTreeView.html#Syncfusion_XForms_TreeView_SfTreeView_CheckedItems) property from view model with `ObservableCollection<object>` type.

N> TreeView process and sets [TreeViewNode.IsChecked](https://help.syncfusion.com/cr/xamarin/Syncfusion.TreeView.Engine.TreeViewNode.html#Syncfusion_TreeView_Engine_TreeViewNode_IsChecked) based on `CheckedItems` only when you are binding `ItemsSource`.

{% tabs %}
{% highlight xaml %}
<syncfusion:SfTreeView 
    x:Name="TreeView"  
    CheckBoxMode="Recursive"
    ItemsSource="{Binding Folders}"
    CheckedItems="{Binding CheckedNodeInfo}"
    ItemTemplateContextType="Node">
    <syncfusion:SfTreeView.ItemTemplate>
        <DataTemplate>
            <ViewCell>
                <ViewCell.View>
                        <Grid Padding="5">
                            <SfCheckBox:SfCheckBox
                                x:Name="CheckBox"
                                Text="{Binding Content.FileName}"
                                IsChecked="{Binding IsChecked, Mode=TwoWay}"/>
                        </Grid>
                </ViewCell.View>
            </ViewCell>
        </DataTemplate>
    </syncfusion:SfTreeView.ItemTemplate>
</syncfusion:SfTreeView>
{% endhighlight %}
{% highlight c# %}
public class ViewModel
{
    private ObservableCollection<object> checkedNodeInfo;
    public ObservableCollection<object> CheckedNodeInfo
    {
        get
        {
            return checkedNodeInfo;
        }
        set
        {
            this.checkedNodeInfo = value;
        }
    }

    public ViewModel()
    {
        var doc = new Folder() { FileName = "Documents" };
        checkedNodeInfo = new ObservableCollection<object>();
        checkedNodeInfo.Add(doc);
    }
}
{% endhighlight %}
{% endtabs %}

Download the entire source code from GitHub [here](https://github.com/SyncfusionExamples/xamarin-treeview-checkbox-in-mvvm). 

To know more about usage of checkbox, you can refer the documentation from [here](https://help.syncfusion.com/xamarin/treeview/checkbox).

## See also

[How to bind data using FreshMVVM in Xamarin.Forms TreeView (SfTreeView)](https://support.syncfusion.com/kb/article/9841/how-to-bind-data-using-freshmvvm-in-xamarin-forms-treeview-sftreeview)                                                                                                                                                                                                                                                                  
[How to bind node data as CommandParameter for TreeView ItemTemplate content in Xamarin.Forms (SfTreeView)](https://support.syncfusion.com/kb/article/9999/how-to-bind-node-data-as-commandparameter-for-treeview-itemtemplate-content-in-xamarin)                                                                                                                                                                                                                                                                                                                                                                                
[How to add nodes to bound mode TreeView in Xamarin.Forms (SfTreeView)](https://support.syncfusion.com/kb/article/9910/how-to-add-nodes-to-bound-mode-treeview-in-xamarin-forms-sftreeview)
