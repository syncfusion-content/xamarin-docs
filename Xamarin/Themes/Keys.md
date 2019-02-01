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
        <td rowspan="23">
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
          Background color of the RowDragView.
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
             Background color of the [TableSummary](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridTableSummaryRow.html) in SfDataGrid.
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
            Foreground color of the [TableSummary](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridTableSummaryRow.html) in SfDataGrid.
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
            Background color of the [CaptionSummary](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~CaptionSummaryRow.html) in SfDataGrid.
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
            Foreground color of the [CaptionSummary](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~CaptionSummaryRow.html) in SfDataGrid.
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
            Background color of the [GroupSummary](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~GroupSummaryRows.html) in SfDataGrid.
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
              Foreground color of the [GroupSummary](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~GroupSummaryRows.html) in SfDataGrid.
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
        <td rowspan="7">
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
        <td>
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
