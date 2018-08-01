---
layout: post
title: Multi Selection in Syncfusion SfAutoComplete control for Xamarin.Forms
description: Learn how to restrict maximum suggestion to be displayed in SfAutoComplete
platform: xamarin
control: SfAutoComplete
documentation: ug
---
# Multiple Selection

Select multiple items from a suggestion list. There are two ways to perform multi selection in autocomplete.

* Token Representation

*  Delimiter

## Token Representation

Selected items will be displayed with a customizable token representation and the users can remove each tokenized item with the close button.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" MultiSelectMode="Token" TokensWrapMode="Wrap" IsSelectedItemsVisibleInDropDown="false" />                    
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

autoComplete.MultiSelectMode=MultiSelectMode.Token;
autoComplete.TokensWrapMode=TokensWrapMode.Wrap;
autoComplete.IsSelectedItemsVisibleInDropDown=false;

{% endhighlight %}

{% endtabs %}

### Wrap Mode of Token

The selected item can be displayed as token inside SfAutoComplete in two ways. They are

* `Wrap` - When `TokensWrapMode` is set to `Wrap` the selected items will be wrap to the next line of the SfAutoComplete.

* `None` - When `TokensWrapMode` is set to `None` the selected item will be wrap in horizontal orientation.

{% tabs %}

{% highlight xaml %}


<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
    <autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" DropDownItemHeight="50" DisplayMemberPath="Name" ImageMemberPath="Image" MultiSelectMode="Token" DataSource="{Binding EmployeeCollection}">
    </autocomplete:SfAutoComplete>
</StackLayout>

{% endhighlight %}

{% highlight c# %}
namespace autocomplete
{
public partial class autocompletePage : ContentPage
{
EmployeeViewModel view = new EmployeeViewModel();
public autocompletePage()
{
InitializeComponent();
// Set TokensWrapMode to Wrap
autoComplete.TokensWrapMode = TokensWrapMode.Wrap;
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
employeeCollection.Add(new Employee() { Image = "James.png", Name = "James" });
employeeCollection.Add(new Employee() { Image = "Jacob.png", Name = "Jacob" });
employeeCollection.Add(new Employee() { Image = "Joy.png", Name = "Joy" });
employeeCollection.Add(new Employee() { Image = "Justin.png", Name = "Justin" });
employeeCollection.Add(new Employee() { Image = "Jerome.png", Name = "Jerome" });
employeeCollection.Add(new Employee() { Image = "Jessica.png", Name = "Jessica" });
employeeCollection.Add(new Employee() { Image = "Victoria.png", Name = "Victoria" });

}

public int GetHeight(bool value)
{
if (value)
return 80;
}

private int toHeight = 40;
public int ToHeight
{
get { return toHeight; }
set
{
toHeight = value;
RaisePropertyChanged("ToHeight");
}
}
private bool isToFocused = false;
public bool IsToFocused
{
get { return isToFocused; }
set
{
isToFocused = value;
ToHeight = GetHeight(value);
RaisePropertyChanged("IsToFocused");
}
}
public event PropertyChangedEventHandler PropertyChanged;
private void RaisePropertyChanged(String name)
{
if (PropertyChanged != null)
this.PropertyChanged(this, new PropertyChangedEventArgs(name));
}
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

* `IsCloseButtonVisible` - Enables and disables the close button inside SfAutoComplete.

* `DeleteButtonColor` - sets the color of the close button inside SfAutoComplete.

* `CornerRadius` - sets the corner radius for the token.



{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
    <autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" DropDownItemHeight="50" DisplayMemberPath="Name" ImageMemberPath="Image" MultiSelectMode="Token" TokensWrapMode="Wrap" DataSource="{Binding EmployeeCollection}">
    </autocomplete:SfAutoComplete>
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
autoComplete.TokenSettings = token;
 
{% endhighlight %}

{% endtabs %}


![](images/MultiSelect/TokenRepresentation.png)

## Delimiter

When selecting the multiple items, the selected items can be divided with a desired character given for a delimiter. We can set delimiter character with the `Delimiter` property.

{% tabs %}
{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" MultiSelectMode="Delimiter"  Delimiter="," />                    
</StackLayout> 

N> The optimal value for Delimiter property is any single character.

{% endhighlight %}

{% highlight c# %}


autoComplete.MultiSelectMode=MultiSelectMode.Delimiter;
autoComplete.Delimiter=",";


{% endhighlight %}

{% endtabs %}

![](images/MultiSelect/Delimiter.png)

### Selection indicator

The autocomplete enables the user to indicate the selected item from the datasource when selecting multiple items from the dropdown. It can be performed by enabling `EnableSelectionIndicator` property.

N> Selection Indicator support has enhanced only on iOS and Android platform.

{% tabs %}
{% highlight xaml %}

 <autocomplete:SfAutoComplete HeightRequest="40" ShowSuggestionsOnFocus="true" IsSelectedItemsVisibleInDropDown="true" IndicatorText="A" IndicatorTextSize="sample.ttf" IndicatorTextColor="Red" EnableSelectionIndicator="true" MultiSelectMode="Token"  x:Name="autoComplete" DataSource="{Binding EmployeeCollection}"/>
       
{% endhighlight %}

{% highlight c# %}

autoComplete.MultiSelectMode=MultiSelectMode.Token;
autoComplete.ShowSuggestionsOnFocus=true;
autoComplete.IsSelectedItemsVisibleInDropDown=true;
autoComplete.IndicatorText= "A";
autoComplete.IndicatorTextSize= "sample.ttf";
autoComplete.IndicatorTextColor = Color.Red;
autoComplete.EnableSelectionIndicator= true;

{% endhighlight %}

{% endtabs %}

### Item padding

The autocomplete enables the user to provide padding for the items inside dropdown using `ItemPadding` property.

N> `ItemPadding` property is available only on iOS and Android platform.

{% tabs %}
{% highlight xaml %}

 <autocomplete:SfAutoComplete ShowSuggestionsOnFocus="true" ItemPadding="20,10,0,0" MultiSelectMode="Token"  x:Name="autoComplete" DataSource="{Binding EmployeeCollection}"/>
       
{% endhighlight %}

{% highlight c# %}

autoComplete.MultiSelectMode=MultiSelectMode.Token;
autoComplete.ShowSuggestionsOnFocus=true;
autoComplete.ItemPadding= new Thickness(20,10,0,0);;

{% endhighlight %}

{% endtabs %}
