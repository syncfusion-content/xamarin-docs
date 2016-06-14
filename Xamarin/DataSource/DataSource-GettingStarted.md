---
layout: post
title: GettingStarted | DataSource | Xamarin | Syncfusion
description: How to create a sample in DataSource with sorting and grouping.
platform: xamarin
control: DataSource
documentation: UG
---
# DataSource
## Overview
DataSource.Portable is a non UI component that consumes raw data and processes data manipulation operations such as sorting, filtering and grouping saving developers’ time and efforts in building the functionality themselves. We can apply DataSource to any data bound control which can be further processed using the bound DataSource.

![](DataSource-GettingStarted_images/datasource.png)
## Getting started 
### Assembly deployment
After installing Essential Studio for Xamarin, you can find all the required assemblies in the following installation folders,
{Syncfusion Essential Studio Installed location}\Essential Studio\{Syncfusion release version}\lib
***Note: Assemblies can be found in unzipped package location in Mac***
Add the following assemblies to the pcl project as shown below:
**PCL project:**
{% tabs %}
{% highlight c# %}
pcl\Syncfusion.DataSource.Portable.dll
{% endhighlight %}
{% endtabs %}
## Creating your first DataSource in Xamarin.Forms
* This is how the final output will look like on iOS, Android and Windows Phone devices.
![](DataSource-GettingStarted_images/gettingstarted.png)

* Create new **BlankApp** (Xamarin.Forms.Portable) application in**Xamarin Studio** or **Visual Studio**.
* Now, create a simple data source as shown in the following code example. Add the following code example in a newly created class file and save it as **Contacts.cs**file.
{% tabs %}
{% highlight c# %}
public class Contacts : INotifyPropertyChanged
{
    private string contactName;

    public Contacts(string name)
    {
        contactName = name;
    }

    public string ContactName
    {
        get { return contactName; }
        set
        {
            if (contactName != value)
            {
                contactName = value;
                this.RaisedOnPropertyChanged("ContactName");
            }
        }
    }

    public event PropertyChangedEventHandler PropertyChanged;

    public void RaisedOnPropertyChanged(string _PropertyName)
    {
        if (PropertyChanged != null)
        {
            PropertyChanged(this, new PropertyChangedEventArgs(_PropertyName));
        }
    }
}
{% endhighlight %}
{% endtabs %}
* Add the following code example in a newly created class file and save it as **ContactList.cs**file.
{% tabs %}
{% highlight c# %}
public class ContactsList : ObservableCollection<Contacts>, INotifyPropertyChanged
{
    public ContactsList()
    {
        foreach (var cusName in CustomerNames)
        {
            var contact = new Contacts(cusName);
            this.Add(contact);
        }
    }
    string[] CustomerNames = new string[] {
    "Kyle",
    "Gina",
    "Irene",
    "Katie",
    "Michael",
    "Oscar",
    "Ralph",
    "Torrey",
    "William",
    "Bill",
    "Daniel",
    "Frank",
    "Brenda",
    "Danielle",
    "Fiona",
    "Howard",
    "Jack",
    "Larry",
    };
}
{% endhighlight %}
{% endtabs %}
* You can set the source of the DataSource by using the **`**DataSource.Source` property as follows. Now you can bind the DataSource.DisplayItems as ItemsSource for any data bound control.

{% tabs %}
{% highlight c# %}
[C#]
public App()
{
    DataSource dataSource = new DataSource();
    dataSource.Source = new ContactsList();
}
{% endhighlight %}
{% endtabs %}
## Sorting
DataSource also allows to sort the bound source by using the `DataSource.SortDescriptors` property**.**  You can create a `SortDescriptor` for the property to be sorted and add it in the `DataSource.SortDescriptors` collection. 
SortDescriptor object holds following three properties:
* PropertyName: Name of the sorted property.
* Direction: An object of type `ListSortDirection` defines the sorting direction.
* Comparer: Comparer to be applied in when sorting take place
 The following code illustrates this.
{% tabs %}
{% highlight c# %}
[C#]
dataSource.SortDescriptors.Add(new SortDescriptor("ContactName"));
{% endhighlight %}
{% endtabs %}
## Grouping
DataSource also allows to sort the bound source by using the `DataSource.GroupDescriptors` property**.**  You can create a `GroupDescriptor` for the property to be grouped and add it in the `DataSource.GroupDescriptors` collection. 
GroupDescriptor object holds following two properties:
* PropertyName: Name of the grouped property.
* KeySelector: Sets the key selector for grouping
* Comparer: Comparer to be applied in when sorting take place
The following code example illustrates this without Key Selector.
{% tabs %}
{% highlight c# %}
[C#]
dataSource.GroupDescriptors.Add(new GroupDescriptor("ContactName"));

{% endhighlight %}
{% endtabs %}
The following code example illustrates this with Key Selector.
{% tabs %}
{% highlight c# %}
[C#]
    dataSource.GroupDescriptors.Add(new GroupDescriptor() 
    {
        PropertyName = "ContactName",
        KeySelector = (object obj1) =>
        {
            var item = (obj1 as Contacts);
            return item.ContactName[0].ToString();
        }
    });

{% endhighlight %}
{% endtabs %}
## Binding DataSource to a ListView
Please refer the below code example that illustrates binding the created DataSource to a ListView control.
{% tabs %}
{% highlight c# %}
[C#]

public App()
{
    DataSource dataSource = new DataSource();
    dataSource.Source = new ContactsList();
    dataSource.SortDescriptors.Add(new SortDescriptor("ContactName"));
    dataSource.GroupDescriptors.Add(new GroupDescriptor() 
    {
        PropertyName = "ContactName",
        KeySelector = (object obj1) =>
        {
            var item = (obj1 as Contacts);
            return item.ContactName[0].ToString();
        }
    });

  StackLayout stack = new StackLayout();
    stack.Children.Add(new Label()
    {
        TextColor = Color.Black,
        FontSize = 14,
        HeightRequest = 50,
        Text ="Contact List",
        HorizontalTextAlignment = TextAlignment.Center,
        VerticalTextAlignment = TextAlignment.Center,
        BackgroundColor = Color.Gray
    });
           
    listView = new ListView();
    listView.ItemTemplate = new DataTemplate(() =>
    {
        var label = new Label()
        {
            TextColor = Color.Black,
            FontSize = 12,
            VerticalTextAlignment = TextAlignment.Center,
            BackgroundColor = Color.White,
        };
        label.SetBinding(Label.TextProperty, new Binding("ContactName"));
        var viewCell = new ViewCell() { View = label };
        viewCell.BindingContextChanged += ViewCell_BindingContextChanged;
        return viewCell;
    });
    listView.ItemsSource = dataSource.DisplayItems;
    stack.Children.Add(listView);
    MainPage = new ContentPage { Content = stack };
    Device.OnPlatform(iOS:() => MainPage.Padding = new Thickness(0, 20, 0, 0));
}

private void ViewCell_BindingContextChanged(object sender, EventArgs e)
{
    var viewCell = sender as ViewCell;
    if (viewCell.BindingContext is GroupResult)
    {
        var label = new Label()
        {
            TextColor = Color.Black,
            FontSize = 14,
            HeightRequest = 50,
            HorizontalTextAlignment = TextAlignment.Center,
            VerticalTextAlignment = TextAlignment.Center,
            BackgroundColor = Color.Gray
        };
        label.SetBinding(Label.TextProperty, new Binding("Key"));
        viewCell.View = label;
    }
}

{% endhighlight %}
{% endtabs %}
