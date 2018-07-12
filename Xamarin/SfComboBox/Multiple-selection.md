---
layout: post
title: Multi Selection in Syncfusion SfComboBox control for Xamarin.Forms
description: Learn how to select multiple items in SfComboBox
platform: xamarin
control: SfComboBox
documentation: ug
---
# Multiple Selection

Select multiple items from a suggestion list. There are two ways to perform multi selection in combobox.

* Token Representation

* Delimiter

## Token Representation

Selected items will be displayed with a customizable token representation and the users can remove each tokenized item with the close button.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" MultiSelectMode="Token" TokensWrapMode="Wrap" IsSelectedItemsVisibleInDropDown="false" />                    
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

comboBox.MultiSelectMode = MultiSelectMode.Token;
comboBox.TokensWrapMode = TokensWrapMode.Wrap;
comboBox.IsSelectedItemsVisibleInDropDown = false;

{% endhighlight %}

{% endtabs %}

### Wrap Mode of Token

The selected item can be displayed as token inside SfComboBox in two ways. They are

* `Wrap` - When `TokensWrapMode` is set to `Wrap` the selected items will be wrap to the next line of the SfComboBox.

* `None` - When `TokensWrapMode` is set to `None` the selected item will be wrap in horizontal orientation.

{% tabs %}

{% highlight xaml %}


<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
    <combobox:SfComboBox HeightRequest="40" x:Name="comboBox" DropDownItemHeight="50" DisplayMemberPath="Name" ImageMemberPath="Image" MultiSelectMode="Token" DataSource="{Binding EmployeeCollection}"/>
</StackLayout>

{% endhighlight %}

{% highlight c# %}
namespace combobox
{
    public partial class ComboBoxPage : ContentPage 
    { 
        EmployeeViewModel view = new EmployeeViewModel(); 
        public ComboBoxPage() 
        { 
            InitializeComponent(); 
            // Set TokensWrapMode to Wrap 
            comboBox.TokensWrapMode = TokensWrapMode.Wrap;  
            this.BindingContext = view; 
        } 
    } 

    // Create a Employee Class which holds the Name and image. 
    public class Employee 
    { 
        private string image; 
        public string Image 
        { 
            get { return image; } 
            set { image = value; } 
        } 

        private string name; 
        public string Name 
        { 
            get { return name; } 
            set { name = value; } 
        } 
    } 

    // Create EmployeeViewModel class holds the collection of employee data. 
    public class EmployeeViewModel :INotifyPropertyChanged 
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
            employeeCollection.Add(new Employee() { Image = "John.png", Name = "John" }); 
            employeeCollection.Add(new Employee() { Image = "Justin.png", Name = "Justin" }); 
            employeeCollection.Add(new Employee() { Image = "Jerome.png", Name = "Jerome" });
            employeeCollection.Add(new Employee() { Image = "Jessica.png", Name = "Jessica" }); 
            employeeCollection.Add(new Employee() { Image = "Victoria.png", Name = "Victoria" });
        } 
 
        public event PropertyChangedEventHandler PropertyChanged; 
        private void RaisePropertyChanged(String name) 
        { 
        if (PropertyChanged != null) 
            this.PropertyChanged(this, new PropertyChangedEventArgs(name)); 
        } 
    }
} 

{% endhighlight %}

{% endtabs %}


![](images/MultiSelect/TokenRepresentation_Wrap.png)
 
### Token Customization

Customization can be done for Token. There are various ways to customize the tokens. They are as follows.

* `TextColor` - sets the color of the text inside the token.

* `FontSize` - sets the size of the Font inside the token.

* `FontFamily` - sets the Font family for the text inside the token.

* `BackgroundColor` - sets the background color of the token.

* `SelectedBackgroundColor` - sets the background color of the token when it is selected.

* `IsCloseButtonVisible` - Enables and disables the close button inside SfComboBox.

* `DeleteButtonColor` - sets the color of the close button inside SfComboBox.

* `CornerRadius` - sets the corner radius for the token.



{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
    <combobox:SfComboBox HeightRequest="40" x:Name="comboBox" DropDownItemHeight="50" DisplayMemberPath="Name" ImageMemberPath="Image" MultiSelectMode="Token" TokensWrapMode="Wrap" DataSource="{Binding EmployeeCollection}"/>
</StackLayout>

{% endhighlight %}

{% highlight c# %}

// Token Customization

TokenSettings token = new TokenSettings();
token.FontSize = 16;
token.BackgroundColor = Color.FromHex("#66ccff");
token.TextColor = Color.White;
token.SelectedBackgroundColor = Color.FromHex("#ffffe0");
token.DeleteButtonColor = Color.Brown;
token.FontFamily= "Times New Roman";
token.IsCloseButtonVisible = true;
token.CornerRadius = 15;
comboBox.TokenSettings = token;
 
{% endhighlight %}

{% endtabs %}


![](images/MultiSelect/TokenRepresentation.png)

## Delimiter

When selecting the multiple items, the selected items can be divided with a desired character given for a delimiter. We can set delimiter character with the `Delimiter` property.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" MultiSelectMode="Delimiter"  Delimiter="," /> 
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

combobox.MultiSelectMode = MultiSelectMode.Delimiter;
combobox.Delimiter = ",";

{% endhighlight %}

{% endtabs %}

![](images/MultiSelect/Delimiter.png)