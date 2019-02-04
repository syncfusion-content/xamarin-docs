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
