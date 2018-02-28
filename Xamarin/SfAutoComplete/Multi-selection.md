---
layout: post
title: Multi Selection in Syncfusion SfAutoComplete control for Xamarin.Forms
description: Learn how to restrict maximum suggestion to be displayed in SfAutoComplete
platform: xamarin
control: SfAutoComplete
documentation: ug
---
# Multi Selection

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

List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
autoComplete.MaximumSuggestion=3;
autoComplete.MultiSelectMode=MultiSelectMode.Token;
autoComplete.TokensWrapMode=TokensWrapMode.Wrap;
autoComplete.IsSelectedItemsVisibleInDropDown=false;
autoComplete.DataSource = countryNames;

{% endhighlight %}

{% endtabs %}

### Token Customization

Customization can be done for Token. Following code illustrate the how to customize the token.


{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
    <autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" DropDownItemHeight="50" DisplayMemberPath="Name" ImageMemberPath="Image" MultiSelectMode="Token" TokensWrapMode="Wrap" DataSource="{Binding EmployeeCollection}">
    </autocomplete:SfAutoComplete>
</StackLayout>

{% endhighlight %}

{% highlight c# %}

namespace autocomplete
{
public partial class autocompletePage : ContentPage
{
    EmployeeViewModel vm = new EmployeeViewModel();
    public autocompletePage()
    {
        InitializeComponent();

        TokenSettings tokensetting = new TokenSettings();
        tokensetting.FontSize = 16;
        tokensetting.BackgroundColor = Color.FromHex("#d3d3d3");
        tokensetting.TextColor = Color.Red;
        tokensetting.SelectedBackgroundColor = Color.FromHex("#ffffe0");
        tokensetting.DeleteButtonColor = Color.Brown;
        tokensetting.IsCloseButtonVisible = true;
        tokensetting.CornerRadius = 3;
        autoComplete.TokenSettings = tokensetting;
        this.BindingContext = vm;
    }
}

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
        employeeCollection.Add(new Employee() { Image = "a0.png", Name = "John" });
        employeeCollection.Add(new Employee() { Image = "a1.png", Name = "James" });
        employeeCollection.Add(new Employee() { Image = "a2.png", Name = "Jacob" });
        employeeCollection.Add(new Employee() { Image = "a3.png", Name = "Joy" });
        employeeCollection.Add(new Employee() { Image = "a4.png", Name = "Justin" });
        employeeCollection.Add(new Employee() { Image = "a5.png", Name = "Jerome" });
        employeeCollection.Add(new Employee() { Image = "b0.png", Name = "Jessica" });
        employeeCollection.Add(new Employee() { Image = "b1.png", Name = "Victoria" });
       
    }
}

}
{% endhighlight %}

{% endtabs %}


![](images/MultiSelect/TokenRepresentation.png)

## Delimiter

Selected items can be divided with a desired character given for a delimiter.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" MultiSelectMode="Delimiter"  Delimiter="*" />                    
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
autoComplete.MaximumSuggestion=3;
autoComplete.MultiSelectMode=MultiSelectMode.Delimiter;
autoComplete.Delimiter="*";
autoComplete.DataSource = countryNames;

{% endhighlight %}

{% endtabs %}

![](images/MultiSelect/Delimiter.png)

