---
layout: post
title: Suggestion DropDown in Syncfusion SfAutoComplete control for Xamarin.Forms
description: Learn how to deal with the properties of Suggestion DropDown
platform: xamarin
control: SfAutoComplete
documentation: ug
---

# Dealing with Suggestion Box

Suggestion box is the drop-down list box, which displays the filtered suggestions inside a popup. This section explains the properties that deals with drop-down list in the SfAutoComplete control.

## Suggestion box placement mode

Suggestion box can be placed either at the top or bottom using the `SuggestionBoxPlacement` property. By default, it is placed at the bottom.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Center" HorizontalOptions="Center" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" SuggestionBoxPlacement="Top" x:Name="autoComplete" />
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
autoComplete.SuggestionBoxPlacement = SuggestionBoxPlacement.Top;

{% endhighlight %}

{% endtabs %}

![](images/Dealing-with-Suggestion-Box/suggestion-box-placement-top.png)

## Maximum suggestion box height

The maximum height of the suggestion box in the SfAutocomplete control can be varied using the `MaximumDropDownHeight` property.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" MaximumDropDownHeight="100" />                     
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

List<String> countryNames = new List<String>();
countryNames.Add("Great Britain");
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("Canada");
countryNames.Add("United Arab Emirates");
countryNames.Add("France");
countryNames.Add("United Kingdom");
countryNames.Add("China");
countryNames.Add("United States");
countryNames.Add("Japan");
autoComplete.DataSource = countryNames;
autoComplete.MaximumDropDownHeight = 100;

{% endhighlight %}

{% endtabs %}

![](images/Dealing-with-Suggestion-Box/maximum-dropdown-height.png)

## Opening suggestion box on focus

Suggestion box can be shown whenever the control receives focus using the `ShowSuggestionsOnFocus` property. At this time, suggestion list is the complete list of data source.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" ShowSuggestionsOnFocus="true" />                        
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

List<String> countryNames = new List<String>();
countryNames.Add("Great Britain");
countryNames.Add("Canada");
countryNames.Add("France");
countryNames.Add("China");
countryNames.Add("Japan");
autoComplete.DataSource = countryNames;
autoComplete.ShowSuggestionsOnFocus = true;

{% endhighlight %}

{% endtabs %}

![](images/Dealing-with-Suggestion-Box/show-suggestions-on-focus.png)

## Delay opening suggestion box

The `PopupDelay` property is used to delay the suggestion box opening process. It gets milliseconds as input in integer data type.
In this example, a time duration of 3 seconds is set to popup delay.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="StartAndExpand" HorizontalOptions="StartAndExpand" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" PopupDelay="3000" />                            
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
autoComplete.PopupDelay = 3000;

{% endhighlight %}

{% endtabs %}

## Delay before searching algorithm starts

The `SearchDelay` property is used to delay the searching algorithm process. It gets milliseconds as input in integer data type.

In this example, a time duration of 3 seconds is set to search delay.

{% tabs %}

{% highlight xaml %}

    <StackLayout VerticalOptions="StartAndExpand" HorizontalOptions="StartAndExpand" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" SearchDelay="3000" />                            
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
    autoComplete.SearchDelay = 3000;

{% endhighlight %}

{% endtabs %}

## Avoid opening suggestion box

APIs are available to avoid pop-ups and retrieve filtered suggestion items that help you arrange lists or items control. 

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="StartAndExpand" HorizontalOptions="StartAndExpand" Padding="30">
	<autocomplete:SfAutoComplete HeightRequest="40" x:Name="autoComplete" SuggestionBoxPlacement="None" />                            
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
autoComplete.SuggestionBoxPlacement=SuggestionBoxPlacement.None;
autoComplete.DataSource = countryNames;


{% endhighlight %}

{% endtabs %}
