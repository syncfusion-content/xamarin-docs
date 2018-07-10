---
layout: post
title: Suggestion DropDown in Syncfusion SfComboBox control for Xamarin.Forms
description: Learn how to deal with the properties of Suggestion DropDown
platform: xamarin
control: SfComboBox
documentation: ug
---

# Dealing with Suggestion Box

Suggestion box is the drop down list box which displays the filtered suggestions inside a popup. This section explains the properties that deals with drop down list in SfComboBox control.

## Suggestion Box Placement mode

Suggestion Box can be placed either at top or bottom using the `SuggestionBoxPlacement` property. By default, it is placed at bottom.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Center" HorizontalOptions="Center" Padding="30">
	<combobox:SfComboBox HeightRequest="40" SuggestionBoxPlacement="Top" x:Name="comboBox" />
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
comboBox.SuggestionBoxPlacement = SuggestionBoxPlacement.Top;

{% endhighlight %}

{% endtabs %}

![](images/Dealing-with-Suggestion-Box/suggestion-box-placement-top.png)

## Maximum Suggestion Box Height

The maximum height of the suggestion box in the SfComboBox control can be varied using `MaximumDropDownHeight` property.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" MaximumDropDownHeight="100" />                     
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
comboBox.DataSource = countryNames;
comboBox.MaximumDropDownHeight = 100;

{% endhighlight %}

{% endtabs %}

![](images/Dealing-with-Suggestion-Box/maximum-dropdown-height.png)

## Opening Suggestion Box on Focus

Suggestion Box can be shown whenever control receives focus using `ShowSuggestionsOnFocus` property. At this time, suggestion list is the complete list of data source.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" ShowSuggestionsOnFocus="true" />                        
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

List<String> countryNames = new List<String>();
countryNames.Add("Great Britain");
countryNames.Add("Canada");
countryNames.Add("France");
countryNames.Add("China");
countryNames.Add("Japan");
comboBox.DataSource = countryNames;
comboBox.ShowSuggestionsOnFocus = true;

{% endhighlight %}

{% endtabs %}

![](images/Dealing-with-Suggestion-Box/show-suggestions-on-focus.png)

## Delay Opening Suggestion Box

`PopupDelay` property is used to delay the suggestion box opening process. It gets milliseconds as input in integer data type.
Here in this example, a time duration of 3 seconds is set as popup delay.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="StartAndExpand" HorizontalOptions="StartAndExpand" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" PopupDelay="3000" />                            
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
comboBox.PopupDelay = 3000;

{% endhighlight %}

{% endtabs %}

## Avoid Opening Suggestion Box

APIs are available to avoid pop-ups and retrieve filtered suggestion items that help you arrange lists or items control. 

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="StartAndExpand" HorizontalOptions="StartAndExpand" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" SuggestionBoxPlacement="None" />                            
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");
comboBox.SuggestionBoxPlacement = SuggestionBoxPlacement.None;
comboBox.DataSource = countryNames;


{% endhighlight %}

{% endtabs %}
