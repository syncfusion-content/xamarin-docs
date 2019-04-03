---
layout: post
title: Retrieving selected value in Syncfusion SfComboBox control
description: Learn how to retrieve selected value from SfComboBox control
platform: xamarin
control: SfComboBox
documentation: ug
---

# Retrieving Selected values

SfComboBox provides a way to get the selected values using SelectedValue and SelectedIndex properties.

## Retrieving the Index of Selected Item

When an item is selected from suggestion list, its index can be retrieved using [`SelectedIndex`] property. 
SelectedIndex property holds the index of selected item in suggestion list. 

The following code example demonstrates the way to retrieve SelectedIndex and display it in an alert.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ComboBox"
	      xmlns:comboBox="clr namespace:Syncfusion.XForms.ComboBox;assembly=Syncfusion.SfComboBox.XForms"
             x:Class="ComboBox.MainPage">

	<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
		<comboBox:SfComboBox HeightRequest="40" x:Name="comboBox" SelectionChanged="ComboBox_SelectionChanged"/>
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
			List<String> countryNames = new List<String>();
			countryNames.Add("Uganda");
			countryNames.Add("Ukraine");
			countryNames.Add("United Arab Emirates");
			countryNames.Add("United Kingdom");
			countryNames.Add("United States");
			comboBox.DataSource = countryNames;
		}

		private void ComboBox_SelectionChanged(object sender, Syncfusion.XForms.ComboBox.SelectionChangedEventArgs e)
		{
			DisplayAlert("Selection Changed", "Selected Index: " + comboBox.SelectedIndex, "OK");
		}
	}
}

{% endhighlight %}

{% endtabs %}

## Retrieving the Value of Selected Item

When an item is selected from suggestion list, selected value can be retrieved using [`SelectedValue`] property. If the DataSource is bound to string data, then selected string is set to the SelectedValue property.  

The following code example demonstrates the way to retrieve SelectedValue and display it in an alert.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ComboBox"
			 xmlns:comboBox="clr-namespace:Syncfusion.XForms.ComboBox;assembly=Syncfusion.SfComboBox.XForms"
             x:Class="ComboBox.MainPage">

	<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
		<comboBox:SfComboBox HeightRequest="40" x:Name="comboBox" SelectionChanged="ComboBox_SelectionChanged"/>
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
			List<String> countryNames = new List<String>();
			countryNames.Add("Uganda");
			countryNames.Add("Ukraine");
			countryNames.Add("United Arab Emirates");
			countryNames.Add("United Kingdom");
			countryNames.Add("United States");
			comboBox.DataSource = countryNames;
		}

		private void ComboBox_SelectionChanged(object sender, Syncfusion.XForms.ComboBox.SelectionChangedEventArgs e)
		{
			DisplayAlert("Selection Changed", "Selected Value: " + comboBox.SelectedValue.ToString(), "OK");
		}
	}
}

{% endhighlight %}

{% endtabs %}

### Retrieving a Member of Model Object

If the DataSource is bound to business object data, there is an additional step to get the SelectedValue. The model class may have one or more properties. So, it is necessary to intimate AutoComplete that which property of model class should be stored in SelectedValue property. This can be accomplished by [`SelectedValuePath`] property.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ComboBox"
			 xmlns:comboBox="clr-namespace:Syncfusion.XForms.ComboBox;assembly=Syncfusion.SfComboBox.XForms"
             x:Class="ComboBox.MainPage">

	<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
		<comboBox:SfComboBox HeightRequest="40" x:Name="comboBox" DataSource="{Binding EmployeeCollection}" DisplayMemberPath="Name" SelectedValuePath="ID" SelectionChanged="ComboBox_SelectionChanged"/>
	</StackLayout>

</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;
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
			comboBox.BindingContext = new EmployeeViewModel();
		}

		private void ComboBox_SelectionChanged(object sender, Syncfusion.XForms.ComboBox.SelectionChangedEventArgs e)
		{
			DisplayAlert("Selection Changed", "Selected Value: " + comboBox.SelectedValue.ToString(), "OK");
		}
	}
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
	public class EmployeeViewModel
	{
		private ObservableCollection<Employee> employeeCollection;
		public ObservableCollection<Employee> EmployeeCollection
		{
			get { return employeeCollection; }
			set { employeeCollection = value; }
		}
		public EmployeeViewModel()
		{
			employeeCollection = new ObservableCollection<Employee>();
			employeeCollection.Add(new Employee() { ID = 1, Name = "Eric" });
			employeeCollection.Add(new Employee() { ID = 2, Name = "James" });
			employeeCollection.Add(new Employee() { ID = 3, Name = "Jacob" });
			employeeCollection.Add(new Employee() { ID = 4, Name = "Lucas" });
			employeeCollection.Add(new Employee() { ID = 5, Name = "Mark" });
		}
	}
}


{% endhighlight %}

{% endtabs %}

If the DataSource is bound to business object data, the selected item can be set initially by specifying the index of the data source item. The property specified in the `SelectedValuePath` will be displayed with respect to index of the selected item.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:ComboBox"
			 xmlns:comboBox="clr-namespace:Syncfusion.XForms.ComboBox;assembly=Syncfusion.SfComboBox.XForms"
             x:Class="ComboBox.MainPage">

	<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
		<comboBox:SfComboBox HeightRequest="40" x:Name="comboBox" DisplayMemberPath="Name" SelectedValuePath="ID" SelectionChanged="ComboBox_SelectionChanged"/>
	</StackLayout>

</ContentPage>

{% endhighlight %}

{% highlight c# %}

using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;
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
			var employeeCollection = new ObservableCollection<Employee>
			{
				new Employee{ ID = 1, Name = "Eric" },
				new Employee{ ID = 2, Name = "James" },
				new Employee{ ID = 3, Name = "Jacob" },
				new Employee{ ID = 4, Name = "Lucas" },
				new Employee{ ID = 5, Name = "Mark" }
			};
			comboBox.DataSource = employeeCollection;
			comboBox.SelectedItem = employeeCollection[4];
		}

		private void ComboBox_SelectionChanged(object sender, Syncfusion.XForms.ComboBox.SelectionChangedEventArgs e)
		{
			DisplayAlert("Selection Changed", "Selected Value: " + comboBox.SelectedValue.ToString(), "OK");
		}
	}
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
}

{% endhighlight %}

{% endtabs %}

