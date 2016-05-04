---
layout : post
title : AutoCompleteSource mode in Syncfusion AutoComplete control for Xamarin.Forms
description : Learn how to use AutoCompleteSource in AutoComplete
platform : Xamarin
control : AutoComplete
documentation : ug
---

# AutoCompleteSource 

The `AutoCompleteSource` property is used to populate the list of data to the suggestions dropdown.
	
{% tabs %}	
	
{% highlight c# %}
	
   	List<String> countryList = new List<String>(); 
	countryList.Add ("Iceland");
	countryList.Add ("India");
	countryList.Add ("Indonesia");
	countryList.Add ("Iran");
  	countryAutoComplete.AutoCompleteSource=countryList;
	 
{% endhighlight %}

{% highlight xaml %}

  		<autocomplete:SfAutoComplete  x:Name="countryAutoComplete" HeightRequest="40" AutoCompleteSource="{Binding }" />

{% endhighlight %}

{% endtabs %}
	
![](images/autocompletesource.png)

