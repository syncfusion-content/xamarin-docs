---
layout: post
title: Retrieving selected value in Syncfusion SfAutoComplete control.
description: This section describes how to get the selected value and set the selected value in the SfAutoComplete control.
platform: xamarin
control: SfAutoComplete
documentation: ug
---

# Handling Selected Items

## Retrieving selected  values in Xamarin SfAutoComplete 

SfAutoComplete provides a way to handle the selected item using the following properties:

* SelectedIndex

* SelectedIndices 

* SelectedItem

## SelectedIndex

You can get or set the index of the selected item using the [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_SelectedIndexProperty) property. It can be applicable only when [`MultiSelectMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_MultiSelectModeProperty) is None. SelectedIndex will accept integer values.

### How to set the index of item to be selected

The [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_SelectedIndexProperty) property holds the index of selected item in suggestion list. 

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:local="clr-namespace:AutocompleteSample"
             x:Class="AutocompleteSample.MainPage">
    <StackLayout VerticalOptions="Start" 
                 HorizontalOptions="Start" 
                 Padding="30">
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
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfAutoComplete.XForms;
using System.Collections.Generic;
using Xamarin.Forms;

namespace AutocompleteSample
{
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
                SelectedIndex = 1,
                MultiSelectMode = MultiSelectMode.None,
                AutoCompleteSource = new List<string>()
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
}

{% endhighlight %}

{% endtabs %}

### Retrieving the index of selected item

When an item is selected from suggestion list, its index can be retrieved using the [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_SelectedIndexProperty) property. 

The following code snippet demonstrates the way to retrieve [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_SelectedIndexProperty) and display it in an alert.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:local="clr-namespace:AutocompleteSample"
             x:Class="AutocompleteSample.MainPage">
    <StackLayout VerticalOptions="Start" 
                 HorizontalOptions="Start" 
                 Padding="30">
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
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfAutoComplete.XForms;
using System.Collections.Generic;
using Xamarin.Forms;

namespace AutocompleteSample
{
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
                AutoCompleteSource = new List<string>()
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
    }
}

{% endhighlight %}

{% endtabs %}

The following code snippet will handle the event

{% tabs%}

{% highlight C# %}

        private void autoComplete_SelectionChanged(object sender, Syncfusion.SfAutoComplete.XForms.SelectionChangedEventArgs e)
        {
            DisplayAlert("Selection Changed", "SelectedIndex: " + autoComplete.SelectedIndex, "OK");
        }

{% endhighlight %}

{% endtabs %}

## SelectedIndices

You can get or set the indices of the selected items using the [`SelectedIndices`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_SelectedIndicesProperty) property. It can be applicable when [`MultiSelectMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_MultiSelectModeProperty) is in either Token or Delimiter. SelectedIndices will accept collection of integer.

### How to set the indices of items 

[`SelectedIndices`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_SelectedIndicesProperty) property holds the Indices of selected items in suggestion list.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:local="clr-namespace:AutocompleteSample"
             x:Class="AutocompleteSample.MainPage">
    <StackLayout VerticalOptions="Start" 
                 HorizontalOptions="Start" 
                 Padding="30">
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
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System.Collections.Generic;
using Xamarin.Forms;

namespace AutocompleteSample
{
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
            StackLayout stackLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = new Thickness(30)
            };
            SfAutoComplete autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40,
                MultiSelectMode = MultiSelectMode.Token,
                SelectedIndices = this.SelectedIndices,
                AutoCompleteSource = new List<string>()
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
}

{% endhighlight %}

{% endtabs %}

### Retrieving the indices of selected item

When an item is selected from suggestion list, its index can be retrieved using the [`SelectedIndices`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_SelectedIndicesProperty) property. 

The following code snippet demonstrates the way to retrieve [`SelectedIndices`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_SelectedIndicesProperty) and display in the ListView.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:local="clr-namespace:AutocompleteSample"
             x:Class="AutocompleteSample.MainPage">
    <StackLayout VerticalOptions="Start" 
                 HorizontalOptions="Start" 
                 Padding="30">
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
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System.ComponentModel;
using System.Runtime.CompilerServices;
using Xamarin.Forms;

namespace AutocompleteSample
{
 public partial class MainPage : ContentPage,INotifyPropertyChanged
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
            StackLayout stackLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = new Thickness(30)
            };
            SfAutoComplete autoComplete = new SfAutoComplete()
            {
                HeightRequest = 40,
                MultiSelectMode = MultiSelectMode.Token,
                AutoCompleteSource = new List<string>()
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

            ListView mainListView = new ListView()
            {
                RowHeight = 30,
            };

            Binding itemSource_Binding = new Binding();
            itemSource_Binding.Source = autoComplete;
            itemSource_Binding.Path = "SelectedIndices";
            mainListView.SetBinding(ListView.ItemsSourceProperty, itemSource_Binding);

           
            DataTemplate itemTemplate = new DataTemplate(() =>
            {
                StackLayout layout = new StackLayout()
                {
                    Orientation = StackOrientation.Horizontal
                };

                Label nameLabel = new Label();
                nameLabel.Text = "SelectedIndex : ";
                layout.Children.Add(nameLabel);
                Label selectedindexLabel = new Label();
                selectedindexLabel.SetBinding(Label.TextProperty,".");
                layout.Children.Add(selectedindexLabel);
                return new ViewCell { View = layout };
            });
            mainListView.ItemTemplate = itemTemplate;
            stackLayout.Children.Add(mainListView);
            this.BindingContext = this;
            this.Content = stackLayout;
        }
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

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:local="clr-namespace:AutocompleteSample"
             x:Class="AutocompleteSample.MainPage">
    <StackLayout VerticalOptions="Start" 
                 HorizontalOptions="Start" 
                 Padding="30">
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
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfAutoComplete.XForms;
using System.Collections.Generic;
using Xamarin.Forms;

namespace AutocompleteSample
{
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
                AutoCompleteSource = new List<string>()
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
}

{% endhighlight %}

{% endtabs %}

### Retrieving the selected item

When an item is selected from suggestion list, it can be retrieved using the [`SelectedItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_SelectedItemProperty) property. 

The following code snippet demonstrates the way to retrieve [`SelectedItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfAutoComplete.XForms.SfAutoComplete.html#Syncfusion_SfAutoComplete_XForms_SfAutoComplete_SelectedItemProperty) and display it in an alert.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:local="clr-namespace:AutocompleteSample"
             x:Class="AutocompleteSample.MainPage">
    <StackLayout VerticalOptions="Start" 
                 HorizontalOptions="Start" 
                 Padding="30">
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
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.SfAutoComplete.XForms;
using System.Collections.Generic;
using Xamarin.Forms;

namespace AutocompleteSample
{
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
                AutoCompleteSource = new List<string>()
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

    }
}

{% endhighlight %}

{% endtabs %}

The following event will be triggered

{% tabs %}

{% highlight C# %}

       private void autoComplete_SelectionChanged(object sender, Syncfusion.SfAutoComplete.XForms.SelectionChangedEventArgs e)
        {
            DisplayAlert("Selection Changed", "SelectedItem: " + autoComplete.SelectedItem, "OK");
        }

{% endhighlight %}

{% endtabs %}
