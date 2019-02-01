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




