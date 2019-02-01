---
layout: post
title: Keys for Syncfusion Controls
description: This section contains the details about the keys which are mapped to the UI elements of all the controls
platform: xamarin
control: General
documentation: ug
---

# Keys of Syncfusion Controls

This page lists the keys for each control and the element to which it is mapped for all the controls.

## SfTextInputLayout

<table>
    <tr>
        <th>Theme Dictionary<br/>
            <br/></th>        
        <th>
          Keys
            <br/>
            <br/>
        </th>
        <th>
            Description
            <br/>
            <br/>
        </th>
    </tr>

    <tr>
        <td rowspan="24">
            SfTextInputLayoutStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfTextInputLayoutTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, it is possible to customize the appearance of the SfTextInputLayout without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfTextInputLayoutTheme">CustomTheme</x:String> 
                <Color x:Key="SfTextInputLayoutCounterLabelColor">Blue</Color> 
                <Color x:Key="SfTextInputLayoutCounterLabelDisabledColor">Green</Color> 
            </ResourceDictionary>
        </syncCore:SyncfusionThemeDictionary.MergedDictionaries>
    </syncCore:SyncfusionThemeDictionary>
</Application.Resources>

....

</Application>

{% endhighlight %}
            <br/>
            <br/>
        </td>
	</tr>
	<tr>
        <td rowspan="2">
            SyncPrimaryColor  
            <br/>
            <br/>
        </td>
        <td>
            Color of hint when text input layout is focused.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Color of line/border when text input layout is focused.
            <br/>
            <br/>
        </td>
    </tr>


    <tr>
        <td rowspan="3">
            SyncErrorColor   
            <br/>
            <br/>
        </td>
        <td>
            Color of hint when the input view contains error and is focused.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Color of border when input view contains error.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Color of counter label when input view contains error.
            <br/>
            <br/>
        </td>
    </tr>

    
    <tr>
        <td>
            SfTextInputLayoutHintColor
            <br/>
            <br/>
        </td>
        <td>
            Color of hint when the text input layout is in the default state.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
    <td>
            SfTextInputLayoutDisabledHintColor 
            <br/>
            <br/>
        </td>
        <td>
            Color of hint when text input layout is disabled.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfTextInputLayoutFloatedHintDisabledColor  
            <br/>
            <br/>
        </td>
        <td>
            Color of hint when text input layout is disabled, and text inside the input view is floated.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfTextInputLayoutLineColor   
            <br/>
            <br/>
        </td>
        <td>
            Color of line/border when text input layout is in the default state.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfTextInputLayoutFilledLineDisabledColor    
            <br/>
            <br/>
        </td>
        <td>
            Color of line when text input layout is in the disabled state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfTextInputLayoutOutlinedLineDisabledColor     
            <br/>
            <br/>
        </td>
        <td>
            Color of border when text input layout is in the disabled state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfTextInputLayoutCounterLabelColor      
            <br/>
            <br/>
        </td>
        <td>
            Color of counter label when text input layout is in the default state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfTextInputLayoutCounterLabelDisabledColor       
            <br/>
            <br/>
        </td>
        <td>
            Color of counter label when text input layout is in the disabled state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfTextInputLayoutContainerBackgroundColor           
            <br/>
            <br/>
        </td>
        <td>
            Color of container background when the text input layout is in the default state.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfTextInputLayoutContainerBackgroundDisabledColor       
            <br/>
            <br/>
        </td>
        <td>
            Color of container background when text input layout is in the disabled state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfTextInputLayoutHelperTextColor       
            <br/>
            <br/>
        </td>
        <td>
            Color of helper text when text input layout is in the default state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfTextInputLayoutHelperTextDisabledColor       
            <br/>
            <br/>
        </td>
        <td>
            Color of helper text when text input layout is in the disabled state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfTextInputLayoutErrorTextColor       
            <br/>
            <br/>
        </td>
        <td>
            Color of error text when text input layout is in the default state.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfTextInputLayoutErrorTextDisabledColor        
            <br/>
            <br/>
        </td>
        <td>
            Color of error text when text input layout is in the disabled state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfTextInputLayoutPasswordToggleFocusedColor         
            <br/>
            <br/>
        </td>
        <td>
            Color of password toggle button when the input view is focused.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfTextInputLayoutPasswordToggleDisabledColor          
            <br/>
            <br/>
        </td>
        <td>
            Color of password toggle button when the text input layout is in the disabled state.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfTextInputLayoutPasswordToggleUnfocusedColor          
            <br/>
            <br/>
        </td>
        <td>
            Color of password toggle button when the input view is unfocused.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfTextInputLayoutPasswordToggleErrorColor          
            <br/>
            <br/>
        </td>
        <td>
            Color of password toggle button when the input view contains error.
            <br/>
            <br/>
        </td>
    </tr>      

</table>

## SfLinearProgressBar

<table>
    <tr>
        <th>Theme Dictionary<br/>
            <br/></th>        
        <th>
          Keys
            <br/>
            <br/>
        </th>
        <th>
            Description
            <br/>
            <br/>
        </th>
    </tr>

    <tr>
        <td rowspan="24">
             SfProgressBarStyles 
            <br/>
            <br/>
        </td>
		<td>
           SfProgressBarTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, it is possible to customize the appearance of the SfLinearProgressBar without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfProgressBarTheme">CustomTheme</x:String> 
                <Color x:Key="SyncPrimaryColor">Blue</Color> 
                <Color x:Key="SfProgressBarSecondaryProgressColor">Green</Color> 
            </ResourceDictionary>
        </syncCore:SyncfusionThemeDictionary.MergedDictionaries>
    </syncCore:SyncfusionThemeDictionary>
</Application.Resources>

....

</Application>

{% endhighlight %}
            <br/>
            <br/>
        </td>
	</tr>
	<tr>
        <td>
            SyncPrimaryColor  
            <br/>
            <br/>
        </td>
        <td>
            Indicator color of the linear progress indicator.
            <br/>
            <br/>
        </td>
    </tr>
	
    <tr>
        <td>
            SfProgressBarTrackColor   
            <br/>
            <br/>
        </td>
        <td>
            Track color of the linear progress indicator.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfProgressBarSecondaryProgressColor     
            <br/>
            <br/>
        </td>
        <td>
            Secondary progress color of the linear progress indicator.
            <br/>
            <br/>
        </td>
    </tr>
    
</table>

## SfCircularProgressBar

<table>
    <tr>
        <th>Theme Dictionary<br/>
            <br/></th>        
        <th>
          Keys
            <br/>
            <br/>
        </th>
        <th>
            Description
            <br/>
            <br/>
        </th>
    </tr>

    <tr>
        <td rowspan="24">
             SfProgressBarStyles 
            <br/>
            <br/>
        </td>
		<td>
           SfProgressBarTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, it is possible to customize the appearance of the SfCircularProgressBar without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfProgressBarTheme">CustomTheme</x:String> 
                <Color x:Key="SyncPrimaryColor">Blue</Color> 
                <Color x:Key="SfProgressBarTrackColor">Green</Color> 
            </ResourceDictionary>
        </syncCore:SyncfusionThemeDictionary.MergedDictionaries>
    </syncCore:SyncfusionThemeDictionary>
</Application.Resources>

....

</Application>

{% endhighlight %}
            <br/>
            <br/>
        </td>
	</tr>
	<tr>
        <td>
            SyncPrimaryColor  
            <br/>
            <br/>
        </td>
        <td>
            Indicator color of the circular progress indicator.
            <br/>
            <br/>
        </td>
    </tr>
	
    <tr>
        <td>
            SfProgressBarTrackColor   
            <br/>
            <br/>
        </td>
        <td>
            Track color of the circular progress indicator.
            <br/>
            <br/>
        </td>
    </tr>
    
</table>

## SfNumericTextBox

<table>
    <tr>
        <th>Theme Dictionary<br/>
            <br/></th>        
        <th>
          Keys
            <br/>
            <br/>
        </th>
        <th>
            Description
            <br/>
            <br/>
        </th>
    </tr>

    <tr>
        <td rowspan="24">
             SfNumericTextBoxStyles 
            <br/>
            <br/>
        </td>
		<td>
           SfNumericTextBoxTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, it is possible to customize the appearance of the SfNumericTextBox without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfNumericTextBoxTheme">CustomTheme</x:String> 
                <Color x:Key="SyncPrimaryColor">Blue</Color> 
                <Color x:Key="SfNumericTextBoxTextColor">Green</Color> 
            </ResourceDictionary>
        </syncCore:SyncfusionThemeDictionary.MergedDictionaries>
    </syncCore:SyncfusionThemeDictionary>
</Application.Resources>

....

</Application>

{% endhighlight %}
            <br/>
            <br/>
        </td>
	</tr>
	<tr>
        <td>
            SyncPrimaryColor  
            <br/>
            <br/>
        </td>
        <td>
            Border color of the numeric textbox is in default state.
            <br/>
            <br/>
        </td>
    </tr>
	
    <tr>
        <td>
            SfNumericTextBoxTextColor   
            <br/>
            <br/>
        </td>
        <td>
            Text color of the numeric textbox is in default state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
		<td>
            SfNumericTextBoxBackgroundColor     
            <br/>
            <br/>
        </td>
        <td>
            Background color of the numeric textbox is in the default state.
            <br/>
            <br/>
        </td>
    </tr>
    
</table>


## SfNumericUpDown

<table>
    <tr>
        <th>Theme Dictionary<br/>
            <br/></th>        
        <th>
          Keys
            <br/>
            <br/>
        </th>
        <th>
            Description
            <br/>
            <br/>
        </th>
    </tr>

    <tr>
        <td rowspan="24">
             SfNumericUpDownStyles 
            <br/>
            <br/>
        </td>
		<td>
           SfNumericUpDownTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, it is possible to customize the appearance of the SfNumericUpDown without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfNumericUpDownTheme">CustomTheme</x:String> 
                <Color x:Key="SyncPrimaryColor">Blue</Color> 
                <Color x:Key="SfNumericUpDownTextColor">Green</Color> 
            </ResourceDictionary>
        </syncCore:SyncfusionThemeDictionary.MergedDictionaries>
    </syncCore:SyncfusionThemeDictionary>
</Application.Resources>

....

</Application>

{% endhighlight %}
            <br/>
            <br/>
        </td>
	</tr>
	<tr>
        <td>
            SyncPrimaryColor  
            <br/>
            <br/>
        </td>
        <td>
            Border color of the numericUpDown is in default state.
            <br/>
            <br/>
        </td>
    </tr>
	
    <tr>
        <td>
            SfNumericUpDownTextColor   
            <br/>
            <br/>
        </td>
        <td>
            Text color of the numericUpDown is in default state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
		<td>
            SfNumericUpDownBackgroundColor     
            <br/>
            <br/>
        </td>
        <td>
            Background color of the numericUpDown is in the default state.
            <br/>
            <br/>
        </td>
    </tr>
	
	<tr>
		<td>
            SfNumericUpDownButtonBackgroundColor     
            <br/>
            <br/>
        </td>
        <td>
            Background color of the up down button's is in the default state.
            <br/>
            <br/>
        </td>
    </tr>	
    
	<tr>
		<td>
            SfNumericUpDownButtonForegroundColor     
            <br/>
            <br/>
        </td>
        <td>
            Foreground color of the up down button's is in the default state.
            <br/>
            <br/>
        </td>
    </tr>
	
</table>

## SfMaskedEdit

<table>
    <tr>
        <th>Theme Dictionary<br/>
            <br/></th>        
        <th>
          Keys
            <br/>
            <br/>
        </th>
        <th>
            Description
            <br/>
            <br/>
        </th>
    </tr>

    <tr>
        <td rowspan="24">
              SfMaskedEditStyles 
            <br/>
            <br/>
        </td>
		<td>
           SfMaskedEditTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, it is possible to customize the appearance of the SfMaskedEdit without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfMaskedEditTheme">CustomTheme</x:String> 
                <Color x:Key="SyncPrimaryColor">Blue</Color> 
                <Color x:Key="SfMaskedEditTextColor">Green</Color> 
            </ResourceDictionary>
        </syncCore:SyncfusionThemeDictionary.MergedDictionaries>
    </syncCore:SyncfusionThemeDictionary>
</Application.Resources>

....

</Application>

{% endhighlight %}
            <br/>
            <br/>
        </td>
	</tr>
	<tr>
        <td>
            SyncPrimaryColor  
            <br/>
            <br/>
        </td>
        <td>
            Border color of the masked edit is in default state.
            <br/>
            <br/>
        </td>
    </tr>
	
    <tr>
        <td>
            SfMaskedEditTextColor   
            <br/>
            <br/>
        </td>
        <td>
            Text color of the masked edit is in default state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
		<td>
            SfMaskedEditBackgroundColor     
            <br/>
            <br/>
        </td>
        <td>
            Background color of the masked edit is in the default state.
            <br/>
            <br/>
        </td>
    </tr>
    
</table>

