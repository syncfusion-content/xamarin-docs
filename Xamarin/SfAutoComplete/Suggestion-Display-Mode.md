---
layout : post
title : AutoComplete mode for Syncfusion AutoComplete control in Xamarin.Forms
description : Learn how to change the AutoComplete mode in AutoComplete
platform : Xamarin
control : AutoComplete
documentation : ug
---

# Suggestion Display Mode

The `AutocompleteMode` property is used to decide the suggestion pattern for displaying the filtered data according to the text entered. 

N> By default, three types of AutoComplete mode such as `Append`, `Suggest` and `SuggestAppend` are provided.

## Append

Appends the first matching string with the entered character.

{% tabs %}

{% highlight xaml %}

  	<autocomplete:SfAutoComplete x:Name="countryAutoComplete" AutoCompleteMode="Append" />
		  
{% endhighlight %}

{% highlight c# %}
	
	countryAutoComplete.AutoCompleteMode = AutoCompleteMode.Append;
	 
{% endhighlight %}

{% endtabs %}

![](images/autocompletemode.png)

## Suggest in Dropdown

Displays the suggestion in the dropdown.

{% tabs %}

{% highlight xaml %}

  	<autocomplete:SfAutoComplete x:Name="countryAutoComplete" AutoCompleteMode="Suggest" />
		  
{% endhighlight %}

{% highlight c# %}
	
	countryAutoComplete.AutoCompleteMode = AutoCompleteMode.Suggest;
	 
{% endhighlight %}

{% endtabs %}

![](images/autocompletesource.png)

## Both Append and Suggest in DropDown

Displays the suggestion in the dropdown along with appending the first matching string.
	
{% tabs %}	

{% highlight xaml %}

  	<autocomplete:SfAutoComplete x:Name="countryAutoComplete" AutoCompleteMode="SuggestAppend" />
		  
{% endhighlight %}

	
{% highlight c# %}
	
	countryAutoComplete.AutoCompleteMode = AutoCompleteMode.SuggestAppend;
	 
{% endhighlight %}

{% endtabs %}

![](images/suggestappend.png)
 
