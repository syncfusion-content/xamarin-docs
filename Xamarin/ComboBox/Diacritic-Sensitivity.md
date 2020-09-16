---
layout: post
title: Diacritic sensitivity in Syncfusion ComboBox control
description: Learn how to enable and disable Diacritic sensitivity in SfComboBox
platform: xamarin
control: SfComboBox
documentation: ug
---
# Diacritic Sensitivity

The control does not stick with one type of keyboard, so you can populate items from a language with letters containing diacritics, and search for them with English characters from an en-US keyboard. Users can enable or disable the diacritic sensitivity with the [`IgnoreDiacritic`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.ComboBox.SfComboBox.html#Syncfusion_XForms_ComboBox_SfComboBox_IgnoreDiacritic) property. In the below code example we have illustrate how to enables the diacritic sensitivity so that items in the suggestion list get populated by entering any diacritic character of that alphabet.

N> Diacritic Sensitivity support has enhanced only on iOS and Android platform.

{% tabs %}

{% highlight xaml %}

<StackLayout VerticalOptions="Start" HorizontalOptions="Start" Padding="30">
    <combobox:SfComboBox  HeightRequest="40" x:Name="comboBox" IsEditableMode="True" AllowFiltering="True" TextHighlightMode="MultipleOccurrence" SuggestionMode="Contains" HighlightedTextColor="Red" IgnoreDiacritic="false">
        <combobox:SfComboBox.ComboBoxSource>
            <ListCollection:List x:TypeArguments="x:String">
                <x:String>Hów tó gâin wéight?</x:String>
                <x:String>Hów tó drâw ân éléphânt?</x:String>
                <x:String>Whéré cân I buy â câmérâ?</x:String>
                <x:String>Guidé mé âll thé wây</x:String>
                <x:String>Hów tó mâké â câké?</x:String>
                <x:String>Sây, Hélló Wórld!</x:String>
                <x:String>Hów tó mâké â róbót?</x:String>
                <x:String>Whât timé nów in Indiâ?</x:String>
            </ListCollection:List>
        </combobox:SfComboBox.ComboBoxSource>
    </combobox:SfComboBox>
</StackLayout>            

{% endhighlight %}

{% highlight c# %}

StackLayout mainLayout = new StackLayout()
{
    Padding = new Thickness(30)
};

SfComboBox comboBox = new SfComboBox();
comboBox.HeightRequest = 40;
comboBox.IsEditableMode = true;
comboBox.AllowFiltering = true;
comboBox.TextHighlightMode = OccurrenceMode.MultipleOccurrence;
comboBox.SuggestionMode = SuggestionMode.Contains;
comboBox.HighlightedTextColor = Color.Red;
comboBox.IgnoreDiacritic = false;

List<String> diacritic = new List<String>();
diacritic.Add("Hów tó gâin wéight?");
diacritic.Add("Hów tó drâw ân éléphânt?");
diacritic.Add("Whéré cân I buy â câmérâ?");
diacritic.Add("Guidé mé âll thé wây");
diacritic.Add("Hów tó mâké â câké?");
diacritic.Add("Sây, Hélló Wórld!");
diacritic.Add("Hów tó mâké â róbót?");
diacritic.Add("Whât timé nów in Indiâ?");
comboBox.ComboBoxSource = diacritic;
mainLayout.Children.Add(comboBox);
Content = mainLayout;

{% endhighlight %}

{% endtabs %}

![Diacritic](images/Diacritic-Sensitivity/Diacritic.png)

