---
layout : post
title : Interaction in Syncfusion AutoComplete Control in Xamarin.
description : Learn how to perform an operation while changing its selection from dropdown list in Xamarin.
platform : Xamarin
control : AutoComplete
documentation : ug
---

# How To

## How to perform an operation when selecting an item from drop-down list?

You can perform an operation when selecting an item among the filtered suggestions using the `SelectionChanged` event. The SelectionChanged event returns the following arguments:

<table>
<tr>
<th>Members</th>
<th>Description</th>
</tr>
<tr>
<td>AddedItems</td>
<td>Shows recently added item in AutoComplete.</td>
</tr>
<tr>
<td>RemovedItems</td>
<td>Shows recently removed items in AutoComplete.</td>
</tr>
<tr>
<td>Value</td>
<td>Holds all selected items in AutoComplete.</td>
</tr>
</table>

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage
    xmlns="http://xamarin.com/schemas/2014/forms"
    xmlns:autocomplete="clr-namespace:Syncfusion.SfAutoComplete.XForms;assembly=Syncfusion.SfAutoComplete.XForms"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
    xmlns:local="clr-namespace:Events"
    x:Class="Events.MainPage">
    <ContentPage.BindingContext>
        <local:EmployeeViewModel/>
    </ContentPage.BindingContext>
    <ContentPage.Content>
        <StackLayout>
            <autocomplete:SfAutoComplete
                DisplayMemberPath="Name"
                DataSource="{Binding EmployeeCollection}" 
                SelectionChanged="Handle_SelectionChanged"/>
        </StackLayout> 
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}

{% highlight c# %}
	
using System;
using System.Collections;
using System.Collections.Generic;
using System.Collections.ObjectModel;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Xamarin.Forms;

namespace Events
{
    public partial class MainPage : ContentPage
    {
         StackLayout stack;
        EmployeeViewModel employeeViewModel;

        public MainPage()
        {
            InitializeComponent();
            stack = new StackLayout();
            employeeViewModel = new EmployeeViewModel();
            SfAutoComplete autocomplete = new SfAutoComplete()
            {
                DisplayMemberPath = "Name",
                DataSource = employeeViewModel.EmployeeCollection,
            };
            autocomplete.BindingContext = employeeViewModel;
            autocomplete.SelectionChanged += Handle_SelectionChanged;
            stack.Children.Add(autocomplete);
            this.Content = stack;
        }
    }
}

{% endhighlight %}

{% endtabs %}

The following event will be called. 

{% tabs %}

{% highlight C# %}


        void Handle_SelectionChanged(object sender, Syncfusion.SfAutoComplete.XForms.SelectionChangedEventArgs e)
        {
            var addedEmployee = e.AddedItems as Employee;
            string addedItems = addedEmployee != null ? addedEmployee.Name : "null";
            var removedEmployee = e.RemovedItems as Employee;
            string removedItems = removedEmployee != null ? removedEmployee.Name : "null";
            DisplayAlert("SelectionChanged", "AddedItems: " + addedItems + "\n" + "RemovedItems: " + removedItems, "Ok");
        }

{% endhighlight %}

{% endtabs %}

Create simple `EmployeeViewModel` that contains the properties of  `Employee` class 

{% tabs %}

{% highlight C# %}

 public class Employee
    {
        private int id;
        private string name;

        public int ID
        {
            get
            {
                return this.id;
            }

            set
            {
                this.id = value;
            }
        }

        public string Name
        {
            get
            {
                return this.name;
            }

            set
            {
                this.name = value;
            }
        }
    }

    public class EmployeeViewModel
    {
        private ObservableCollection<Employee> employeeCollection;

        public ObservableCollection<Employee> EmployeeCollection
        {
            get
            {
                return this.employeeCollection;
            }

            set
            {
                this.employeeCollection = value;
            }
        }

        public EmployeeViewModel()
        {
            employeeCollection = new ObservableCollection<Employee>();
            employeeCollection.Add(new Employee() { ID = 1, Name = "Eric" });
            employeeCollection.Add(new Employee() { ID = 2, Name = "James" });
            employeeCollection.Add(new Employee() { ID = 3, Name = "Jacob" });
            employeeCollection.Add(new Employee() { ID = 4, Name = "Lucas" });
            employeeCollection.Add(new Employee() { ID = 5, Name = "Mark" });
            employeeCollection.Add(new Employee() { ID = 6, Name = "Aldan" });
            employeeCollection.Add(new Employee() { ID = 7, Name = "Aldrin" });
            employeeCollection.Add(new Employee() { ID = 8, Name = "Alan" });
            employeeCollection.Add(new Employee() { ID = 9, Name = "Aaron" });
        }
    }

{% endhighlight %}

{% endtabs %}

The following screenshot illustrates the result of adding the item.

![added item is shown in alert window](images/How-To/AddingItem.png)

The following screenshot illustrates the result of removing the item.

![removed item is shown in alert window](images/How-To/RemovingItem.png)