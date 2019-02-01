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

## SfDiagram

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
        <td rowspan="8">
            SfDiagramStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfDiagramTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, it is possible to customize the appearance of the SfDiagram without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfDiagramTheme">CustomTheme</x:String> 
                <Color x:Key="SfDiagramStencilBorderColor">Blue</Color> 
                <Color x:Key="SfDiagramStencilHeaderForegroundColor">Green</Color> 
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
            SfDiagramStencilHeaderBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the Diagram Stencil Header.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
        <td>
            SfDiagramStencilHeaderForegroundColor
            <br/>
            <br/>
        </td>
        <td>
            Foreground Color of the Diagram Stencil Header.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
    <td>
            SfDiagramDialogHeaderForegroundColor
            <br/>
            <br/>
        </td>
        <td>
            Header Foregroundcolor of the Diagram Dialog box.
            <br/>
            <br/>
        </td>
    </tr>
    	<tr>
        <td>
            SfDiagramDialogBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background Color of the Diagram Dialog box.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
    <td>
            SfDiagramLabelBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background Color of Diagram Label.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
            SfDiagramStencilBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of Diagram Stencil.
            <br/>
            <br/>
        </td>
    </tr>  
    <tr>
    <td>
            SfDiagramStencilBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background Color of Diagram Stencil.
            <br/>
            <br/>
        </td>
    </tr>
</table>









