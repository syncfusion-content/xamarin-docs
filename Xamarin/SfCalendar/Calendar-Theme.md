---
layout: post
title: Add theming support in syncfusion calendar control
description: Learn how to add the theme.
platform: Xamarin
control: Calendar
documentation: ug
---

# Theming

Theming is a set of resources which are used to provide the consistency look for calendar.
You can modify the default appearance of calendar using this support. By default calendar have default theme resources and it’s located in `Syncfusion.Xamarin.Core` assembly. You need to merge them in your application’s resource to apply the theme.

In the below code you can see the default color and key value for the default resources.

{% tabs %}
{% highlight xaml %}
<Color x:Key="SfCalendarInlineTextColor">#414141</Color>
<Color x:Key="SfCalendarBlackoutColor">#C2C2C2</Color>
<Color x:Key="SfCalendarDateSelectionColor">#F5F5F5</Color>
<Color x:Key="SfCalendarInlineBackgroundColor">#F5F5F5</Color>
<Color x:Key="SfCalendarSelectedDayTextColor">#FFFFFF</Color>
<Color x:Key="SfCalendarBorderColor">#F0F0F0</Color>
<Color x:Key="SfCalendarWeekDayBackgroundColor">#FFFFFF</Color>
<Color x:Key="SfCalendarWeekDayTextColor">#707070</Color>
<Color x:Key="SfCalendarDisabledBackgroundColor">#FFFFFF</Color>
<Color x:Key="SfCalendarDisabledTextColor">#C2C2C2</Color>
<Color x:Key="SfCalendarPreviousMonthBackgroundColor">#FFFFFF</Color>
<Color x:Key="SfCalendarPreviousMonthTextColor">#C2C2C2</Color>
<Color x:Key="SfCalendarCurrentMonthBackgroundColor">#FFFFFF</Color>
<Color x:Key="SfCalendarCurrentMonthTextColor">#414141</Color>
<Color x:Key="SfCalendarWeekEndTextColor">#707070</Color>
<Color x:Key="SfCalendarDayHeaderTextColor">#707070</Color>
<Color x:Key="SfCalendarDayHeaderBackgroundColor">#FFFFFF</Color>
<Color x:Key="SfCalendarWeekEndBackgroundColor">#C2C2C2</Color>
<Color x:Key="SfCalendarHeaderBackgroundColor">#FFFFFF</Color>
<Color x:Key="SfCalendarHeaderTextColor">#707070</Color>
<Color x:Key="SfCalendarYearViewLayoutBackground">#FFFFFF</Color>
<Color x:Key="SfCalendarYearViewHeaderBackground">#FFFFFF</Color>
<Color x:Key="SfCalendarYearViewMonthLayoutBackground">#FFFFFF</Color>
<Color x:Key="SfCalendarYearViewMonthHeaderBackground">#FFFFFF</Color>
<Color x:Key="SfCalendarYearViewDateTextColor">#414141</Color>
<Color x:Key="SfCalendarYearViewHeaderTextColor">#707070</Color>
<Color x:Key="SfCalendarAgendaSelectedDateColor">#FFFFFF</Color>
{% endhighlight %}
{% endtabs %} 

You can apply the default theme (light theme) or customized theme to calendar.

## Default theme (light theme)

You need to apply the syncfusion theme dictionaries in your application to view the default theme (light theme).

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" xmlns:local="clr-namespace:CalendarSample" x:Class="CalendarSample.MainPage" xmlns:syncfusion="clr-namespace:Syncfusion.SfCalendar.XForms;assembly=Syncfusion.SfCalendar.XForms" xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms">
    <ContentPage.Resources>
        <syncTheme:SyncfusionThemeDictionary>
            <syncTheme:SyncfusionThemeDictionary.MergedDictionaries>
                <syncTheme:LightTheme x:Name="LightTheme" />
            </syncTheme:SyncfusionThemeDictionary.MergedDictionaries>
        </syncTheme:SyncfusionThemeDictionary>
    </ContentPage.Resources>
    <syncfusion:SfCalendar x:Name="calendar" ViewMode="MonthView" ShowInlineEvents="true" InlineViewMode="Inline" />
</ContentPage>
{% endhighlight %}
{% endtabs %} 

Month view

![SfCalendar themes](images/xamarin.forms-calendar-monthdefaulttheme.png)

Year view

![SfCalendar themes](images/xamarin.forms-calendar-yeardefaultcustom.png)

## Customizing the default theme

You can customize the default theme by overriding the existing key and set the new value.

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" xmlns:local="clr-namespace:CalendarSample" x:Class="CalendarSample.MainPage" xmlns:syncfusion="clr-namespace:Syncfusion.SfCalendar.XForms;assembly=Syncfusion.SfCalendar.XForms" xmlns:syncTheme="clr-namespace:Syncfusion.XForms.Themes;assembly=Syncfusion.Core.XForms">
    <ContentPage.Resources>
        <ResourceDictionary>
            <ResourceDictionary.MergedDictionaries>
                <syncTheme:LightTheme />
                <syncfusion:SfCalendarStyles />
                <ResourceDictionary>
                    <Color x:Key="SfCalendarInlineBackgroundColor">Green</Color>
                    <Color x:Key="SfCalendarInlineTextColor">White</Color>
                    <Color x:Key="SfCalendarWeekEndBackgroundColor">Blue</Color>
                    <Color x:Key="SfCalendarYearViewHeaderTextColor">Blue</Color>
                    <Color x:Key="SfCalendarYearViewDateTextColor">Green</Color>
                </ResourceDictionary>
            </ResourceDictionary.MergedDictionaries>
        </ResourceDictionary>
    </ContentPage.Resources>
    <syncfusion:SfCalendar x:Name="calendar" ViewMode="MonthView" ShowInlineEvents="true" InlineViewMode="Inline" />
</ContentPage>
{% endhighlight %}
{% endtabs %} 

>**NOTE**
`Xamarin.Forms` version should be above 3 while customize the default theme.

Month view

![SfCalendar themes](images/xamarin.forms-calendar-monthcustomizationdefaulttheme.png)

Year view

![SfCalendar themes](images/xamarin.forms-calendar-yearcustometheme.png)

You can download the entire source code of this demo for Xamarin.Forms from
here [CalendarTheme](https://github.com/SyncfusionExamples/xamarin-calendar-theming).