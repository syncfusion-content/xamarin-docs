---
layout: post
title: Suggestion DropDown in Syncfusion SfComboBox control for Xamarin.Forms
description: Learn how to deal with the properties of Suggestion DropDown
platform: xamarin
control: SfComboBox
documentation: ug
---

# Dealing with suggestion box

Suggestion box is a drop-down list box which displays the filtered suggestions inside a popup. This section explains the properties that deals with the drop-down list in SfComboBox control.

## Suggestion box placement mode

Suggestion Box can be placed either at the top or bottom using the `SuggestionBoxPlacement` property. By default, it is placed at the bottom.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Center" HorizontalOptions="Center" Padding="30">
	<combobox:SfComboBox HeightRequest="40" SuggestionBoxPlacement="Top" x:Name="comboBox">
		<combobox:SfComboBox.DataSource>
			<ListCollection:List x:TypeArguments="x:String">
                <x:String> Uganda </x:String>
                <x:String> Ukraine </x:String>
                <x:String> United Arab Emirates </x:String>
                <x:String> United Kingdom </x:String>
                <x:String> United States </x:String>
            </ListCollection:List>
        </combobox:SfComboBox.DataSource>
	 </combobox:SfComboBox>                   
</StackLayout>

{% endhighlight %}

{% highlight c# %}

StackLayout layout = new StackLayout() 
{ 
	VerticalOptions = LayoutOptions.Start, 
	HorizontalOptions = LayoutOptions.Start, 
	Padding = new Thickness(30) 
};	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");

SfComboBox comboBox = new SfComboBox();
comboBox.HeightRequest = 40;
comboBox.DataSource = countryNames;
comboBox.SuggestionBoxPlacement = SuggestionBoxPlacement.Top;

layout.Children.Add(comboBox); 
Content = layout;

{% endhighlight %}

{% endtabs %}

![](images/Dealing-with-Suggestion-Box/suggestion-box-placement-top.png)

## Maximum suggestion box height

The maximum height of the suggestion box in the SfComboBox control can be varied using the `MaximumDropDownHeight` property.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" MaximumDropDownHeight="100">
		<combobox:SfComboBox.DataSource>
			<ListCollection:List x:TypeArguments="x:String">
                <x:String> Great Britain </x:String>
                <x:String> Uganda </x:String>
                <x:String> Ukraine </x:String>
                <x:String> Canada </x:String>
                <x:String> United Arab Emirates </x:String>
				<x:String> France </x:String>
                <x:String> United Kingdom </x:String>
                <x:String> China </x:String>
                <x:String> United States </x:String>
				<x:String> Japan </x:String>
            </ListCollection:List>
        </combobox:SfComboBox.DataSource>
	 </combobox:SfComboBox>                           
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

StackLayout layout = new StackLayout() 
{ 
	VerticalOptions = LayoutOptions.Start, 
	HorizontalOptions = LayoutOptions.Start, 
	Padding = new Thickness(30) 
};

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

SfComboBox comboBox = new SfComboBox();
comboBox.HeightRequest = 40;
comboBox.DataSource = countryNames;
comboBox.MaximumDropDownHeight = 100;

layout.Children.Add(comboBox); 
Content = layout;

{% endhighlight %}

{% endtabs %}

![](images/Dealing-with-Suggestion-Box/maximum-dropdown-height.png)

## Opening suggestion box on focus

Suggestion Box can be shown whenever control receives focus using the `ShowSuggestionsOnFocus` property. Suggestion list is the complete list of data source.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" ShowSuggestionsOnFocus="true">
		<combobox:SfComboBox.DataSource>
			<ListCollection:List x:TypeArguments="x:String">
                <x:String> Great Britain </x:String>
                <x:String> Canada </x:String>
                <x:String> France </x:String>
                <x:String> China </x:String>
                <x:String> Japan </x:String>
            </ListCollection:List>
        </combobox:SfComboBox.DataSource>
	 </combobox:SfComboBox>                                       
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

StackLayout layout = new StackLayout() 
{ 
	VerticalOptions = LayoutOptions.Start, 
	HorizontalOptions = LayoutOptions.Start, 
	Padding = new Thickness(30) 
};	
List<String> countryNames = new List<String>();
countryNames.Add("Great Britain");
countryNames.Add("Canada");
countryNames.Add("France");
countryNames.Add("China");
countryNames.Add("Japan");

SfComboBox comboBox = new SfComboBox();
comboBox.HeightRequest = 40;
comboBox.DataSource = countryNames;
comboBox.ShowSuggestionsOnFocus = true;
comboBox.IsEditableMode = true;
comboBox.SelectionChanged += (sender, e) => 
{
	DisplayAlert("Selection Changed", "Selected Value: " + comboBox.SelectedValue.ToString(), "OK"); 
};

layout.Children.Add(comboBox); 
Content = layout;

{% endhighlight %}

{% endtabs %}

![](images/Dealing-with-Suggestion-Box/show-suggestions-on-focus.png)

## Delay opening suggestion box

The `PopupDelay` property is used to delay the suggestion box opening process. It gets milliseconds as input in integer data type.
Here in this example, a time duration of 3 seconds is set as popup delay.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="StartAndExpand" HorizontalOptions="StartAndExpand" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" PopupDelay="3000">
		<combobox:SfComboBox.DataSource>
			<ListCollection:List x:TypeArguments="x:String">
                <x:String> Uganda </x:String>
                <x:String> Ukraine </x:String>
                <x:String> United Arab Emirates </x:String>
                <x:String> United Kingdom </x:String>
                <x:String> United States </x:String>
            </ListCollection:List>
        </combobox:SfComboBox.DataSource>
	 </combobox:SfComboBox>                                            
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

StackLayout layout = new StackLayout() 
{ 
	VerticalOptions = LayoutOptions.Start, 
	HorizontalOptions = LayoutOptions.Start, 
	Padding = new Thickness(30) 
};	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");

SfComboBox comboBox = new SfComboBox();
comboBox.HeightRequest = 40;
comboBox.DataSource = countryNames;
comboBox.PopupDelay = 3000;

layout.Children.Add(comboBox); 
Content = layout;

{% endhighlight %}

{% endtabs %}

## Avoid opening suggestion box

APIs are available to avoid pop-ups and retrieve filtered suggestion items that help you arrange lists or items control. 

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="StartAndExpand" HorizontalOptions="StartAndExpand" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" SuggestionBoxPlacement="None">
		<combobox:SfComboBox.DataSource>
			<ListCollection:List x:TypeArguments="x:String">
                <x:String> Uganda </x:String>
                <x:String> Ukraine </x:String>
                <x:String> United Arab Emirates </x:String>
                <x:String> United Kingdom </x:String>
                <x:String> United States </x:String>
            </ListCollection:List>
        </combobox:SfComboBox.DataSource>
	 </combobox:SfComboBox>                             
</StackLayout> 

{% endhighlight %}

{% highlight c# %}

StackLayout layout = new StackLayout() 
{ 
	VerticalOptions = LayoutOptions.Start, 
	HorizontalOptions = LayoutOptions.Start, 
	Padding = new Thickness(30) 
};	
List<String> countryNames = new List<String>();
countryNames.Add("Uganda");
countryNames.Add("Ukraine");
countryNames.Add("United Arab Emirates");
countryNames.Add("United Kingdom");
countryNames.Add("United States");

SfComboBox comboBox = new SfComboBox();
comboBox.HeightRequest = 40;
comboBox.SuggestionBoxPlacement = SuggestionBoxPlacement.None;
comboBox.DataSource = countryNames;

layout.Children.Add(comboBox); 
Content = layout;

{% endhighlight %}

{% endtabs %}
