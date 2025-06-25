---
layout: post
title: Supported Input Views in Xamarin Text Input Layout | Syncfusion
description: Learn about Supported Input Views in Syncfusion Xamarin Text Input Layout (SfTextInputLayout) control.
platform: xamarin
control: SfTextInputLayout
documentation: ug
---

# Supported Input Views in Xamarin Text Input Layout (SfTextInputLayout)

Input views can be integrated into the text input layout control by setting the [InputView](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html#Syncfusion_XForms_TextInputLayout_SfTextInputLayout_InputView) property. To reduce the XAML syntax complexity, the `InputView` property is designated with the [ContentPropertyAttribute](https://learn.microsoft.com/en-us/dotnet/api/xamarin.forms.contentpropertyattribute?view=xamarin-forms).

## Entry

To allow single-line text input, utilize the [Entry](https://learn.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/text/entry) control.

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

For multi-line text input, use the [Editor](https://learn.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/text/editor) control and set the `AutoSize` property to `TextChanges`.

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

## Masked Edit

To initialize the masked edit control and deploy it on each platform, refer to the [Masked Edit documentation](https://help.syncfusion.com/xamarin/sfmaskededit/getting-started).

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

## Numeric Text Box

For integrating the numeric text box control, refer to the [Numeric Text Box documentation](https://help.syncfusion.com/xamarin/sfnumerictextbox/getting-started).

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

![Numeric TextBox](Supported-input-views-images/textInput_input_img4.PNG)

## Numeric Up Down

For deploying the numeric up-down control on each platform, refer to the [Numeric Up Down documentation](https://help.syncfusion.com/xamarin/sfnumericupdown/getting-started).

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout
   Hint="Amount"
   HelperText="Maximum limit is $10,000.">
   <numeric:SfNumericUpDown 
   x:Name="numericUpDown" 
   Value="5"/>
</inputLayout:SfTextInputLayout>  

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Amount"; 
inputLayout.HelperText = "Maximum limit is $10,000."
inputLayout.InputView = new SfNumericUpDown() { Value = 5}; 

{% endhighlight %}

{% endtabs %}

## Autocomplete

To use the autocomplete control across platforms, refer to the [Autocomplete documentation](https://help.syncfusion.com/xamarin/sfautocomplete/getting-started).

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout Hint="Country" ContainerType="Outlined">
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
inputLayout.ContainerType = ContainerType.Outlined;
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

## Combo Box

For initializing the ComboBox control on different platforms, refer to the [Combo Box documentation](https://help.syncfusion.com/xamarin/sfcombobox/getting-started).

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout Hint="Country" ContainerType="Outlined">
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
inputLayout.ContainerType = ContainerType.Outlined;
List<String> countryNames = new List<String>();
countryNames.Add("Afghanistan");
countryNames.Add("Akrotiri");
countryNames.Add("Albania");
combobox.DataSource = countryNames;
inputLayout.InputView = combobox; 

{% endhighlight %}

{% endtabs %}

![Combobox](Supported-input-views-images/textInput_input_img6.PNG)

> **Note:** Entry and Editor are the only input views supported by [`SfTextInputLayout`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.TextInputLayout.SfTextInputLayout.html) on the WPF platform.

## Picker

To select an item from a list, use the [Picker](https://learn.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/picker) control.

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout Hint="Picker"
                               HelperText="Select a color">
<Picker>
  <Picker.ItemsSource>
     <x:Array Type="{x:Type x:String}">
     <x:String>Red</x:String>
     <x:String>Blue</x:String>
     <x:String>Green</x:String>
     <x:String>Purple</x:String>
     <x:String>Yellow</x:String>
     </x:Array>
   </Picker.ItemsSource>
</Picker>
</inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
inputLayout.Hint = "Picker"; 
inputLayout.HelperText = "Select a color";
var picker = new Picker();
List<string> colors = new List<string>();
colors.Add("Red");
colors.Add("Blue");
colors.Add("Green");
colors.Add("Purple");
colors.Add("Yellow");
picker.ItemsSource = colors;
inputLayout.InputView = picker; 

{% endhighlight %}

{% endtabs %}

> **Note:** UWP and WPF platforms do not support [`Xamarin.Forms Picker`](https://learn.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/picker) as an input view in the text input layout.

## Date Picker

To select a date, use the [DatePicker](https://learn.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/datepicker).

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout ContainerType="None"
                               Hint="Date" 
                               HelperText="Select a date">
<DatePicker MinimumDate="01/01/2019"
            MaximumDate="12/31/2019" 
            Date="11/12/2019"/>
</inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
var datePicker = new DatePicker();
inputLayout.Hint = "Date";
inputLayout.HelperText = "Select a date from a calender";
datePicker.MinimumDate = new DateTime(2019, 1, 1);
datePicker.MaximumDate = new DateTime(2019, 12, 31);
datePicker.Date = new DateTime(2019, 11, 12);
inputLayout.InputView = datePicker;
         

{% endhighlight %}

{% endtabs %}

> **Note:** UWP and WPF platforms do not support [`Xamarin.Forms DatePicker`](https://learn.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/datepicker) as an input view in the text input layout.

## Time Picker

To select a time, use the [TimePicker](https://learn.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/timepicker).

{% tabs %} 

{% highlight xaml %} 

<inputLayout:SfTextInputLayout Hint="Time"
                               HelperText="Select a time">
<TimePicker Time="12:00:00"/>
</inputLayout:SfTextInputLayout>

{% endhighlight %}

{% highlight C# %} 

var inputLayout = new SfTextInputLayout();
var timePicker = new TimePicker();
inputLayout.Hint = "Time";
inputLayout.HelperText = "Select a time";
timePicker.Time = new TimeSpan(12, 00, 00) 
inputLayout.InputView = timePicker;
         

{% endhighlight %}

{% endtabs %}

> **Note:** UWP and WPF platforms do not support [`Xamarin.Forms TimePicker`](https://learn.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/timepicker) as an input view in the text input layout.
