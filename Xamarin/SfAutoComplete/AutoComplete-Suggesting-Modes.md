---
layout : post
title : AutoComplete mode for Syncfusion AutoComplete control in Xamarin.Forms
description : Learn how to change the AutoComplete mode in AutoComplete
platform : Xamarin
control : AutoComplete
documentation : ug
---

# AutoComplete Suggesting Modes

AutoComplete provides three different ways to display the filtered suggestions. They are 

* Suggest - displaying suggestion in drop down list

* Append - appending the first suggestion to text

* SuggestAppend - Both of these

AutoCompleteMode property is used to choose the suggestion display mode in SfAutoComplete control. The default value is Suggest.

## Suggesting Choices in List

The filtered suggestions are displayed in a drop down list. User can pick an item from the list.

{% tabs %}

{% highlight xaml %}

	<StackLayout VerticalOptions="StartAndExpand" HorizontalOptions="StartAndExpand" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" AutoCompleteMode="Suggest"/>                      
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
	autoComplete.AutoCompleteMode = AutoCompleteMode.Suggest;
	 
{% endhighlight %}

{% endtabs %}

![](images/suggest.png)

## Appending Suggestion to Text

The first item in filtered suggestions is appended to SfAutoComplete text. In this mode, drop down remains closed.

{% tabs %}

{% highlight xaml %}

	<StackLayout VerticalOptions="StartAndExpand" HorizontalOptions="StartAndExpand" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" AutoCompleteMode="Append"/>                       
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
	autoComplete.AutoCompleteMode = AutoCompleteMode.Append;
	 
{% endhighlight %}

{% endtabs %}

![](images/append.png)

## Suggesting Choices and Appending Suggestions to Text

The text is appended with the first matched item in the suggestions collection and filtered suggestions are displayed in a drop down list. User can pick from list directly or use up and down keys for browsing the list.
	
{% tabs %}	

{% highlight xaml %}

	<StackLayout VerticalOptions="StartAndExpand" HorizontalOptions="StartAndExpand" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" AutoCompleteMode="SuggestAppend"/>                
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
	autoComplete.AutoCompleteMode = AutoCompleteMode.SuggestAppend;

{% endhighlight %}

{% endtabs %}

![](images/suggest-append.png)