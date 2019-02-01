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

## SfListView

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
        <td rowspan="11">
            SfListViewStyles  
            <br/>
            <br/>
        </td>
        <td>
           SfListViewTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of the SfListView without merging common theme resource and control style resource dictionaries.

{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                    <x:String x:Key="SfListViewTheme">CustomTheme</x:String>
                    <Color x:Key="SfListViewBackgroundColor">LightGreen</Color>
                    <Color x:Key="SfListViewForegroundColor">DarkGreen</Color>
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
    <tr>
        <td>
            SfListViewBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of ListView.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfListViewForegroundColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the ListViewItem, when it in the default state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td >
            SfListViewSelectionBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the ListViewItem when it is in selection.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfListViewFocusBorderThickness
            <br/>
            <br/>
        </td>
        <td>
            Border thickness of the ListViewItem when it is in selection.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
        <td>
            SfListViewFocusBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the ListViewItem when it is in selection.
            <br/>
            <br/>
        </td>
    </tr>

    
    <tr>
        <td>
            SfListViewGroupHeaderForegroundColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the GroupHeaderItem, when it in the default state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfListViewLoadMoreForegroundColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the LoadMoreItem When it is in the default state.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
        <td>
            SyncPrimaryLightColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the LoadMoreIndicator when the indicator is in the progressed state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfListViewLoadMoreBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the LoadMoreItem when it is in the default state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfListViewLoadMoreOpacity
            <br/>
            <br/>
        </td>
        <td>
            Percentage of transparency level for the text in the LoadMoreItem when it is in the default state.
            <br/>
            <br/>
        </td>
    </tr>

</table>



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
            By merging this key in application resources, you can customize the appearance of SfLinearProgressBar without merging common theme resource and control style resource dictionaries.
			
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
            Color of the progress indicator in the linear progress bar.
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
            Color of the track in the linear progress bar.
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
            Color of the secondary progress(buffer) indicator in the linear progress bar.
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
            By merging this key in application resources, you can customize the appearance of SfCircularProgressBar without merging common theme resource and control style resource dictionaries.
			
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
            Color of the progress indicator in the circular progress bar.
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
            Color of the track in the circular progress bar.
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
            By merging this key in application resources, you can customize the appearance of SfNumericTextBox without merging common theme resource and control style resource dictionaries.
			
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
            Border color of the numeric text box.
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
            Text color of the numeric text box.
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
            Background color of the numeric text box.
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
            By merging this key in application resources, you can customize the appearance of SfNumericUpDown without merging common theme resource and control style resource dictionaries.
			
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
            Border color of numeric up down.
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
            Text color of the numeric up down.
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
            Background color of numeric up down.
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
            Background color of the up and down buttons.
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
            Foreground color of the up and down buttons.
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
            By merging this key in application resources, you can customize the appearance of SfMaskedEdit without merging common theme resource and control style resource dictionaries.
			
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
            Border color of the masked edit.
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
            Text color of the masked edit.
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
            Background color of the masked edit.
            <br/>
            <br/>
        </td>
    </tr>
    
</table>

## SfPdfViewer

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
        <td rowspan="46">
            SfPdfViewerStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfPdfViewerTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfPdfViewer without merging common theme resource and control style resource dictionaries.    

{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             xmlns:chart="clr-namespace:Syncfusion.SfPdfViewer.XForms;assembly=Syncfusion.SfPdfViewer.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfPdfViewerTheme">CommonTheme</x:String> 
                <Color x:Key="SfPdfViewerToolbarBackgroundColor">Cyan</Color> 
                <Color x:Key="SfPdfViewerToolbarSeparatorColor">Red</Color> 
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
            SfPdfViewerButtonIconEnabledColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the button when it is in enabled state.
            <br/>
            <br/>
        </td>
    </tr>

        <tr>
    <td>
            SfPdfViewerButtonIconDisabledColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the button when it is in disabled state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerButtonPressedColor
            <br/>
            <br/>
        </td>
        <td>
            Pressed color of the toolbar buttons.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerToolbarBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the toolbar.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerToolbarBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the toolbar.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerToolbarSeparatorColor
            <br/>
            <br/>
        </td>
        <td>
            Toolbar separator color.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerEntryTextColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of page number entry.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerEntryBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of page number entry.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerBookmarkTitlebarBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the bookmark titlebar.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerBookmarkTitlebarTextColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the bookmark title.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerBookmarkItemBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the bookmark items.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerTextElementColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the `PDF Viewer` text labels.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerMoreMenuBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the more menu bar.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerMoreMenuTextDisabledColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the more menu items when it is in disabled state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerMoreMenuTextEnabledColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the more menu items when it is in enabled state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerScrollHeadColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the scroll head label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerScrollHeadBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the scroll head.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerScrollHeadPageNumberViewBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the page number alert window.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerSignaturePadTitleColor
            <br/>
            <br/>
        </td>
        <td>
            Title color of the signature pad.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerSignaturePadColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the signature pad view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerSignaturePadHeaderFooterColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of header and footer of signature pad. 
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerSignatureBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the signature pad.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerSignaturePadButtonDisabledColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the signature pad button when it is in disabled state.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfPdfViewerEditWindowPlaceHolderColor
            <br/>
            <br/>
        </td>
        <td>
            Placeholder color of the edit text window.
            <br/>
            <br/>
        </td>
    </tr>

</table>

