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
        <td rowspan="49">
            SfScheduleStyles  
            <br/>
            <br/>
        </td>
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
            Change the color of view header day text(sun,mon,etc) in schedule.
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
        <td rowspan="27">
            SfCalendarStyles  
            <br/>
            <br/>
        </td>
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
           Change the color of week day(monday to friday month cell) background in calendar month view.
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
            Change the color of week day(monday to friday month cell) text in calendar month view.
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
            Change the color of prvious month cell date background in calendar month view. 
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
            Change the color of prvious month cell date text in calendar month view. 
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
            Change the color of week end(sunday & saturday month cell) text in calendar month view.
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
            Change the color day header (sun,mon,etc) text color in calendar month view.
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
            Change the color day header (sun,mon,etc) background color in calendar month view.
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
            Change the color of week end(sunday & saturday month cell) background in calendar month view.
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
            Change the color of month layout(jan,feb,etc) background in calendar year view.
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
            Change the color of month layout header(jan,feb,etc) background in calendar year view.
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
            SfScheduleViewHeaderDateTextColor          
            <br/>
            <br/>
        </td>
        <td>
            Change the color of view header date text(10,11,etc) in calendar year view.
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
            Change the color of month header text(jan,feb,etc) in calendar year view.
            <br/>
            <br/>
        </td>
    </tr> 
</table>









