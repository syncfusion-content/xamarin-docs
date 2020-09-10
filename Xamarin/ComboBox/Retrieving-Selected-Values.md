---
layout: post
title: Retrieving selected value in Syncfusion ComboBox control.
description: This section describes how to get the selected value and set the selected value in the SfComboBox control.
platform: xamarin
control: SfComboBox
documentation: ug
---

# Handling Selected Items

SfComboBox provides a way to handle the selected item using the following properties:
* SelectedIndex
* SelectedIndices
* SelectedItem

## SelectedIndex

You can get or set the index of the selected item using the [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_SelectedIndexProperty_) property. It is applicable only when [`MultiSelectMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_MultiSelectModeProperty) is set to None. SelectedIndex will accept integer values.

### Set the index of item to be selected

The [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_SelectedIndexProperty_) property holds the index of selected item in suggestion list. 

{% tabs %}

{% highlight xaml %}
 
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ComboBox"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:comboBox="clr namespace:Syncfusion.XForms.ComboBox;assembly=Syncfusion.SfComboBox.XForms"
             x:Class="ComboBox.MainPage">
 <StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <comboBox:SfComboBox x:Name="comboBox" HeightRequest="40" MultiSelectMode="None" SelectedIndex="1">
            <comboBox:SfComboBox.ComboBoxSource>
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
            </comboBox:SfComboBox.ComboBoxSource>
        </comboBox:SfComboBox>
    </StackLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Xamarin.Forms;

namespace ComboBox
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
            SfComboBox comboBox = new    SfComboBox()
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

         stackLayout.Children.Add(comboBox);
         this.Content = stackLayout;
            }
    }
}

{% endhighlight %}

{% endtabs %}

### Retrieve the index of selected item

When an item is selected from suggestion list, its index can be retrieved using the [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_SelectedIndexProperty_) property. 

The following code sample demonstrates how to retrieve [`SelectedIndex`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_SelectedIndexProperty_) and display it in an alert.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ComboBox"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:comboBox="clr namespace:Syncfusion.XForms.ComboBox;assembly=Syncfusion.SfComboBox.XForms"
             x:Class="ComboBox.MainPage">
    <StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <comboBox:SfComboBox x:Name="comboBox" HeightRequest="40" MultiSelectMode="None" SelectionChanged="ComboBox_SelectionChanged">
            <comboBox:SfComboBox.ComboBoxSource>
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
            </comboBox:SfComboBox.ComboBoxSource>
        </comboBox:SfComboBox>
    </StackLayout> 
</ContentPage>

{% endhighlight %}

{% highlight c# %}
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Xamarin.Forms;

namespace ComboBox
{
    public partial class MainPage : ContentPage
    {
        SfComboBox comboBox;
        public MainPage()
     {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = 30
            };

            comboBox = new SfComboBox()
            {
                HeightRequest = 40,MultiSelectMode=MultiSelectMode.None,
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

            comboBox.SelectionChanged += comboBox_SelectionChanged;
            stackLayout.Children.Add(comboBox);
            this.Content = stackLayout;
        }

        private void comboBox_SelectionChanged(object sender, Syncfusion.XForms.ComboBox.SelectionChangedEventArgs e)
        {
            DisplayAlert("Selection Changed", "SelectedIndex: " + comboBox.SelectedIndex, "OK");
        }
    }
}

{% endhighlight %}

{% endtabs %}

## SelectedIndices

You can get or set the indices of the selected items using the [`SelectedIndices`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_SelectedIndicesProperty) property. It is applicable when [`MultiSelectMode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_MultiSelectModeProperty) is set to either Token or Delimiter. SelectedIndices will accept collection of integer.

### Set the indices of items

The [`SelectedIndices`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_SelectedIndicesProperty) property holds the indices of the selected items in suggestion list.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ComboBox"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:comboBox="clr namespace:Syncfusion.XForms.ComboBox;assembly=Syncfusion.SfComboBox.XForms"
             x:Class="ComboBox.MainPage">
 <StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <comboBox:SfComboBox x:Name="comboBox" HeightRequest="40" MultiSelectMode="Token" SelectedIndices="{Binding SelectedIndices}">
            <comboBox:SfComboBox.ComboBoxSource>
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
            </comboBox:SfComboBox.ComboBoxSource>
        </comboBox:SfComboBox>
    </StackLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Xamarin.Forms;

namespace ComboBox
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
            this.BindingContext = this;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Retrieve the indices of selected item

When an item is selected from suggestion list, its index can be retrieved using the [`SelectedIndices`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_SelectedIndicesProperty) property.

The following code sample demonstrates how to retrieve [`SelectedIndices`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_SelectedIndicesProperty) and display them in ListView.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ComboBox"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:comboBox="clr namespace:Syncfusion.XForms.ComboBox;assembly=Syncfusion.SfComboBox.XForms"
             x:Class="ComboBox.MainPage">
    <StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <comboBox:SfComboBox x:Name="comboBox"HeightRequest="40" MultiSelectMode="Token">
            <comboBox:SfComboBox.ComboBoxSource>
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
            </comboBox:SfComboBox.ComboBoxSource>
        </comboBox:SfComboBox>
        <ListView 
            x:Name="MainListView"  
            RowHeight="30" 
            ItemsSource="{Binding Source={x:Reference comboBox},Path=SelectedIndices}">
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

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Xamarin.Forms;

namespace ComboBox
{
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
}

{% endhighlight %}

{% endtabs %}

## SelectedItem

The `SelectedItem` property is used to select a particular item from the suggestion list. You can either get or set the SelectedItem.

### How to set the SelectedItem

The following code sample demonstrates how to set `SelectedItem`.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ComboBox"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:comboBox="clr namespace:Syncfusion.XForms.ComboBox;assembly=Syncfusion.SfComboBox.XForms"
             x:Class="ComboBox.MainPage">
 <StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <comboBox:SfComboBox x:Name="comboBox" HeightRequest="40" SelectedItem="Angola">
            <comboBox:SfComboBox.ComboBoxSource>
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
            </comboBox:SfComboBox.ComboBoxSource>
        </comboBox:SfComboBox>
    </StackLayout>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Xamarin.Forms;

namespace ComboBox
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
            SfComboBox comboBox = new SfComboBox()
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

            stackLayout.Children.Add(comboBox);
            this.Content = stackLayout;
        }
    }
}

{% endhighlight %}

{% endtabs %}

### Retrieve the selected item

When an item is selected from suggestion list, it can be retrieved using the [`SelectedItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_SelectedItemProperty) property. 

The `SelectedValuePath` API is used to retrieve the value of the selected item in drop-down when the item is selected. The `SelectedValue` property is updated based on the selection. For loading the default values in the control, use only the SelectedItem, and the SelectedValue is used for retrieving the value of our desired property[ID] based on the selection.

There are scenarios in which SelectedValue can have duplicate items when DisplayMemberPath is loaded with Countries and SelectedValue is bound to Continent; it will be the same for many countries. In such scenarios, you cannot populate based on SelectedValue.

The following code sample demonstrates how to retrieve [`SelectedItem`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_SelectedItemProperty) and display it in an alert.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ComboBox"
             xmlns:ListCollection="clr-namespace:System.Collections.Generic;assembly=netstandard"
             xmlns:comboBox="clr namespace:Syncfusion.XForms.ComboBox;assembly=Syncfusion.SfComboBox.XForms"
             x:Class="ComboBox.MainPage">
   <ContentPage.BindingContext>
      <local:EmployeeViewModel/>
   </ContentPage.BindingContext>
    <StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
        <comboBox:SfComboBox x:Name="comboBox" HeightRequest="40" MultiSelectMode="None"  DisplayMemberPath ="Name" DataSource="{Binding EmployeeCollection}" SelectedItem="{Binding SelectedItem,Mode=TwoWay}"  SelectionChanged="ComboBox_SelectionChanged">
           
        </comboBox:SfComboBox>
    </StackLayout> 
</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Xamarin.Forms;

namespace ComboBox
{  
    public partial class MainPage : ContentPage
    {
   
       SfComboBox comboBox;
       EmployeeViewModel ViewModel;
        public MainPage()
        {
            InitializeComponent();
            StackLayout stackLayout = new StackLayout()
            {
                VerticalOptions = LayoutOptions.Start,
                HorizontalOptions = LayoutOptions.Start,
                Padding = 30
            };
            
            comboBox = new SfComboBox();
            ViewModel = new EmployeeViewModel();
            comboBox.HeightRequest = 40
            comboBox.DisplayMemberPath = "Name";
            comboBox.DataSource = ViewModel.EmployeeCollection
            Binding selectedItem = new Binding("SelectedItem");
            selectedItem.Source = ViewModel;
            selectedItem.Mode = BindingMode.TwoWay;
            BindingOperations.SetBinding(comboBox, comboBox.SelectedItemProperty, selectedItem);
            comboBox.MultiSelectMode = MultiSelectMode.None
            comboBox.SelectionChanged += ComboBox_SelectionChanged;
            stackLayout.Children.Add(comboBox);
            this.BindingContext = ViewModel;
            this.Content = stackLayout;

        }
          
        //ComboBox SelectionChangedEvent has been created here
        private void ComboBox_SelectionChanged(object sender, Syncfusion.XForms.ComboBox.SelectionChangedEventArgs e)
        {
            DisplayAlert("Selection Changed", "SelectedItem: " + comboBox.SelectedItem, "OK");
        }
    }
}
       
{% endhighlight %}
{% endtabs %}

Define a simple model class employee with fields ID and Name, and then populate employee data and `SelectedItem` in ViewModel.

{% tabs %}
{% highlight c# %}

    public class Employee
    {
         private int id;
         public int ID
         {
	      get { return id; }
	      set { id = value; }
         }

         private string name;
         public string Name
         {
	      get { return name; }
	      set { name = value; }
         }
     }

    public class EmployeeViewModel : INotifyPropertyChanged
    {
        private ObservableCollection<Employee> employeeCollection;
        public ObservableCollection<Employee> EmployeeCollection
        {
            get { return employeeCollection; }
            set 
            { 
                employeeCollection = value; 
            }
        }

        private object selectedItem;

        public event PropertyChangedEventHandler PropertyChanged;

        private void NotifyPropertyChanged([CallerMemberName] String propertyName = "")
        {
            PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
        }


        public object SelectedItem
        {
            get { return selectedItem; }
            set
            { 
                selectedItem = value;
                NotifyPropertyChanged();
            }
        }

        public EmployeeViewModel()
        {
            employeeCollection = new ObservableCollection<Employee>();
            employeeCollection.Add(new Employee() { ID = 1, Name = "Frank" });
            employeeCollection.Add(new Employee() { ID = 2, Name = "James" });
            employeeCollection.Add(new Employee() { ID = 3, Name = "Steve" });
            employeeCollection.Add(new Employee() { ID = 4, Name = "Lucas" });
            employeeCollection.Add(new Employee() { ID = 5, Name = "Mark" });
            employeeCollection.Add(new Employee() { ID = 6, Name = "Michael" });
            employeeCollection.Add(new Employee() { ID = 7, Name = "Aldrin" });
            employeeCollection.Add(new Employee() { ID = 8, Name = "Jack" });
            employeeCollection.Add(new Employee() { ID = 9, Name = "Howard" });

            SelectedItem = EmployeeCollection[2];
        }
    }

{% endhighlight %}
{% endtabs %}