---
layout: post
title: Syncfusion supported input views
description: How to add supported input views in text input layout.
platform: xamarin
control: SfTextInputLayout
documentation: ug
---

# Supported input views

Input views can be added to the text input layout control by setting the [InputView](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~InputView.html) property. To reduce the XAML syntax, [InputView](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout~InputView.html) property is applied with [ContentPropertyAttribute](https://docs.microsoft.com/en-us/dotnet/api/xamarin.forms.contentpropertyattribute?view=xamarin-forms).

## Entry

To enter a single line text input, add [Entry](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/text/entry).

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
   Hint="Name"
   HelperText="Enter your name">
   <Entry />
</inputLayout:SfTextInputLayout>  

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Name"; 
inputLayout.HelperText = "Enter your name"
inputLayout.InputView = new Entry(); 

{% endhighlight %}

{% endtabs %}

![Entry](Supported-input-views-images/textInput_input_img1.PNG)

## Editor


To enter multi-line text input, add [Editor](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/text/editor), and then set the `AutoSize` property to `TextChanges`.


{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
   Hint="Notes">
   <Editor AutoSize="TextChanges" />
</inputLayout:SfTextInputLayout>  

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Notes"; 
inputLayout.InputView = new Editor(); 

{% endhighlight %}

{% endtabs %}

![Editor](Supported-input-views-images/textInput_input_img2.PNG)

## Masked edit

To initialize the masked edit control and launch it in each platform, refer to the [getting started with masked edit](https://help.syncfusion.com/xamarin/sfmaskededit/getting-started) documentation.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
   Hint="Card number"
   HelperText="Required *">
   <maskededit:SfMaskedEdit
        Keyboard="Numeric"
        Mask="0000 0000 0000 0000" />
</inputLayout:SfTextInputLayout>  

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Card number"; 
inputLayout.HelperText = "Required *"
inputLayout.InputView = new SfMaskedEdit() { Keyboard = Keyboard.Numeric, Mask = "0000 0000 0000 0000" }; 

{% endhighlight %}

{% endtabs %}

![Masked edit](Supported-input-views-images/textInput_input_img3.PNG)

## Numeric text box

To initialize the numeric text box control and launch it in each platform, refer to the [getting started with numeric text box](https://help.syncfusion.com/xamarin/sfnumerictextbox/getting-started) documentation.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
   Hint="Amount"
   HelperText="Required *">
   <numericBox:SfNumericTextBox 
      Value="123.45"
      FormatString="c" />
</inputLayout:SfTextInputLayout>  

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Amount"; 
inputLayout.HelperText = "Required *"
inputLayout.InputView = new SfNumericTextBox() { Value = 123.45, FormatString="c" }; 

{% endhighlight %}

{% endtabs %}


![Numerictextbox](Supported-input-views-images/textInput_input_img4.PNG)

## Autocomplete

To initialize the Autocomplete control and launch it in each platform, refer to the [getting started with auto complete](https://help.syncfusion.com/xamarin/sfautocomplete/getting-started) documentation.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout Hint="Country">
   <autocomplete:SfAutoComplete  AutoCompleteMode="SuggestAppend">
      <autocomplete:SfAutoComplete.AutoCompleteSource>
         <ListCollection:List x:TypeArguments="x:String">
         	<x:String> United Kingdom </x:String>
            <x:String> United States </x:String>
            <x:String> United Republic of Tanzania </x:String>
         </ListCollection:List>
      </autocomplete:SfAutoComplete.AutoCompleteSource>
   </autocomplete:SfAutoComplete>
</inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

var autoComplete = new SfAutoComplete();
var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Country"; 
List<String> countryNames = new List<String>();
countryNames.Add("United Kingdom");
countryNames.Add("United States");
countryNames.Add("United Republic of Tanzania");
autoComplete.AutoCompleteMode = AutoCompleteMode.SuggestAppend;
autoComplete.DataSource = countryNames;
inputLayout.InputView = autoComplete; 

{% endhighlight %}

{% endtabs %}

![Autocomplete](Supported-input-views-images/textInput_input_img5.PNG)

## Combo box

To initialize the ComboBox control and launch it in each platform, refer to the [getting started with combo box](https://help.syncfusion.com/xamarin/sfcombobox/getting-started) documentation.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout Hint="Country">
   <combobox:SfComboBox>
      <combobox:SfComboBox.ComboBoxSource>
         <ListCollection:List x:TypeArguments="x:String">
         	<x:String> Afghanistan </x:String>
            <x:String> Akrotiri </x:String>
            <x:String> Albania </x:String>
         </ListCollection:List>
      </combobox:SfComboBox.ComboBoxSource>
   </combobox:SfComboBox>
</inputLayout:SfTextInputLayout> 

{% endhighlight %}

{% highlight C# %} 

var combobox = new SfComboBox();
var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Country"; 
List<String> countryNames = new List<String>();
countryNames.Add("Afghanistan");
countryNames.Add("Akrotiri");
countryNames.Add("Albania");
combobox.DataSource = countryNames;
inputLayout.InputView = combobox; 

{% endhighlight %}

{% endtabs %}

![Combobox](Supported-input-views-images/textInput_input_img6.PNG)

N> Entry and Editor are the only input views supported by [`SfTextInputLayout`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Core.XForms~Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html) in WPF platform.