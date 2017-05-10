---
layout : post
title : Suggestion mode for Syncfusion AutoComplete Control in Xamarin.Forms
description : Learn how to display suggestion mode in AutoComplete 
platform : Xamarin.Forms
control : AutoComplete
documentation : ug
---

# AutoComplete Filtering Options

The phenomenon of string comparison for filtering suggestions can be changed using the SuggestionMode property. The default filtering strategy is “StartsWith” and it is case insensitive. The available filtering modes are

* StartsWith

* StartsWithCaseSensitive

* Contains

* ContainsWithCaseSensitive

* Equals

* EqualsWithCaseSensitive

* EndsWith

* EndsWithCaseSensitive

## Filtering Words that Starts with Input Text

Displays all the matches that starts with the typed characters in control. This strategy is case in-sensitive.
	
{% tabs %}	

{% highlight xaml %}

	<StackLayout VerticalOptions="Center" HorizontalOptions="Center">
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

![](images/starts-with.png)

### Filtering Words that Starts with Input Text - CaseSensitive

Displays all the matches that starts with the typed characters in control. This strategy is case sensitive.

{% tabs %}

{% highlight xaml %}

	<StackLayout VerticalOptions="Center" HorizontalOptions="Center">
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

![](images/starts-with-case-sensitive.png)

## Filtering Words that Contains the Input Text

Displays all the matches that contains the typed characters in control. This strategy is case in-sensitive.
	
{% tabs %}

{% highlight xaml %}

	<StackLayout VerticalOptions="Center" HorizontalOptions="Center">
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
	autoComplete.DataSource = countryNames;
	autoComplete.SuggestionMode= SuggestionMode.Contains;
	 
{% endhighlight %}

{% endtabs %}

### Filtering Words that Contains the Input Text - CaseSensitive

Displays all the matches that contains the typed characters in control. This strategy is case sensitive.

{% tabs %}

{% highlight xaml %}

	<StackLayout VerticalOptions="Center" HorizontalOptions="Center">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" SuggestionMode="ContainsCaseSensitive"/>                            
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
	autoComplete.SuggestionMode= SuggestionMode.ContainsCaseSensitive;

{% endhighlight %}

{% endtabs %}

## Filtering Words that Equals the Input Text

Displays all the words that completely matches with the typed characters in control. This strategy is case in-sensitive.
	
{% tabs %}

{% highlight xaml %}

	<StackLayout VerticalOptions="Center" HorizontalOptions="Center">
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

	<StackLayout VerticalOptions="Center" HorizontalOptions="Center">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" SuggestionMode="EqualsCaseSensitive"/>                            
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
	autoComplete.SuggestionMode= SuggestionMode.EqualsCaseSensitive;

{% endhighlight %}

{% endtabs %}

## Filtering Words that Ends with the Input Text

Displays all the matches that ends with the typed characters in control. This strategy is case in-sensitive.

{% tabs %}
	
{% highlight xaml %}

	<StackLayout VerticalOptions="Center" HorizontalOptions="Center">
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

![](images/ends-with.png)

### Filtering Words that Ends with the Input Text - CaseSensitive 

Displays all the matches that ends with the typed characters in control. This strategy is case sensitive.
	
{% tabs %}

{% highlight xaml %}

	<StackLayout VerticalOptions="Center" HorizontalOptions="Center">
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

![](images/ends-with-case-sensitive.png)