---
layout: post
title: Retrieving selected value in Syncfusion SfAutoComplete control.
description: Learn how to retrieve selected value from SfAutoComplete control
platform: xamarin
control: SfAutoComplete
documentation: ug
---

# Handling Selected Items

SfAutoComplete provides a way to handle the selected item using the following properties:

* SelectedIndex

* SelectedIndices 

* SelectedItem

## SelectedIndex

You can get or set the index of the selected item using the [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms~Syncfusion.SfAutoComplete.XForms.SfAutoComplete~SelectedIndexProperty.html) property. It can be applicable only when [`MultiSelectMode`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfAutoComplete.XForms~Syncfusion.SfAutoComplete.XForms.SfAutoComplete~MultiSelectModeProperty.html) is None.

### How to set the index of item to be selected

The [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms~Syncfusion.SfAutoComplete.XForms.SfAutoComplete~SelectedIndexProperty.html) property holds the index of selected item in suggestion list. 

{% tabs %}

{% highlight xaml %}

	<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <autocomplete:SfAutoComplete
	           x:Name="autoComplete"
	           HeightRequest="40" 
			   MultiSelectMode="None"
	           SelectedIndex="1">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Antigua and Barbuda</x:String>
                    <x:String>American Samoa</x:String>
                    <x:String>Afghanistan</x:String>
                    <x:String>Antarctica</x:String>
                    <x:String>Argentina</x:String>
                    <x:String>Anguilla</x:String>
                    <x:String>Albania</x:String>
                    <x:String>Algeria</x:String>
                    <x:String>Andorra</x:String>
                    <x:String>Angola</x:String>
                </ListCollection:List>
            </autocomplete:SfAutoComplete.AutoCompleteSource>
        </autocomplete:SfAutoComplete>
    </StackLayout>

{% endhighlight %}

{% highlight c# %}

    StackLayout stackLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = 30
            };    
            SfAutoComplete autoComplete = new    SfAutoComplete()
            {
                HeightRequest = 40,
                SelectedIndex = 1,
				MultiSelectMode=MultiSelectMode.None,
                DataSource = new List<string>()
                {
                    "Antigua and Barbuda",
                    "American Samoa",
                    "Afghanistan",
                    "Antarctica",
                    "Argentina",
                    "Anguilla",
                    "Albania",
                    "Algeria",
                    "Andorra",
                    "Angola"
                }
            };

    		stackLayout.Children.Add(autoComplete);
    		this.Content = stackLayout;

{% endhighlight %}

{% endtabs %}

### Retrieving the index of selected item

When an item is selected from suggestion list, its index can be retrieved using the [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms~Syncfusion.SfAutoComplete.XForms.SfAutoComplete~SelectedIndexProperty.html) property. 

The following code snippet demonstrates the way to retrieve [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms~Syncfusion.SfAutoComplete.XForms.SfAutoComplete~SelectedIndexProperty.html) and display it in an alert.

{% tabs %}

{% highlight xaml %}

    <StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <autocomplete:SfAutoComplete
	           x:Name="autoComplete"
	           HeightRequest="40" 
			   MultiSelectMode="None"
               SelectionChanged="autoComplete_SelectionChanged">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Antigua and Barbuda</x:String>
                    <x:String>American Samoa</x:String>
                    <x:String>Afghanistan</x:String>
                    <x:String>Antarctica</x:String>
                    <x:String>Argentina</x:String>
                    <x:String>Anguilla</x:String>
                    <x:String>Albania</x:String>
                    <x:String>Algeria</x:String>
                    <x:String>Andorra</x:String>
                    <x:String>Angola</x:String>
                </ListCollection:List>
            </autocomplete:SfAutoComplete.AutoCompleteSource>
        </autocomplete:SfAutoComplete>
    </StackLayout> 

{% endhighlight %}

{% highlight c# %}

        SfAutoComplete autoComplete;
        public MainPage()
		{
            InitializeComponent();
            StackLayout stackLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = 30
            };

            autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40,
				MultiSelectMode=MultiSelectMode.None,
                DataSource = new List<string>()
                {
                    "Antigua and Barbuda",
                    "American Samoa",
                    "Afghanistan",
                    "Antarctica",
                    "Argentina",
                    "Anguilla",
                    "Albania",
                    "Algeria",
                    "Andorra",
                    "Angola"
                }
            };

            autoComplete.SelectionChanged += autoComplete_SelectionChanged;
            stackLayout.Children.Add(autoComplete);
            this.Content = stackLayout;
        }

        private void autoComplete_SelectionChanged(object sender, Syncfusion.SfAutoComplete.XForms.SelectionChangedEventArgs e)
        {
            DisplayAlert("Selection Changed", "SelectedIndex: " + autoComplete.SelectedIndex, "OK");
        }

{% endhighlight %}

{% endtabs %}

## SelectedIndices

You can get or set the indices of the selected items using the [`SelectedIndices`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfAutoComplete.XForms~Syncfusion.SfAutoComplete.XForms.SfAutoComplete~SelectedIndicesProperty.html) property. It can be applicable when [`MultiSelectMode`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfAutoComplete.XForms~Syncfusion.SfAutoComplete.XForms.SfAutoComplete~MultiSelectModeProperty.html) is in either Token or Delimiter.

### How to set the indices of items 

[`SelectedIndices`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfAutoComplete.XForms~Syncfusion.SfAutoComplete.XForms.SfAutoComplete~SelectedIndicesProperty.html) property holds the Indices of selected items in suggestion list.

{% tabs %}

{% highlight xaml %}

	<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <autocomplete:SfAutoComplete
	           x:Name="autoComplete"
	           HeightRequest="40" 
               MultiSelectMode="Token"
               SelectedIndices="{Binding SelectedIndices}">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Antigua and Barbuda</x:String>
                    <x:String>American Samoa</x:String>
                    <x:String>Afghanistan</x:String>
                    <x:String>Antarctica</x:String>
                    <x:String>Argentina</x:String>
                    <x:String>Anguilla</x:String>
                    <x:String>Albania</x:String>
                    <x:String>Algeria</x:String>
                    <x:String>Andorra</x:String>
                    <x:String>Angola</x:String>
                </ListCollection:List>
            </autocomplete:SfAutoComplete.AutoCompleteSource>
        </autocomplete:SfAutoComplete>
    </StackLayout>

{% endhighlight %}

{% highlight c# %}

    public partial class MainPage : ContentPage
    {
        private object selectedIndices;
        public object SelectedIndices
        {
            get { return selectedIndices; }
            set { selectedIndices = value; }
        }

        public MainPage()
        {
            InitializeComponent();
            SelectedIndices = new List<int>() { 2, 4, 7 };
            this.BindingContext = this;
        }
    }

{% endhighlight %}

{% endtabs %}

### Retrieving the indices of selected item

When an item is selected from suggestion list, its index can be retrieved using the [`SelectedIndices`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfAutoComplete.XForms~Syncfusion.SfAutoComplete.XForms.SfAutoComplete~SelectedIndicesProperty.html) property. 

The following code snippet demonstrates the way to retrieve [`SelectedIndices`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfAutoComplete.XForms~Syncfusion.SfAutoComplete.XForms.SfAutoComplete~SelectedIndicesProperty.html) and display in the ListView.

{% tabs %}

{% highlight xaml %}

    <StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <autocomplete:SfAutoComplete
	           x:Name="autoComplete"
	           HeightRequest="40" 
               MultiSelectMode="Token">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Antigua and Barbuda</x:String>
                    <x:String>American Samoa</x:String>
                    <x:String>Afghanistan</x:String>
                    <x:String>Antarctica</x:String>
                    <x:String>Argentina</x:String>
                    <x:String>Anguilla</x:String>
                    <x:String>Albania</x:String>
                    <x:String>Algeria</x:String>
                    <x:String>Andorra</x:String>
                    <x:String>Angola</x:String>
                </ListCollection:List>
            </autocomplete:SfAutoComplete.AutoCompleteSource>
        </autocomplete:SfAutoComplete>
        <ListView 
            x:Name="MainListView"  
            RowHeight="30" 
            ItemsSource="{Binding Source={x:Reference autoComplete},Path=SelectedIndices}">
            <ListView.ItemTemplate>
                <DataTemplate>
                    <ViewCell>
                        <StackLayout Orientation="Horizontal">
                            <Label Text="SelectedIndex:"/>
                            <Label Text="{Binding}" />
                        </StackLayout>
                    </ViewCell>
                </DataTemplate>
            </ListView.ItemTemplate>
        </ListView>
    </StackLayout> 

{% endhighlight %}

{% highlight c# %}

    public partial class MainPage : ContentPage, INotifyPropertyChanged
    {
        public event PropertyChangedEventHandler PropertyChanged;

        protected virtual void NotifyPropertyChanged([CallerMemberName] string propertyName = "")
        {
            PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
        }  
   
    
        private object selectedIndices;
        public object SelectedIndices
        {
            get { return selectedIndices; }
            set
            {
                selectedIndices = value;
                NotifyPropertyChanged("SelectedIndices");
                
            }
        }
        public MainPage()
        {
            InitializeComponent();
            this.BindingContext = this;
        }
	}

{% endhighlight %}

{% endtabs %}

## SelectedItem

The `SelectedItem` property is used to select the particular item from the suggestion list. You can either get or set the SelectedItem.

### How to set the SelectedItem

The following code snippet demonstrates the way to set `SelectedItem`.

{% tabs %}

{% highlight xaml %}

	<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <autocomplete:SfAutoComplete
	           x:Name="autoComplete"
	           HeightRequest="40" 
               SelectedItem="Angola">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Antigua and Barbuda</x:String>
                    <x:String>American Samoa</x:String>
                    <x:String>Afghanistan</x:String>
                    <x:String>Antarctica</x:String>
                    <x:String>Argentina</x:String>
                    <x:String>Anguilla</x:String>
                    <x:String>Albania</x:String>
                    <x:String>Algeria</x:String>
                    <x:String>Andorra</x:String>
                    <x:String>Angola</x:String>
                </ListCollection:List>
            </autocomplete:SfAutoComplete.AutoCompleteSource>
        </autocomplete:SfAutoComplete>
    </StackLayout>

{% endhighlight %}

{% highlight c# %}

    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = 30
            };
            SfAutoComplete autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40,
                SelectedItem = "Angola",
                MultiSelectMode = MultiSelectMode.None,
                DataSource = new List<string>()
                {
                    "Antigua and Barbuda",
                    "American Samoa",
                    "Afghanistan",
                    "Antarctica",
                    "Argentina",
                    "Anguilla",
                    "Albania",
                    "Algeria",
                    "Andorra",
                    "Angola"
                }
            };

            stackLayout.Children.Add(autoComplete);
            this.Content = stackLayout;
        }
    }

{% endhighlight %}

{% endtabs %}

### Retrieving the selected item

When an item is selected from suggestion list, it can be retrieved using the [`SelectedItem`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfAutoComplete.XForms~Syncfusion.SfAutoComplete.XForms.SfAutoComplete~SelectedItemProperty.html) property. 

The following code snippet demonstrates the way to retrieve [`SelectedItem`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfAutoComplete.XForms~Syncfusion.SfAutoComplete.XForms.SfAutoComplete~SelectedItemProperty.html) and display it in an alert.

{% tabs %}

{% highlight xaml %}

    <StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <autocomplete:SfAutoComplete
	           x:Name="autoComplete"
	           HeightRequest="40" 
			   MultiSelectMode="None"
               SelectionChanged="autoComplete_SelectionChanged">
            <autocomplete:SfAutoComplete.AutoCompleteSource>
                <ListCollection:List x:TypeArguments="x:String">
                    <x:String>Antigua and Barbuda</x:String>
                    <x:String>American Samoa</x:String>
                    <x:String>Afghanistan</x:String>
                    <x:String>Antarctica</x:String>
                    <x:String>Argentina</x:String>
                    <x:String>Anguilla</x:String>
                    <x:String>Albania</x:String>
                    <x:String>Algeria</x:String>
                    <x:String>Andorra</x:String>
                    <x:String>Angola</x:String>
                </ListCollection:List>
            </autocomplete:SfAutoComplete.AutoCompleteSource>
        </autocomplete:SfAutoComplete>
    </StackLayout> 

{% endhighlight %}

{% highlight c# %}

    public partial class MainPage : ContentPage
     {
        SfAutoComplete autoComplete;
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = 30
            };

            autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40,
                MultiSelectMode = MultiSelectMode.None,
                DataSource = new List<string>()
                {
                    "Antigua and Barbuda",
                    "American Samoa",
                    "Afghanistan",
                    "Antarctica",
                    "Argentina",
                    "Anguilla",
                    "Albania",
                    "Algeria",
                    "Andorra",
                    "Angola"
                }
            };

            autoComplete.SelectionChanged += autoComplete_SelectionChanged;
            stackLayout.Children.Add(autoComplete);
            this.Content = stackLayout;
        }

        private void autoComplete_SelectionChanged(object sender, Syncfusion.SfAutoComplete.XForms.SelectionChangedEventArgs e)
        {
            DisplayAlert("Selection Changed", "SelectedItem: " + autoComplete.SelectedItem, "OK");
        }
	 }

{% endhighlight %}

{% endtabs %}
