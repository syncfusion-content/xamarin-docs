---
layout : post
title : Editable mode for Syncfusion SfComboBox control in Xamarin.Forms
description : Learn how to change the Editable mode in ComboBox
platform : Xamarin
control : SfComboBox
documentation : ug
---

# IsEditable Modes

SfComboBox supports both editable and non-editable text box to choose selected items in given data source. Users can select one item from the suggestion list. 

`IsEditableMode` property is used to enable the user input in SfComboBox control. The default value is false.

## Editable Mode

In editable mode, the combo box allows users to edit in the text box that shows the suggestion in drop-down list based on the input.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="true"/>                      
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
	 
{% endhighlight %}

{% endtabs %}

![](images/ComboBox-Editing/iseditable.png)

## Non-Editable Mode

Non-editable mode is used to prevent users from typing and select from drop-down list.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
	<combobox:SfComboBox HeightRequest="40" x:Name="comboBox" IsEditableMode="false"/>                      
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
comboBox.IsEditableMode = false;
	 
{% endhighlight %}

{% endtabs %}

![](images/ComboBox-Editing/noneditable.png)

