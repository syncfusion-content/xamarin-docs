---
layout : post
title : Filter Suggestions for Syncfusion ComboBox Control in Xamarin.Forms
description : Learn how to filter the suggestions in ComboBox 
platform : Xamarin.Forms
control : SfComboBox
documentation : ug
---

# Filtering
ComboBox provides enable the filer option for filtering the suggestions in drop down. 

{% tabs %}	

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30"> 
<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="true" AllowFiltering="true" MaximumDropDownHeight="150" /> 
</StackLayout>

{% endhighlight %}
	
{% highlight c# %}
	
List<String> countryNames = new List<String>();
countryNames.Add("Afghanistan"); 
countryNames.Add("Akrotiri"); 
countryNames.Add("Albania");
countryNames.Add("Algeria");
countryNames.Add("American Samoa");
countryNames.Add("Andorra");
countryNames.Add("Angola");
countryNames.Add("Anguilla");
countryNames.Add("Antarctica");
countryNames.Add("Antigua and Barbuda");
countryNames.Add("Argentina");
comboBox.DataSource = countryNames; 
comboBox.IsEditableMode = true;
comboBox.AllowFiltering = true;
	 
{% endhighlight %}

{% endtabs %}

![](images/ComboBox-Filtering-Options/allowfiltering.png)

## Types of Filtering Options

The phenomenon of string comparison for filtering suggestions can be changed using the `SuggestionMode` property. The default filtering strategy is “StartsWith” and it is case insensitive. The available filtering modes are

* StartsWith

* StartsWithCaseSensitive

* Contains

* ContainsWithCaseSensitive

* Equals

* EqualsWithCaseSensitive

* EndsWith

* EndsWithCaseSensitive

* Custom

### Filtering Words that Starts with Input Text

Displays all the matches that starts with the typed characters in control. This strategy is case in-sensitive.
	
{% tabs %}	

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="true" AllowFiltering="true" SuggestionMode="StartsWith"/>
</StackLayout>

{% endhighlight %}
	
{% highlight c# %}
	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
comboBox.DataSource = countryNames;
comboBox.IsEditableMode = true;
comboBox.AllowFiltering = true;
comboBox.SuggestionMode = SuggestionMode.StartsWith;
	 
{% endhighlight %}

{% endtabs %}

![](images/ComboBox-Filtering-Options/starts-with.png)

#### Filtering Words that Starts with Input Text - CaseSensitive

Displays all the matches that starts with the typed characters in control. This strategy is case sensitive.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<comboBox:SfComboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="true" AllowFiltering="true" SuggestionMode="StartsWithCaseSensitive"/> 
</StackLayout>

{% endhighlight %}

{% highlight c# %}
	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
comboBox.DataSource = countryNames;
comboBox.IsEditableMode = true;
comboBox.AllowFiltering = true;
comboBox.SuggestionMode= SuggestionMode.StartsWithCaseSensitive;

{% endhighlight %}

{% endtabs %}

![](images/ComboBox-Filtering-Options/starts-with-case-sensitive.png)

### Filtering Words that Contains the Input Text

Displays all the matches that contains the typed characters in control. This strategy is case in-sensitive.
	
{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="true" AllowFiltering="true" SuggestionMode="Contains"/>                            
</StackLayout>

{% endhighlight %}

{% highlight c# %}
	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
countryNames.Add("Italy");
comboBox.DataSource = countryNames;
comboBox.IsEditableMode = true;
comboBox.AllowFiltering = true;
comboBox.SuggestionMode= SuggestionMode.Contains;
	 
{% endhighlight %}

{% endtabs %}

![](images/ComboBox-Filtering-Options/contains.png)

#### Filtering Words that Contains the Input Text - CaseSensitive

Displays all the matches that contains the typed characters in control. This strategy is case sensitive.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="true" AllowFiltering="true" SuggestionMode="ContainsWithCaseSensitive"/>                            
</StackLayout>

{% endhighlight %}

{% highlight c# %}

List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
countryNames.Add("Italy");
comboBox.DataSource = countryNames;
comboBox.IsEditableMode = true;
comboBox.AllowFiltering = true;
comboBox.SuggestionMode= SuggestionMode.ContainsWithCaseSensitive;

{% endhighlight %}

{% endtabs %}

![](images/ComboBox-Filtering-Options/contains-casesensitive.png)

### Filtering Words that Equals the Input Text

Displays all the words that completely matches with the typed characters in control. This strategy is case in-sensitive.
	
{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfCpomboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="true" AllowFiltering="true" SuggestionMode="Equals"/>        
</StackLayout>

{% endhighlight %}

{% highlight c# %}
	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
comboBox.DataSource = countryNames;
comboBox.IsEditableMode = true;
comboBox.AllowFiltering = true;
comboBox.SuggestionMode= SuggestionMode.Equals;

{% endhighlight %}

{% endtabs %}

#### Filtering Words that Equals the Input Text - CaseSensitive

Displays all the words that completely matches with the typed characters in control. This strategy is case sensitive.
	
{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="true" AllowFiltering="true" SuggestionMode="EqualsWithCaseSensitive"/>             
</StackLayout>

{% endhighlight %}

{% highlight c# %}
	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
comboBox.DataSource = countryNames;
comboBox.IsEditableMode = true;
comboBox.AllowFiltering = true;
comboBox.SuggestionMode= SuggestionMode.EqualsWithCaseSensitive;

{% endhighlight %}

{% endtabs %}

### Custom

Filter items in the suggestion list based on a custom search by the user. This will help to apply our typo toleration functionality to the control.

![](images/ComboBox-Filtering-Options/custom_filter.png)


{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" DropDownTextSize="20" x:Name="comboBox" IsEditableMode="true" AllowFiltering="true" ComboBoxMode="Suggest" MaximumDropDownHeight="200" SuggestionMode="Custom"/>
</StackLayout>

{% endhighlight %}

{% highlight c# %}

    public ComboBoxPage()
    {
        InitializeComponent();
        List<string> list = new List<string>();
        list.Add("Albania");
        list.Add("Algeria");
        list.Add("American Samoa");
        list.Add("Andorra");
        list.Add("Angola");
        list.Add("Anguilla");
        comboBox.ComboBoxSource = list;
        comboBox.IsEditableMode = true;
        comboBox.AllowFiltering = true;
        comboBox.Filter = ContainingSpaceFilter;
    }
    public bool ContainingSpaceFilter(string search, object item)
    {
        string text = item.ToString().ToLower();
        if (item != null)
        {
            try
            {
                var split = search.Split(' ');
                foreach (var results in split)
                {
                    if (!text.Contains(results.ToLower()))
                    {
                        return true;
                    }
                    else
                        return false;
                }
                return true;
            }
            catch (Exception)
            {
                return (text.Contains(search));
            }
        }
        else
            return false;
    }

	{% endhighlight %}

    {% endtabs %}

### Filtering Words that Ends with the Input Text

Displays all the matches that ends with the typed characters in control. This strategy is case in-sensitive.

{% tabs %}
	
{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" WidthRequest="180" x:Name="comboBox" IsEditableMode="true" AllowFiltering="true" SuggestionMode="EndsWith"/>                            
</StackLayout>

{% endhighlight %}

{% highlight c# %}
	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
comboBox.DataSource = countryNames;
comboBox.IsEditableMode = true;
comboBox.AllowFiltering = true;
comboBox.SuggestionMode= SuggestionMode.EndsWith;
 
{% endhighlight %}

{% endtabs %}

![](images/ComboBox-Filtering-Options/ends-with.png)


#### Filtering Words that Ends with the Input Text - CaseSensitive 

Displays all the matches that ends with the typed characters in control. This strategy is case sensitive.
	
{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="true" AllowFiltering="true"  SuggestionMode="EndsWithCaseSensitive"/>           
</StackLayout>

{% endhighlight %}

{% highlight c# %}
	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
comboBox.DataSource = countryNames;
comboBox.IsEditableMode = true;
comboBox.AllowFiltering = true;
comboBox.SuggestionMode= SuggestionMode.EndsWithCaseSensitive;

{% endhighlight %}

{% endtabs %}

![](images/ComboBox-Filtering-Options/ends-with-case-sensitive.png)


## ComboBox Modes

ComboBox provides three different ways to display the filtered suggestions. They are 

* Suggest - displaying suggestion in drop down list

* Append - appending the first suggestion to text

* SuggestAppend - Both of these

`ComboBoxeMode` property is used to choose the suggestion display mode in SfComboBox control. The default value is Suggest.

## Suggesting Choices in List

The filtered suggestions are displayed in a drop down list. User can pick an item from the list.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="true" AllowFiltering="true"  ComboBoxMode="Suggest"/>                      
</StackLayout> 
		  
{% endhighlight %}

{% highlight c# %}
	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
comboBox.DataSource = countryNames;
comboBox.IsEditableMode = true;
comboBox.AllowFiltering = true;
comboBox.ComboBoxMode = ComboBoxMode.Suggest;
	 
{% endhighlight %}

{% endtabs %}

![](images/ComboBox-Filtering-Options/suggest.png)

## Appending Suggestion to Text

The first item in filtered suggestions is appended to SfComboBox text. In this mode, drop down remains closed.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="true" AllowFiltering="true"  ComboBoxMode="Append"/>                       
</StackLayout> 
		  
{% endhighlight %}

{% highlight c# %}
	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
comboBox.DataSource = countryNames;
comboBox.IsEditableMode = true;
comboBox.AllowFiltering = true;
comboBox.ComboBoxMode = ComboBoxMode.Append;
	 
{% endhighlight %}

{% endtabs %}

![](images/ComboBox-Filtering-Options/append.png)

## Suggesting Choices and Appending Suggestions to Text

The text is appended to the first matched item in the suggestions collection and filtered suggestions are displayed in a drop down list. The user can pick from a list directly or use up and down keys for browsing the list.
	
{% tabs %}	

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="true" AllowFiltering="true"  ComboBoxMode="SuggestAppend"/>                
</StackLayout> 
		  
{% endhighlight %}
	
{% highlight c# %}
	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
comboBox.DataSource = countryNames;
comboBox.IsEditableMode = true;
comboBox.AllowFiltering = true;
comboBox.ComboBoxMode = ComboBoxMode.SuggestAppend;

{% endhighlight %}

{% endtabs %}

![](images/ComboBox-Filtering-Options/suggest-append.png)