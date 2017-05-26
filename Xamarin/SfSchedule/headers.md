---     
layout: post     
title: Header appearance and customization in Syncfusion SfSchedule control for Xamarin.Forms     
description: Learn how to customize header in SfSchedule control 
platform: xamarin    
control: SfSchedule     
documentation: ug   
---  

# Header

You can customize the header of the Schedule using [HeaderStyle](http://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.HeaderStyle.html) and [HeaderHeight](http://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.SfSchedule~HeaderHeightProperty.html) property in schedule.

## Header Height

You can customize the height for the Header in Schedule using `HeaderHeight` in schedule.

{% tabs %} 
{% highlight xaml %}
        
    <syncfusion:SfSchedule x:Name="schedule" HeaderHeight="50" />

{% endhighlight %} 
{% highlight c# %}

	schedule.HeaderHeight = 50;

{% endhighlight %}
{% endtabs %} 

## Appearance

You can change the header format and style using `HeaderStyle` property in schedule.

You can change the background color,text style and text size using properties such as [BackgroundColor](http://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.HeaderStyle~BackgroundColorProperty.html),[TextStyle](http://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.HeaderStyle~TextStyleProperty.html),[TextColor](http://help.syncfusion.com/cr/cref_files/xamarin/sfschedule/Syncfusion.SfSchedule.XForms~Syncfusion.SfSchedule.XForms.HeaderStyle~TextColorProperty.html), of Header using `HeaderStyle` property in schedule.

{% tabs %} 
{% highlight xaml %}

    <syncfusion:SfSchedule x:Name="schedule" >
		<syncfusion:SfSchedule.HeaderStyle>
			<syncfusion:HeaderStyle
				BackgroundColor="#FADBD8" 
				TextColor="Blue" 
				TextStyle="20" />
		</syncfusion:SfSchedule.HeaderStyle>
	</syncfusion:SfSchedule>

{% endhighlight %}
{% highlight c# %}

	HeaderStyle headerStyle = new HeaderStyle();
	headerStyle.BackgroundColor = Color.FromRgb(250, 219, 216);
	headerStyle.TextStyle = Font.SystemFontOfSize(20);
	headerStyle.TextColor=Color.Blue;
	schedule.HeaderStyle = headerStyle;

{% endhighlight %}
{% endtabs %} 

![](Header_images/HeaderStyle.png) 

>**Note**:  FontAttributes and FontFamily are native to the  platform. Custom font and the font which are not available in the specified platform will not be applied.

## Loading Custom Headers

You can collapse the default header of schedule by setting `HeaderHeight` property of `SfSchedule` as 0. Instead you can use your own custom header for it. While navigating views in schedule, text labels available in the header will be changed based on it visible dates, so while using custom header , respective text value can be obtained from the `VisibleDatesChanged` event of `SfSchedule`.

{% highlight c# %}
    
    //triggering the visible dates changed event.
    schedule.VisibleDatesChangedEvent += Schedule_VisibleDatesChangedEvent;
    
    void Schedule_VisibleDatesChangedEvent(object sender, VisibleDatesChangedEventArgs args)
        {
            List<DateTime> datelist = new List<DateTime>();
            datelist = (args.visibleDates);
			var headerString = String.Empty;
            var item = datelist[0];
			if (Schedule.ScheduleView == ScheduleView.DayView)
			{
				item = datelist[0];
				headerString = item.Date.ToString("MMMM, yyyy");
			}
			else
			{
				item = datelist[datelist.Count / 2];
				headerString = item.Date.ToString("MMMM, yyyy");
			}
        }

{% endhighlight %}

You can get the complete sample for customizing the Header of Schedule [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Header_Sample-1251673941.zip) 