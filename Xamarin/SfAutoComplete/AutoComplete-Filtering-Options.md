---
layout : post
title : Suggestion mode for Syncfusion AutoComplete Control in Xamarin.Forms
description : This section describes about the different filtering modes to define filtering strategy.
platform : Xamarin.Forms
control : AutoComplete
documentation : ug
---

# AutoComplete Filtering Options

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

## Filtering Words that Starts with Input Text

Displays all the matches that starts with the typed characters in control. This strategy is case in-sensitive.
	
{% tabs %}	

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" SuggestionMode="StartsWith"/>                            
</StackLayout>

{% endhighlight %}
	
{% highlight c# %}
	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
autoComplete.DataSource = countryNames;
autoComplete.SuggestionMode= SuggestionMode.StartsWith;
	 
{% endhighlight %}

{% endtabs %}

![](images/AutoComplete-Filtering-Options/starts-with.png)

### Filtering Words that Starts with Input Text - CaseSensitive

Displays all the matches that starts with the typed characters in control. This strategy is case sensitive.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" SuggestionMode="StartsWithCaseSensitive"/>                            
</StackLayout>

{% endhighlight %}

{% highlight c# %}
	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
autoComplete.DataSource = countryNames;
autoComplete.SuggestionMode= SuggestionMode.StartsWithCaseSensitive;

{% endhighlight %}

{% endtabs %}

![](images/AutoComplete-Filtering-Options/starts-with-case-sensitive.png)

## Filtering Words that Contains the Input Text

Displays all the matches that contains the typed characters in control. This strategy is case in-sensitive.
	
{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" SuggestionMode="Contains"/>                            
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
autoComplete.DataSource = countryNames;
autoComplete.SuggestionMode= SuggestionMode.Contains;
	 
{% endhighlight %}

{% endtabs %}

![](images/AutoComplete-Filtering-Options/contains.png)

### Filtering Words that Contains the Input Text - CaseSensitive

Displays all the matches that contains the typed characters in control. This strategy is case sensitive.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" SuggestionMode="ContainsWithCaseSensitive"/>                            
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
autoComplete.DataSource = countryNames;
autoComplete.SuggestionMode= SuggestionMode.ContainsWithCaseSensitive;

{% endhighlight %}

{% endtabs %}

![](images/AutoComplete-Filtering-Options/contains-casesensitive.png)

## Filtering Words that Equals the Input Text

Displays all the words that completely matches with the typed characters in control. This strategy is case in-sensitive.
	
{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" SuggestionMode="Equals"/>                            
</StackLayout>

{% endhighlight %}

{% highlight c# %}
	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
autoComplete.DataSource = countryNames;
autoComplete.SuggestionMode= SuggestionMode.Equals;

{% endhighlight %}

{% endtabs %}

### Filtering Words that Equals the Input Text - CaseSensitive

Displays all the words that completely matches with the typed characters in control. This strategy is case sensitive.
	
{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" SuggestionMode="EqualsWithCaseSensitive"/>                            
</StackLayout>

{% endhighlight %}

{% highlight c# %}
	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
autoComplete.DataSource = countryNames;
autoComplete.SuggestionMode= SuggestionMode.EqualsWithCaseSensitive;

{% endhighlight %}

{% endtabs %}

### Custom

Filter items in the suggestion list based on a custom search by the user. This will help to apply our typo toleration functionality to the control.

![](images/AutoComplete-Filtering-Options/custom_filter.png)


{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" DropDownTextSize="20" x:Name="autoComplete" AutoCompleteMode="Suggest" MaximumDropDownHeight="200" SuggestionMode="Custom"/>                        
</StackLayout>

{% endhighlight %}

{% highlight c# %}

    public AutoCompletePage()
    {
        InitializeComponent();
        List<string> list = new List<string>();
        list.Add("Albania");
        list.Add("Algeria");
        list.Add("American Samoa");
        list.Add("Andorra");
        list.Add("Angola");
        list.Add("Anguilla");
        autocomplete.AutoCompleteSource = list;
        autocomplete.Filter = ContainingSpaceFilter;
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



## Filtering Words that Ends with the Input Text

Displays all the matches that ends with the typed characters in control. This strategy is case in-sensitive.

{% tabs %}
	
{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" WidthRequest="180" x:Name="autoComplete" SuggestionMode="EndsWith"/>                            
</StackLayout>

{% endhighlight %}

{% highlight c# %}
	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
autoComplete.DataSource = countryNames;
autoComplete.SuggestionMode= SuggestionMode.EndsWith;
 
{% endhighlight %}

{% endtabs %}

![](images/AutoComplete-Filtering-Options/ends-with.png)


### Filtering Words that Ends with the Input Text - CaseSensitive 

Displays all the matches that ends with the typed characters in control. This strategy is case sensitive.
	
{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" SuggestionMode="EndsWithCaseSensitive"/>                            
</StackLayout>

{% endhighlight %}

{% highlight c# %}
	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
autoComplete.DataSource = countryNames;
autoComplete.SuggestionMode= SuggestionMode.EndsWithCaseSensitive;

{% endhighlight %}

{% endtabs %}

![](images/AutoComplete-Filtering-Options/ends-with-case-sensitive.png)

