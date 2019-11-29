---
layout: post
title: MatchHighlighting in Syncfusion SfComboBox control for Xamarin.Forms
description: Learn how to highlight the matched text in SfComboBox
platform: xamarin
control: SfComboBox
documentation: ug
---
# Highlighting matched text

You can highlight matching characters in a suggestion list to pick an item with more clarity by following two ways:

* First Occurrence

* Multiple Occurrence

Highlighting can be indicated with various customizing styles by enabling the following properties.

* HighlightedTextColor -  Sets the color of the highlighted text for differentiating the highlighted characters.

* HighlightTextFontAttributes - Sets the FontAttributes of the highlighted text.

## First occurrence

Highlights the first position of the matching characters in the suggestion list.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
    <combobox:SfComboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="true" AllowFiltering="true" TextHighlightMode="FirstOccurrence" HighlightedTextColor="Red" HighlightedTextFontAttributes="Bold" SuggestionMode="StartsWith">
        <combobox:SfComboBox.DataSource>
            <ListCollection:List x:TypeArguments="x:String">
                <x:String> Albania </x:String>
                <x:String> Algeria </x:String>
                <x:String> American Samoa </x:String>
                <x:String> Andorra </x:String>
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
countryNames.Add("Albania");
countryNames.Add("Algeria");
countryNames.Add("American Samoa");
countryNames.Add("Andorra");

SfComboBox comboBox = new SfComboBox();
comboBox.HeightRequest = 40;
comboBox.DataSource = countryNames;
comboBox.IsEditableMode = true;
comboBox.AllowFiltering = true;
comboBox.SuggestionMode = SuggestionMode.StartsWith;
comboBox.TextHighlightMode = OccurrenceMode.FirstOccurrence;
comboBox.HighlightedTextColor = Color.Red;
comboBox.HighlightedTextFontAttributes = FontAttributes.Bold;

layout.Children.Add(comboBox); 
Content = layout;

{% endhighlight %}

{% endtabs %}

![First occurrance image](images/Highlighting-matched-text/FirstOccurrance.png)

## Multiple occurrence

Highlights the matching characters that present everywhere in the suggestion list for Contains case in SuggestionMode.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
    <combobox:SfComboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="true" AllowFiltering="true" TextHighlightMode="MultipleOccurrence" HighlightedTextColor="Red" HighlightedTextFontAttributes="Bold" SuggestionMode="Contains">
        <combobox:SfComboBox.DataSource>
            <ListCollection:List x:TypeArguments="x:String">
                <x:String> Albania </x:String>
                <x:String> Algeria </x:String>
                <x:String> American Samoa </x:String>
                <x:String> Andorra </x:String>
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
countryNames.Add("Albania");
countryNames.Add("Algeria");
countryNames.Add("American Samoa");
countryNames.Add("Andorra");

SfComboBox comboBox = new SfComboBox();
comboBox.HeightRequest = 40;
comboBox.DataSource = countryNames;
comboBox.IsEditableMode = true;
comboBox.AllowFiltering = true;
comboBox.SuggestionMode = SuggestionMode.Contains;
comboBox.TextHighlightMode = OccurrenceMode.MultipleOccurrence;
comboBox.HighlightedTextColor = Color.Red;
comboBox.HighlightedTextFontAttributes = FontAttributes.Bold;

layout.Children.Add(comboBox); 
Content = layout;

{% endhighlight %}

{% endtabs %}
![Multiple occurrance image](images/Highlighting-matched-text/MultipleOccurrance.png)
