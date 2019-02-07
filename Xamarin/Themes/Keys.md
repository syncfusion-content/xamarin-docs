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

## SfChart

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
        <td rowspan="55">
            SfChartStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfChartTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfChart without merging common theme resource and control style resource dictionaries.    

{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             xmlns:chart="clr-namespace:Syncfusion.SfChart.XForms;assembly=Syncfusion.SfChart.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfChartTheme">CommonTheme</x:String> 
                <Color x:Key="SfChartBackgroundColor">Transparent</Color> 
                <Color x:Key="SfChartTitleBackgroundColor">Transparent</Color> 
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
            Stroke color of annotation.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Text color of annotation label.
            <br/>
            <br/>
        </td>
    </tr>

            <tr>
    <td>
            SyncPrimaryLightForegroundColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of trackball label.
            <br/>
            <br/>
        </td>
    </tr>

        <tr>
    <td>
            SfChartTitleTextColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the chart title.
            <br/>
            <br/>
        </td>
    </tr>

        <tr>
    <td>
            SfChartTitleBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the chart title.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartTitleBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the chart title.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the chart.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartSelectionRectFillColor
            <br/>
            <br/>
        </td>
        <td>
            Fill color of the selection rectangle when selection zooming the chart.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartSelectionRectStrokeColor
            <br/>
            <br/>
        </td>
        <td>
            Stroke color of the selection rectangle when selection zooming the chart.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartAnnotationFillColor
            <br/>
            <br/>
        </td>
        <td>
            Fill color of annotation.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartAnnotationStrokeColor
            <br/>
            <br/>
        </td>
        <td>
            Stroke color of the annotation.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartAnnotationTextColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the annotation label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartAnnotationLabelBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the annotation label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartAnnotationLabelBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the annotation label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartAnnotationAxisLabelBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the axis label of VerticalLine and HorizontalLine annotations.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartAnnotationAxisLabelTextColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of axis label of VerticalLine and HorizontalLine annotations.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartAnnotationAxisLabelBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the axis label of VerticalLine and HorizontalLine annotations.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartTrackballLineStrokeColor
            <br/>
            <br/>
        </td>
        <td>
            Stroke color of the trackball line.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartTrackballBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the trackball label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartTrackballBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the trackball label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartTrackballTextColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the trackball label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartTrackballAxisLabelBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the axis label of trackball.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartTrackballAxisLabelBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the axis label of trackball.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartTrackballAxisLabelTextColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of axis label of trackball.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartDataPointSelectionColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the selected segment of the series.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartSeriesSelectionColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the selected series.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartStriplineBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the strip line.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartStriplineBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the strip line.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartStriplineTextColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the strip line label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartStriplineLabelBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the strip line label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartStriplineLabelBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the strip line label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartMajorGridLineColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the axis major grid line.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartMinorGridLineColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the axis minor grid line.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartMajorTickLineColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the axis major tick line.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartMinorTickLineColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the axis minor tick line.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartAxisLineColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the axis line.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartAxisTitleTextColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the axis title text.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartAxisTitleBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the axis title.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartAxisTitleBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the axis title.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartAxisLabelColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the axis label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartAxisLabelBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the axis label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartAxisLabelBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the axis label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartLegendTitleTextColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the Legend title text.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartLegendTitleBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the legend title.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartLegendTitleBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the legend title.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfChartLegendLabelColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the legend label.
            <br/>
            <br/>
        </td>
    </tr>
</table>

## SfDateTimeRangeNavigator

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
            SfDateTimeRangeNavigatorStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfDateTimeRangeNavigatorTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfDateTimeRangeNavigator without merging common theme resource and control style resource dictionaries.    

{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             xmlns:chart="clr-namespace:Syncfusion.SfChart.XForms;assembly=Syncfusion.SfChart.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfDateTimeRangeNavigatorTheme">CommonTheme</x:String> 
                <Color x:Key="SfDateTimeRangeNavigatorBackgroundColor">Transparent</Color> 
                <Color x:Key="SfDateTimeRangeNavigatorOverlayColor">White</Color> 
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
        <td rowspan="3">
            SyncPrimaryColor   
            <br/>
            <br/>
        </td>
        <td>
            Border color of tooltip and thumb. 
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Line color of thumb.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Background color of tooltip.
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
            Selected label text color of scale.
            <br/>
            <br/>
        </td>
    </tr>

     <tr>
    <td>
            SfDateTimeRangeNavigatorBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the date-time range navigator.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfDateTimeRangeNavigatorOverlayColor
            <br/>
            <br/>
        </td>
        <td>
            Overlay color of unselected region of the date time range navigator.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfDateTimeRangeNavigatorLabelTextColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the date time range navigator label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfDateTimeRangeNavigatorLabelBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the date time range navigator label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfDateTimeRangeNavigatorLabelBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the date time range navigator label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfDateTimeRangeNavigatorSelectedLabelTextColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the date time range navigator selected label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfDateTimeRangeNavigatorSelectedLabelBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the date time range navigator selected label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfDateTimeRangeNavigatorSelectedLabelBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the date time range navigator selected label.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfDateTimeRangeNavigatorGridLineColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the date time range navigator grid lines.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfDateTimeRangeNavigatorTickLineColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the date time range navigator tick lines.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfDateTimeRangeNavigatorThumbBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the date time range navigator thumb.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfDateTimeRangeNavigatorThumbBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the date time range navigator thumb.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfDateTimeRangeNavigatorThumbLineColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the date time range navigator thumb line.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfDateTimeRangeNavigatorTooltipBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the date time range navigator tooltip.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfDateTimeRangeNavigatorTooltipBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the date time range navigator tooltip.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfDateTimeRangeNavigatorTooltipTextColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the date time range navigator tooltip.
            <br/>
            <br/>
        </td>
    </tr>
</table>

## SfKanban

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
            SfKanbanStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfKanbanTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfKanban without merging common theme resource and control style resource dictionaries.    

{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             xmlns:chart="clr-namespace:Syncfusion.SfKanban.XForms;assembly=Syncfusion.SfKanban.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfKanbanTheme">CommonTheme</x:String> 
                <Color x:Key="SfKanbanBackgroundColor">Transparent</Color> 
                <Color x:Key="SfKanbanPlaceholderBackgroundColor">White Smoke</Color> 
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
            SfKanbanBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of kanban.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfKanbanMinValidationColor
            <br/>
            <br/>
        </td>
        <td>
            Color value of the error bar for minimum limit validation.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfKanbanMaxValidationColor
            <br/>
            <br/>
        </td>
        <td>
            Color value of the error bar for maximum limit validation.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfKanbanValidationColor
            <br/>
            <br/>
        </td>
        <td>
            Color value of the error bar for validation.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfKanbanPlaceholderBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the placeholder.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfKanbanPlaceholderBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the placeholder.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfKanbanPlaceholderTextColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the placeholder.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfKanbanPlaceholderSelectedBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the selected placeholder.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfKanbanPlaceholderSelectedBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the selected placeholder.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfKanbanPlaceholderSelectedTextColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of the selected placeholder.
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
            Background color of the stencil header.
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
            Foreground color of the stencil header.
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
            Foreground color of header in dialog box.
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
            Background color of header in dialog box.
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
            Background color of Label in dialog box.
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
            Border color of stencil.
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
            Background color of stencil.
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

## SfTreeView

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
            SfTreeViewStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfTreeViewTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfTreeView without merging common theme resource and control style resource dictionaries.

{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfTreeViewTheme">CustomTheme</x:String> 
                <Color x:Key="SfTreeViewSelectionBackgroundColor">Blue</Color> 
                <Color x:Key="SyncPrimaryLightColor">White</Color> 
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
            SfTreeViewBackgroundColor   
            <br/>
            <br/>
        </td>
        <td>
            Background color of TreeView.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
        <td>
            SfTreeViewSelectionBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of TreeViewItem when it is in selection.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
    <td>
            SfTreeViewContentForegroundColor   
            <br/>
            <br/>
        </td>
        <td>
            Text color of content view label when it is in default state.
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
            Text color of content view label when it is in selection.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
    <td>
            SfTreeViewExpanderColor    
            <br/>
            <br/>
        </td>
        <td>
            Color of expander icon.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
            SfTreeViewFocusBorderColor 
            <br/>
            <br/>
        </td>
        <td>
            Border color of focused item.
            <br/>
            <br/>
        </td>
    </tr>  
    <tr>
    <td>
            SfTreeViewFocusBorderThickness  
            <br/>
            <br/>
        </td>
        <td>
            Border thickness of focused item.
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


## SfDataGrid

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
            SfDataGridStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfDataGridTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, it is possible to customize the appearance of the SfDataGrid without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfDataGridTheme">CustomTheme</x:String> 
                <Color x:Key="SfDataGridRecordBackgroundColor">Blue</Color> 
                <Color x:Key="SfDataGridRecordForegroundColor">Green</Color> 
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
            SfDataGridHeaderBackgroundColor  
            <br/>
            <br/>
        </td>
        <td>
            Background color of the row and column headers in the SfDataGrid.
            <br/>
            <br/>
        </td>
    </tr>   

    <tr>
        <td>
            SfDataGridHeaderForegroundColor   
            <br/>
            <br/>
        </td>
        <td>
            Foreground color of the row and column headers in the SfDataGrid.
            <br/>
            <br/>
        </td>
    </tr>  
    
    <tr>
        <td>
            SfDataGridHeaderBorderColor
            <br/>
            <br/>
        </td>
        <td>
          Border color of the row and column header cells in the SfDataGrid.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfDataGridRecordBackgroundColor 
            <br/>
            <br/>
        </td>
        <td>
            Background color of the grid cells in the SfDataGrid.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
        <td>
            SfDataGridRecordForegroundColor  
            <br/>
            <br/>
        </td>
        <td>
           Foreground color of the grid cells in the SfDataGrid.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfDataGridBorderColor   
            <br/>
            <br/>
        </td>
        <td>
          Border color of the grid cells in the SfDataGrid.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
        <td>
            SfDataGridSelectionBackgroundColor    
            <br/>
            <br/>
        </td>
        <td>
            Background color of the selected row in SfDataGrid.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfDataGridSelectionForegroundColor     
            <br/>
            <br/>
        </td>
        <td>
            Foreground color of the selected row in SfDataGrid.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfDataGridAlternatingRowBackgroundColor      
            <br/>
            <br/>
        </td>
        <td>
            Background color of the alternate rows in SfDataGrid.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfDataGridRowDragViewBackgroundColor       
            <br/>
            <br/>
        </td>
        <td>
          Background color of the row drag view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfDataGridRowDragViewForegroundColor           
            <br/>
            <br/>
        </td>
        <td>
          Foreground color of the row drag view.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
        <td>
            SfDataGridColumnDragViewBackgroundColor       
            <br/>
            <br/>
        </td>
        <td>
            Background color of the column drag view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfDataGridColumnDragViewForegroundColor       
            <br/>
            <br/>
        </td>
        <td>
           Foreground color of the column drag view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfDataGridColumnDragViewBorderColor       
            <br/>
            <br/>
        </td>
        <td>
            Border color of the column drag view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfDataGridTableSummaryBackgroundColor       
            <br/>
            <br/>
        </td>
        <td>
             Background color of the [TableSummaryRow](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridTableSummaryRow.html) in SfDataGrid.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
        <td>
            SfDataGridTableSummaryForegroundColor        
            <br/>
            <br/>
        </td>
        <td>
            Foreground color of the `TableSummaryRow` in SfDataGrid.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfDataGridCaptionSummaryRowBackgroundColor         
            <br/>
            <br/>
        </td>
        <td>
            Background color of the [CaptionSummaryRow](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~CaptionSummaryRow.html) in SfDataGrid.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
        <td>
            SfDataGridCaptionSummaryRowForegroundColor          
            <br/>
            <br/>
        </td>
        <td>
            Foreground color of the `CaptionSummaryRow` in SfDataGrid.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
        <td>
            SfDataGridGroupSummaryRowBackgroundColor          
            <br/>
            <br/>
        </td>
        <td>
            Background color of the [GroupSummaryRow](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~GroupSummaryRows.html) in SfDataGrid.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
        <td>
            SfDataGridGroupSummaryRowForegroundColor          
            <br/>
            <br/>
        </td>
        <td>
              Foreground color of the `GroupSummaryRow` in SfDataGrid.
            <br/>
            <br/>
        </td>
    </tr>     

     <tr>
        <td>
            SfDataGridLoadMoreViewBackgroundColor          
            <br/>
            <br/>
        </td>
        <td>
            Background color of the LoadMore view in SfDataGrid.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
        <td>
            SfDataGridLoadMoreViewForegroundColor          
            <br/>
            <br/>
        </td>
        <td>
              Foreground color of the LoadMore view in SfDataGrid.
            <br/>
            <br/>
        </td>
    </tr>   

     <tr>
        <td>
            SfDataGridIndentBackgroundColor          
            <br/>
            <br/>
        </td>
        <td>
              Background color of the indent column in SfDataGrid.
            <br/>
            <br/>
        </td>
    </tr>     

</table>




## SfPopupLayout

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
        <td rowspan="12">
            SfPopupLayoutStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfPopupLayoutTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, it is possible to customize the appearance of the SfPopupLayout without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfPopupLayoutTheme">CustomTheme</x:String> 
                <Color x:Key="SfPopupLayoutHeaderBackgroundColor">Blue</Color> 
                <Color x:Key="SfPopupLayoutFooterBackgroundColor">Blue</Color> 
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
            SfPopupLayoutHeaderBackgroundColor  
            <br/>
            <br/>
        </td>
        <td>
           Background color of the header view in SfPopupLayout.
            <br/>
            <br/>
        </td>
    </tr>   

    <tr>
        <td>
            SfPopupLayoutFooterBackgroundColor   
            <br/>
            <br/>
        </td>
        <td>
          Background color of the footer view in SfPopupLayout.
            <br/>
            <br/>
        </td>
    </tr>  

     <tr>
        <td rowspan="2">
            SfPopupLayoutAcceptButtonBackgroundColor  
            <br/>
            <br/>
        </td>
        <td>
             Background color of the accept button in Xamarin.Forms.Android and Xamarin.Forms.iOS platform.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
           Note: Background color of the accept button for Xamarin.Forms.UWP platform is obtained from SyncPrimaryColor key value.
            <br/>
            <br/>
        </td>
    </tr>   

      <tr>
        <td rowspan="2">
            SfPopupLayoutDeclineButtonTextColor  
            <br/>
            <br/>
        </td>
        <td>
              Text color of the decline button in Xamarin.Forms.UWP platform.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
           Note: Text color of the decline button for Xamarin.Forms.Android and Xamarin.Forms.iOS platform is obtained from SyncPrimaryLightColor key value.
            <br/>
            <br/>
        </td>
    </tr>     
      
     <tr>
        <td rowspan="2">
            SfPopupLayoutBorderColor  
            <br/>
            <br/>
        </td>
        <td>
            Border color of the SfPopupLayout in Xamarin.Forms.Android and Xamarin.Forms.iOS platform.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
           Note: Border color of the SfPopupLayout for Xamarin.Forms.UWP platform is obtained from SyncPrimaryColor key value.
            <br/>
            <br/>
        </td>
    </tr>     

    <tr>
        <td rowspan="2">
            SfPopupLayoutDeclineButtonBackgroundColor  
            <br/>
            <br/>
        </td>
        <td>
             Background color of the decline button in Xamarin.Forms.UWP platform.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
           Note: Background color of the decline button for Xamarin.Forms.Android and Xamarin.Forms.iOS platform is obtained from SyncPrimaryLightColor key value.
            <br/>
            <br/>
        </td>
    </tr> 

     <tr>
        <td>
            SfPopupLayoutHeaderTextColor   
            <br/>
            <br/>
        </td>
        <td>
           Text color of the header in SfPopupLayout.
            <br/>
            <br/>
        </td>
    </tr>

</table>


## SfPullToRefresh

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
        <td rowspan="2">
            SfPullToRefreshStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfPullToRefreshTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, it is possible to customize the appearance of the SfPullToRefresh without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfPullToRefreshTheme">CustomTheme</x:String> 
                <Color x:Key="SfPullToRefreshBackgroundColor">Blue</Color> 
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
            SfPullToRefreshBackgroundColor  
            <br/>
            <br/>
        </td>
        <td>
            Background color of the circle view in SfPullToRefresh.
            <br/>
            <br/>
        </td>
    </tr>   

</table>

## SfSchedule

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
       <td rowspan="54">
            SfScheduleStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfScheduleTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, it is possible to customize the appearance of the SfSchedule without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfScheduleTheme">CustomTheme</x:String> 
                <Color x:Key="SfScheduleHeaderTextColor">Red</Color>
                <Color x:Key="SfScheduleViewHeaderDayTextColor">Blue</Color>
                <Color x:Key="SfScheduleViewHeaderDateTextColor">Blue</Color> 
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
        <td >
            SyncPrimaryColor  
            <br/>
            <br/>
        </td>
        <td>
            Change the color of today selection background in schedule month view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td rowspan="2">
            SyncPrimaryLightColor.
            <br/>
            <br/>
        </td>
<td>
            Change the color of current day(Sun,Mon,etc) text in schedule day, week and work week view.
            <br/>
            <br/>
        </td>
    </tr>
<tr>
        <td>
            Change the color of current date(10,11,etc) text in schedule day, week and work week view.
            <br/>
            <br/>
        </td>
    </tr>

<tr>
        <td>
            SyncPrimaryForegroundColor 
            <br/>
            <br/>
        </td>
        <td>
            Change the color of current day text in schedule month view.
            <br/>
            <br/>
        </td>
    </tr>

<tr>
        <td>
            SfScheduleDayViewNonWorkingHoursTimeSlotColor 
            <br/>
            <br/>
        </td>
        <td>
            Change the color of non working hour time slot in schedule day view.
            <br/>
            <br/>
        </td>
    </tr>

	<tr>
        <td>
            SfScheduleDayViewNonWorkingHoursTimeSlotBorderColor  
            <br/>
            <br/>
        </td>
        <td>
            Change the color of non working hour time slot border in schedule day view.
            <br/>
            <br/>
        </td>
    </tr>


    <tr>
        <td>
            SfScheduleDayViewTimeSlotColor   
            <br/>
            <br/>
        </td>
        <td>
            Change the color of time slot in schedule day view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfScheduleDayViewTimeSlotBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Change the color of time slot border color of schedule day view.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
    <td>
            SfScheduleDayViewVerticalLineColor 
            <br/>
            <br/>
        </td>
        <td>
            Change the color of time slot vertical lines at schedule day view.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfScheduleDayViewAllDayAppointmentLayoutColor  
            <br/>
            <br/>
        </td>
        <td>
            Change the color of all day appointment layout color, when enable the all day appointment in schedule day view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfScheduleWeekViewNonWorkingHoursTimeSlotColor   
            <br/>
            <br/>
        </td>
        <td>
           Change the color of non working hour time slot in schedule week view.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfScheduleWeekViewNonWorkingHoursTimeSlotBorderColor    
            <br/>
            <br/>
        </td>
        <td>
            Change the color of non working hour time slot border in schedule week view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfScheduleWeekViewTimeSlotColor    
            <br/>
            <br/>
        </td>
        <td>
            Change the color of time slot in schedule week view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfScheduleWeekViewTimeSlotBorderColor      
            <br/>
            <br/>
        </td>
        <td>
            Change the color of time slot border in schedule week view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfScheduleWeekViewVerticalLineColor       
            <br/>
            <br/>
        </td>
        <td>
            Change the color of time slots vertical line in schedule week view. 
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfScheduleWeekViewAllDayAppointmentLayoutColor           
            <br/>
            <br/>
        </td>
        <td>
            Change the color of all day appointment layout color, when enable the all day appointment in schedule week view.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfScheduleWorkWeekViewNonWorkingHoursTimeSlotColor       
            <br/>
            <br/>
        </td>
        <td>
            Change the color of non working hour timeslot in schedule work week view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfScheduleWorkWeekViewNonWorkingHoursTimeSlotBorderColor       
            <br/>
            <br/>
        </td>
        <td>
            Change the color of non working hour time slot border in schedule work week view.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfScheduleWorkWeekViewTimeSlotColor       
            <br/>
            <br/>
        </td>
        <td>
            Change the color of time slot in schedule work week view.
            <br/>
            <br/>
        </td>
    </tr>
    
     <tr>
    <td>
            SfScheduleWorkWeekViewTimeSlotBorderColor       
            <br/>
            <br/>
        </td>
        <td>
            Change the color of time slot border in schedule work week view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfScheduleWorkWeekViewVerticalLineColor       
            <br/>
            <br/>
        </td>
        <td>
            Change the color of time slot vertical line in schedule work week view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfScheduleWorkWeekViewAllDayAppointmentLayoutColor       
            <br/>
            <br/>
        </td>
        <td>
            Change the color of all day appointment layout color, when enable the all day appointment in schedule work week view.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfScheduleMonthViewTodayBackground        
            <br/>
            <br/>
        </td>
        <td>
            Change the color of current date circle background at schedule month view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfScheduleMonthViewSelectionTextColor         
            <br/>
            <br/>
        </td>
        <td>
            Change the color of select month cell text at schedule month view.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfScheduleDayViewLabelTimeLabelColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of time slot labels(2pm,3pm,etc) at schedule day view.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfScheduleWeekViewLabelTimeLabelColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of time slot labels(2pm,3pm,etc) at schedule week view.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfScheduleWorkWeekViewLabelTimeLabelColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of time slot labels(2pm,3pm,etc) at schedule work week view.
            <br/>
            <br/>
        </td>
    </tr>    
    
      <tr>
    <td>
            SfScheduleHeaderBackgroundColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of header layout in schedule.
            <br/>
            <br/>
        </td>
    </tr>  
    
     <tr>
    <td>
            SfScheduleHeaderTextColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of header text in schedule.
            <br/>
            <br/>
        </td>
    </tr>  
    
    <tr>
    <td>
            SfScheduleViewHeaderDayTextColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of view header day text(Sunday,Monday,etc) in schedule.
            <br/>
            <br/>
        </td>
    </tr>  
    
    <tr>
    <td>
            SfScheduleViewHeaderBackgroundColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of view header layout in schedule.
            <br/>
            <br/>
        </td>
    </tr>  
    
    <tr>
    <td>
            SfScheduleViewHeaderDateTextColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of view header date text(10,11,etc) in schedule.
            <br/>
            <br/>
        </td>
    </tr> 
    
     <tr>
    <td>
            SfScheduleSelectionBackgroundColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of selection background at schedule.
            <br/>
            <br/>
        </td>
    </tr> 
    
    <tr>
    <td>
            SfScheduleSelectionBorderColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of selection border at schedule.
            <br/>
            <br/>
        </td>
    </tr> 
    
     <tr>
    <td>
            SfScheduleAppointmentTextColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of appointment text in schedule day, week and work week view.
            <br/>
            <br/>
        </td>
    </tr> 
    
    <tr>
    <td>
            SfScheduleAppointmentBorderColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the border color of appointment layout in schedule day, week and work week view.
            <br/>
            <br/>
        </td>
    </tr> 
    
    <tr>
    <td>
            SfScheduleAppointmentSelectionBorderColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the border color of appointment layout while select in schedule day, week and work week view.
            <br/>
            <br/>
        </td>
    </tr> 
   
   <tr>
    <td>
            SfScheduleAppointmentSelectionTextColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the text color of appointment while select in schedule day, week and work week view.
            <br/>
            <br/>
        </td>
    </tr>  
    
     <tr>
    <td>
            SfScheduleMonthCellTextColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of month cell text in schedule month view.
            <br/>
            <br/>
        </td>
    </tr>  
    
     <tr>
    <td>
            SfScheduleMonthCellBackgroundColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of month cell background in schedule month view.
            <br/>
            <br/>
        </td>
    </tr>  
    
     <tr>
    <td>
            SfScheduleMonthCellTodayBackgroundColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the current day background color of month cell in schedule month view.
            <br/>
            <br/>
        </td>
    </tr>  
    
     <tr>
    <td>
            SfScheduleMonthCellTodayTextColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the current date text color of month cell in schedule month view.
            <br/>
            <br/>
        </td>
    </tr> 
    
      <tr>
    <td>
            SfScheduleMonthCellPreviousMonthTextColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the previous month date text color of month cell in schedule month view.
            <br/>
            <br/>
        </td>
    </tr> 
    
     <tr>
    <td>
            SfScheduleMonthCellPreviousMonthBackgroundColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the previous month background color of month cell in schedule month view.
            <br/>
            <br/>
        </td>
    </tr> 
    
     <tr>
    <td>
            SfScheduleMonthCellNextMonthBackgroundColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the next month background color of month cell in schedule month view.
            <br/>
            <br/>
        </td>
    </tr> 
    
     <tr>
    <td>
            SfScheduleMonthCellNextMonthTextColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the next month date text color of month cell in schedule month view.
            <br/>
            <br/>
        </td>
    </tr> 
    
      <tr>
    <td>
            SfScheduleMonthViewWeekNumberTextColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the week number text color, when enable the week number view in schedule month view.
            <br/>
            <br/>
        </td>
    </tr> 
    
     <tr>
    <td>
            SfScheduleMonthViewWeekNumberBackgroundColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the week number background color, when enable the week number view in schedule month view.
            <br/>
            <br/>
        </td>
    </tr> 
    
         <tr>
     <td>
            SfScheduleMonthAgendaViewSubjectFontColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the appointment subject text color, when enable the agenda view in schedule month view.
            <br/>
            <br/>
        </td>
    </tr> 
    
    <tr>
     <td>
            SfScheduleMonthAgendaViewBackgroundColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the agenda view layout background color of schedule month view.
            <br/>
            <br/>
        </td>
    </tr> 
    
     <tr>
     <td>
            SfScheduleMonthAgendaViewTimeFontColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the appointment time text color, when enable the agenda view in schedule month view.
            <br/>
            <br/>
        </td>
    </tr> 
    
     <tr>
     <td>
            SfScheduleMonthAgendaViewDateFontColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the selected date text color, when enable the agenda view in schedule month view.
            <br/>
            <br/>
        </td>
    </tr> 

 <tr>
     <td>
            SfScheduleTimeIndicatorTextColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the time indicator text color, when enable drag and drop in schedule day, week and work week view.
            <br/>
            <br/>
        </td>
    </tr> 
</table>

## SfCalendar

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
       <td rowspan="30">
            SfCalendarStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfCalendarTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, it is possible to customize the appearance of the SfCalendar without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfCalendarTheme">CustomTheme</x:String> 
                <Color x:Key="SfCalendarInlineBackgroundColor">Green</Color>
                    <Color x:Key="SfCalendarInlineTextColor">White</Color>
                    <Color x:Key="SfCalendarWeekEndBackgroundColor">Blue</Color>
                    <Color x:Key="SfCalendarYearViewHeaderTextColor">Blue</Color>
                    <Color x:Key="SfCalendarYearViewDateTextColor">Green</Color>
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
            SyncPrimaryLightColor.
            <br/>
            <br/>
        </td>
<td>
            Change the color of current day text in calendar month view.
            <br/>
            <br/>
        </td>
    </tr>
<tr>
        <td>
            Change the color of month header text in calendar year view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
		<td>
           SfCalendarInlineTextColor 
            <br/>
            <br/>
        </td>
        <td>    
           Change the color of inline appointment text in calendar month view.
            <br/>
            <br/>
        </td>
	</tr>


	<tr>
        <td>
            SfCalendarBlackoutColor  
            <br/>
            <br/>
        </td>
        <td>
            Change the color of black out date denoting view in calendar month view.
            <br/>
            <br/>
        </td>
    </tr>


    <tr>
        <td>
            SfCalendarDateSelectionColor   
            <br/>
            <br/>
        </td>
        <td>
            Change the color of selected date background in calendar month view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfCalendarInlineBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Change the color of inline layout background in calendar month view.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
    <td>
            SfCalendarSelectedDayTextColor 
            <br/>
            <br/>
        </td>
        <td>
            Change the color of select date text color in calendar month view.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfCalendarBorderColor  
            <br/>
            <br/>
        </td>
        <td>
            Change the border color(vertical/horizontal line) of calendar month view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfCalendarWeekDayBackgroundColor   
            <br/>
            <br/>
        </td>
        <td>
           Change the color of week day(Monday to Friday month cell) background in calendar month view.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfCalendarWeekDayTextColor    
            <br/>
            <br/>
        </td>
        <td>
            Change the color of week day(Monday to Friday month cell) text in calendar month view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfCalendarDisabledBackgroundColor    
            <br/>
            <br/>
        </td>
        <td>
            Change the color of disabled month cell date background in calendar month view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfCalendarDisabledTextColor      
            <br/>
            <br/>
        </td>
        <td>
            Change the color of disabled month cell date text in calendar month view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfCalendarPreviousMonthBackgroundColor       
            <br/>
            <br/>
        </td>
        <td>
            Change the color of previous month cell date background in calendar month view. 
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfCalendarPreviousMonthTextColor           
            <br/>
            <br/>
        </td>
        <td>
            Change the color of previous month cell date text in calendar month view. 
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfCalendarCurrentMonthBackgroundColor       
            <br/>
            <br/>
        </td>
        <td>
            Change the color of current month cell background in calendar month view. 
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfCalendarCurrentMonthTextColor       
            <br/>
            <br/>
        </td>
        <td>
            Change the color of current month cell date text in calendar month view. 
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfCalendarWeekEndTextColor       
            <br/>
            <br/>
        </td>
        <td>
            Change the color of week end(Sunday & Saturday month cell) text in calendar month view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfCalendarDayHeaderTextColor       
            <br/>
            <br/>
        </td>
        <td>
            Change the color day header (Sunday,Monday,etc) text color in calendar month view.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfCalendarDayHeaderBackgroundColor        
            <br/>
            <br/>
        </td>
        <td>
            Change the color day header (Sunday,Monday,etc) background color in calendar month view.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfCalendarWeekEndBackgroundColor         
            <br/>
            <br/>
        </td>
        <td>
            Change the color of week end(Sunday & Saturday month cell) background in calendar month view.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfCalendarHeaderBackgroundColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of header layout background in calendar.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfCalendarHeaderTextColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of header layout date text in calendar.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfCalendarYearViewLayoutBackground          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of year view layout background in calendar.
            <br/>
            <br/>
        </td>
    </tr>    
    
      <tr>
    <td>
            SfCalendarYearViewHeaderBackground          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of header layout background in calendar year view.
            <br/>
            <br/>
        </td>
    </tr>  
    
     <tr>
    <td>
            SfCalendarYearViewMonthLayoutBackground          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of month layout(Jan,Feb,etc) background in calendar year view.
            <br/>
            <br/>
        </td>
    </tr>  
    
    <tr>
    <td>
            SfCalendarYearViewMonthHeaderBackground          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of month layout header(Jan,Feb,etc) background in calendar year view.
            <br/>
            <br/>
        </td>
    </tr>  
    
    <tr>
    <td>
            SfCalendarYearViewDateTextColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of month date (10,11,etc) text in calendar year view.
            <br/>
            <br/>
        </td>
    </tr>  
    
     <tr>
    <td>
            SfCalendarYearViewHeaderTextColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of month header text(Jan,Feb,etc) in calendar year view.
            <br/>
            <br/>
        </td>
    </tr> 
</table>

## SfAutoComplete

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
            SfAutoCompleteStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfAutoCompleteTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfAutoComplete without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfAutoCompleteTheme">CustomTheme</x:String> 
                <Color x:Key="SfAutoCompleteBackgroundColor">Red</Color> 
                <Color x:Key="SfAutoCompleteTextColor">Green</Color> 
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
        <td rowspan="2">
            SyncPrimaryColor  
            <br/>
            <br/>
        </td>
        <td>
            Color of highlighted text in AutoComplete.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Color of indicator text in AutoComplete.
            <br/>
            <br/>
        </td> 
    </tr>
	</tr>
	<tr>
        <td>
            SfAutoCompleteBorderColor  
            <br/>
            <br/>
        </td>
        <td>
            Border color of AutoComplete.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            SfAutoCompleteClearButtonColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the close button when enter the input text.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
    <td>
            SfAutoCompleteWatermarkColor 
            <br/>
            <br/>
        </td>
        <td>
            Color of AutoComplete's watermark text.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfAutoCompleteDropDownBackgroundColor  
            <br/>
            <br/>
        </td>
        <td>
            Background color of the drop-down box.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfAutoCompleteDropDownTextColor   
            <br/>
            <br/>
        </td>
        <td>
            Text color of items in the drop-down box.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
    <td>
            SfAutoCompleteTokenBackgroundColor    
            <br/>
            <br/>
        </td>
        <td>
            Background color of token.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfAutoCompleteTokenTextColor
            <br/>
            <br/>
        </td>
        <td>
           Color of token's text.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
    <td>
            SfAutoCompleteTokenDeleteButtonColor      
            <br/>
            <br/>
        </td>
        <td>
            Color of token's delete button.
            <br/>
            <br/>
        </td>
    </tr>

</table>

## SfBusyIndicator

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
        <td rowspan="3">
            SfBusyIndicatorStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfBusyIndicatorTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfBusyIndicator without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfBusyIndicatorTheme">CustomTheme</x:String> 
                <Color x:Key="SfBusyIndicatorTextColor">Black</Color> 
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
</table>

## SfButton

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
        <td rowspan="3">
            SfButtonStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfButtonTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfButton without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfButtonTheme">CustomTheme</x:String> 
                <Color x:Key="SyncPrimaryColor">Black</Color> 
                <Color x:Key="SyncPrimaryForegroundColor">White</Color>
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
            Color of border when text input layout is focused.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr> 
    <td>
            SyncPrimaryDarkColor  
            <br/>
            <br/>
        </td>
        <td>
            Color of the button when it is in the pressed state.
            <br/>
            <br/>
        </td>
    </tr>

</table>

## SfBorder

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
        <td rowspan="3">
            SfBorderStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfBorderTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfBorder without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfBorderTheme">CustomTheme</x:String> 
                <Color x:Key="SfBorderBackgroundColor">LightGray</Color> 
                <Color x:Key="SfBorderBorderColor">Gray</Color> 
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

</table>

## SfCarousel

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
        <td rowspan="3">
            SfCarouselStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfCarouselTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfCarousel without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfCarouselTheme">CustomTheme</x:String> 
                <Color x:Key="SfCarouselBackgroundColor">White</Color> 
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

</table>

## SfCheckBox

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
        <td rowspan="5">
            SfCheckBoxStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfCheckBoxTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfCheckBox without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfCheckBoxTheme">CustomTheme</x:String> 
                <Color x:Key="SfCheckBoxBackgroundColor">White</Color> 
                <Color x:Key="SfCheckBoxTextColor">Black</Color> 
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
            SfCheckBoxUncheckedColor 
            <br/>
            <br/>
        </td>
        <td>
            Color of unchecked item.
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
            Color of checked item.
            <br/>
            <br/>
        </td>
    </tr>

</table>

## SfChip

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
        <td rowspan="7">
            SfChipStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfChipTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfChip without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfChipTheme">CustomTheme</x:String> 
                <Color x:Key="SfChipBackgroundColor">LightGray</Color> 
                <Color x:Key="SfChipBorderColor">Transparent</Color> 
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
            SfChipTextColor  
            <br/>
            <br/>
        </td>
        <td>
            Color of the text in the SfChip.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            SfChipCloseButtonColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the close button in SfChip.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
    <td>
           SfChipSelectionIndicatorColor.
            <br/>
            <br/>
        </td>
        <td>
            Color of the selection indicator in SfChip.
            <br/>
            <br/>
        </td>
    </tr>

</table>

## SfChipGroup

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
        <td rowspan="6">
            SfChipGroupStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfChipGroupTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfChipGroup without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfChipGroupTheme">CustomTheme</x:String> 
                <Color x:Key="SfChipGroupBackgroundColor">Blue</Color> 
                <Color x:Key="SfChipBorderColor">Transparent</Color> 
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
            SfChipGroupTextColor  
            <br/>
            <br/>
        </td>
        <td>
            Color of the text in SfChipGroup.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            SfChipGroupCloseButtonColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the close button in SfChipGroup.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
    <td>
           SfChipSelectionIndicatorColor.
            <br/>
            <br/>
        </td>
        <td>
            Color of the selection indicator in SfChipGroup.
            <br/>
            <br/>
        </td>
    </tr>

</table>

## SfComboBox

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
        <td rowspan="15">
            SfComboBoxStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfComboBoxTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfComboBox without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfComboBoxTheme">CustomTheme</x:String> 
                <Color x:Key="SfComboBoxBackgroundColor">White</Color> 
                <Color x:Key="SfComboBoxTextColor">Black</Color> 
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
        <td rowspan="2">
            SyncPrimaryColor  
            <br/>
            <br/>
        </td>
        <td>
            Color of highlighted text in ComboBox.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Color of indicator text in ComboBox.
            <br/>
            <br/>
        </td> 
    </tr>
	</tr>
	<tr>
        <td>
            SfComboBoxBorderColor  
            <br/>
            <br/>
        </td>
        <td>
            Border color of SfComboBox.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            SfComboBoxClearButtonColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the close button in SfComboBox.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
    <td>
           SfComboBoxWatermarkColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the watermark's text in SfComboBox.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
    <td>
           SfComboBoxDropDownBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the suggestion box in SfComboBox.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfComboBoxDropDownTextColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the suggestion box's text in SfComboBox.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfComboBoxTokenBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the token in SfComboBox.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfComboBoxTokenTextColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the token's text in SfComboBox.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfComboBoxTokenDeleteButtonColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the token's delete button in SfComboBox.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfComboBoxDropDownButtonBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the drop-down button in SfComboBox.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
    <td>
           SfComboBoxDropDownButtonTextColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the drop-down button's text in SfComboBox.
            <br/>
            <br/>
        </td>
    </tr>

</table>

## SfNavigationDrawer

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
        <td rowspan="5">
            SfNavigationDrawerStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfNavigationDrawerTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfNavigationDrawer without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfNavigationDrawerTheme">CustomTheme</x:String> 
                <Color x:Key="SfNavigationDrawerBackgroundColor">Black</Color> 
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

</table>

## SfPicker

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
            SfPickerStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfPickerTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfPicker without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfPickerTheme">CustomTheme</x:String> 
                <Color x:Key="SfPickerBackgroundColor">Black</Color> 
                <Color x:Key="SfPickerBorderColor">Red</Color> 
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
           Background color of header in SfPicker.
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
           Color of SelectedItem's text in SfPicker.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
    <td>
           SyncPrimaryForegroundColor
            <br/>
            <br/>
        </td>
        <td>
           Color of Header's text in SfPicker.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfPickerUnselectedItemTextColor
            <br/>
            <br/>
        </td>
        <td>
            Color of UnSelectedItem's text in SfPicker.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfPickerColumnHeaderTextColor
            <br/>
            <br/>
        </td>
        <td>
            Color of column header's text in SfPicker.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfPickerColumnHeaderBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of theColumn header in SfPicker.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfPickerSelectionBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the selected item in SfPicker.
            <br/>
            <br/>
        </td>
    </tr>

</table>

## SfRadioButton

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
        <td rowspan="5">
            SfRadioButtonStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfRadioButtonTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfRadioButton without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfRadioButtonTheme">CustomTheme</x:String> 
                <Color x:Key="SfRadioButtonBackgroundColor">White</Color> 
                <Color x:Key="SfRadioButtonTextColor">Black</Color> 
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
            Color of checked item.
            <br/>
            <br/>
        </td>
    </tr>
       <tr>
    <td>
           SfRadioButtonUncheckedColor
            <br/>
            <br/>
        </td>
        <td>
            Color of unchecked item.
            <br/>
            <br/>
        </td>
    </tr>

</table>

## SfRadialMenu

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
        <td rowspan="9">
            SfRadialMenuStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfRadialMenuTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfRadialMenu without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfRadialMenuTheme">CustomTheme</x:String> 
                <Color x:Key="SfRadialMenuCenterButtonBackgroundColor">Gray</Color> 
                <Color x:Key="SfRadialMenuCenterButtonTextColor">White</Color> 
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
            Selection color of SfRadialMenu.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfRadialMenuCenterButtonBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the center button's border in SfRadialMenu.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfRadialMenuRimColor
            <br/>
            <br/>
        </td>
        <td>
            Color of the rim when tap the center button of SfRadialMenu.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfRadialMenuSeparatorColor
            <br/>
            <br/>
        </td>
        <td>
            Color of separator that appears between two items in SfRadialMenu.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfRadialMenuTextColor
            <br/>
            <br/>
        </td>
        <td>
            Color of RadialMenu's text.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfRadialMenuIconFontColor
            <br/>
            <br/>
        </td>
        <td>
            Color of font icon in SfRadialMenu.
            <br/>
            <br/>
        </td>
    </tr>

</table>

## SfRangeSlider

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
        <td rowspan="9">
            SfRangeSliderStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfRangeSliderTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfRangeSlider without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfRadialMenuTheme">CustomTheme</x:String> 
                <Color x:Key="SfRangeSliderBackgroundColor">White</Color> 
                <Color x:Key="SfRangeSliderTickColor">Gray</Color> 
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
            Selection color of track in SfRangeSlider.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Knob color in SfRangeSlider
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfRangeSliderLabelColor
            <br/>
            <br/>
        </td>
        <td>
            Color of SfRangeSlider's label.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfRangeSliderUnselectedTrackColor
            <br/>
            <br/>
        </td>
        <td>
            Color of unselected track in SfRangeSlider.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfRangeSliderToolTipBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of tooltip in SfRangeSlider.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfRangeSliderToolTipTextColor
            <br/>
            <br/>
        </td>
        <td>
            Color of tooltip's text in SfRangeSlider.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
    <td>
           SfRangeSliderToolTipBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Color of tooltip's border in SfRangeSlider.
            <br/>
            <br/>
        </td>
    </tr>

</table>

## SfRating

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
            SfRatingStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfRatingTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfRating without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfRatingTheme">CustomTheme</x:String> 
                <Color x:Key="SfRatingUnratedFillColor">White</Color> 
                <Color x:Key="SfRatingUnratedStrokeColor">Green</Color> 
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
           Stroke color of rated items.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Fill color of rated items.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            SfRatingTooltipBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Background color of the tooltip in SfRating.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfRatingTooltipTextColor
            <br/>
            <br/>
        </td>
        <td>
            Text color inside the tooltip in SfRating.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfRatingTooltipBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Border color of the tooltip in SfRating.
            <br/>
            <br/>
        </td>
    </tr>

</table>

## SfRotator
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
        <td rowspan="3">
            SfRotatorStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfRotatorTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfRotator without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfRotatorTheme">CustomTheme</x:String> 
                <Color x:Key="SfRotatorUnselectedDotColor">White</Color> 
                <Color x:Key="SfRotatorDotsBorderColor">Gray</Color> 
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
           Color of selected dots in SfRotator.
            <br/>
            <br/>
        </td>
    </tr>

</table>

## SfSegmentedControl
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
            SfSegmentedControlStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfSegmentedControlTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfSegmentedControl without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfSegmentedControlTheme">CustomTheme</x:String> 
                <Color x:Key="SfSegmentedControlBorderColor">Gray</Color> 
                <Color x:Key="SfSegmentColor">White</Color> 
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
            SyncPrimaryForegroundColor
            <br/>
            <br/>
        </td>
        <td>
            Text color of selected item in the SfSegmentedControl.
            <br/>
            <br/>
        </td>
    </tr>
        <tr>
        <td>
            SfSegmentFontIconFontColor
            <br/>
            <br/>
        </td>
        <td>
            Color of font icon in the SfSegmentedControl.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            SfSegmentFontColor
            <br/>
            <br/>
        </td>
        <td>
            Color of font in the SfSegmentedControl.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
        <td>
            SfSegmentBorderColor
            <br/>
            <br/>
        </td>
        <td>
            Color of segment's border in the SfSegmentedControl.
            <br/>
            <br/>
        </td>
    </tr>

</table>

## SfTabView

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
            SfTabViewStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfTabViewTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, you can customize the appearance of SfTabView without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfTabViewTheme">CustomTheme</x:String> 
                <Color x:Key="SfTabItemFontColor">Red</Color>  
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
            SfTabItemFontColor  
            <br/>
            <br/>
        </td>
        <td>
           Font color of title in SfTabView.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
             Font color of font icon in SfTabView.
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
            Background color of tab header in SfTabView.
            <br/>
            <br/>
        </td>
    </tr>
     <tr>
        <td rowspan="2">
            SyncPrimaryForegroundColor  
            <br/>
            <br/>
        </td>
        <td>
           Selection color of tab item in SfTabView.
            <br/>
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Color of selection indicator in SfTabView.
            <br/>
            <br/>
        </td>
    </tr>

</table>

## SfDataForm

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
            SfDataFormStyles  
            <br/>
            <br/>
        </td>
		<td>
           SfDataFormTheme 
            <br/>
            <br/>
        </td>
        <td>    
            By merging this key in application resources, it is possible to customize the appearance of the SfDataForm without merging common theme resource and control style resource dictionaries.
			
{% highlight xaml %}

<Application xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms"
             ...>
<Application.Resources>
    <syncCore:SyncfusionThemeDictionary>
        <syncCore:SyncfusionThemeDictionary.MergedDictionaries>
            <ResourceDictionary>
                <x:String x:Key="SfDataFormTheme">CustomTheme</x:String>
                <Color x:Key="SfDataFormEditorTextColor">Red</Color>
                <Color x:Key="SfDataFormLabelTextColor">Pink</Color>
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
            Border color of dataform editors when focused and date time picker's background color in dataform.
            <br/>
            <br/>
        </td>
    </tr>
	<tr>
        <td>
            SfDataFormBackgroundColor  
            <br/>
            <br/>
        </td>
        <td>
            Background color of the dataform.
            <br/>
            <br/>
        </td>
    </tr>   

    <tr>
        <td>
            SfDataFormEditorBackgroundColor   
            <br/>
            <br/>
        </td>
        <td>
            Background color of the dataform editors.
            <br/>
            <br/>
        </td>
    </tr>  
    
    <tr>
        <td>
            SfDataFormEditorDisabledBackgroundColor
            <br/>
            <br/>
        </td>
        <td>
            Disabled editor`s background color in dataform.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfDataFormEditorTextColor 
            <br/>
            <br/>
        </td>
        <td>
            Text color of the dataform editors.
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
        <td>
            SfDataFormEditorPlaceholderColor  
            <br/>
            <br/>
        </td>
        <td>
           Placeholder color of the editor in dataform.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfDataFormEditorDisabledTextColor   
            <br/>
            <br/>
        </td>
        <td>
     		Disabled editor`s text color in dataform.     
            <br/>
            <br/>
        </td>
    </tr>
    
    <tr>
        <td>
            SfDataFormLabelTextColor    
            <br/>
            <br/>
        </td>
        <td>
            Text color of the dataform labels.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfDataFormLabelDisabledTextColor     
            <br/>
            <br/>
        </td>
        <td>
			Disabled label`s text color in dataform.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfDataFormLabelBackgroundColor      
            <br/>
            <br/>
        </td>
        <td>
            Background color of the dataform labels.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfDataFormLabelDisabledBackgroundColor       
            <br/>
            <br/>
        </td>
        <td>
		    Disabled label`s background color in dataform.
            <br/>
            <br/>
        </td>
    </tr>

    <tr>
        <td>
            SfDataFormEditorBorderColor           
            <br/>
            <br/>
        </td>
        <td>
          Border color of the dataform editors.
            <br/>
            <br/>
        </td>
    </tr>
</table>