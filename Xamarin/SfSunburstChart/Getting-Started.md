---
layout: post
title: Getting Started for Essential Xamarin.Forms SfSunburstChart
description: This section explains the steps required to populate the sunburst chart with data, data labels, legends and title.
platform: xamarin
control: SfSunburstChart
documentation: ug
---

# Getting Started

This section explains you the steps required to populate the sunburst chart with data, data labels, legends and title. This section covers only the minimal features that you need to know to get started with the sunburst chart. 

## Adding SunburstChart Reference

Refer this [article](https://help.syncfusion.com/xamarin/introduction/download-and-installation) to know how to obtain and reference Essential Studio components in your solution; then refer [this](https://help.syncfusion.com/xamarin/introduction/control-dependencies#sfsunburstchart) link to know about the assemblies required for adding SfSunburstChart to your project.

I> After adding the reference, currently, an additional step is required for iOS and UWP projects. We need to call Init method in the `SfSunburstChartRenderer` as shown in this [KB article.](http://www.syncfusion.com/support/kb/7714)

I> For UWP alone, one more additional step is required if the project is built in release mode with .NET Native tool chain enabled. You can refer the [KB article](http://www.syncfusion.com/support/kb/7715) for more details.

## Initialize SunburstChart

Import the [`SfSunburstChart`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSunburstChart.XForms~Syncfusion.SfSunburstChart.XForms.SfSunburstChart.html) namespace as shown below in your respective page,

{% tabs %} 

{% highlight xaml %} 

xmlns:sunburst="clr-namespace:Syncfusion.SfSunburstChart.XForms;assembly=Syncfusion.SfSunburstChart.XForms" 

{% endhighlight %}

{% highlight C# %} 

using Syncfusion.SfSunburstChart.XForms;

{% endhighlight %}

{% endtabs %} 

Then initialize an empty sunburst chart as shown below,

{% tabs %} 

{% highlight xaml %} 
<sunburst:SfSunburstChart>
    
</sunburst:SfSunburstChart>
{% endhighlight %}

{% highlight C# %} 
SfSunburstChart sunburst = new SfSunburstChart();

this.Content = sunburst;
{% endhighlight %}

{% endtabs %} 

## Initialize view model

In this section, the data in the following table is used for demonstration,

<table>
<tr>
<th>
Country
</th>
<th>
Job Description
</th>
<th>
Job Group
</th>
<th>
Job Role
</th>
<th>
Employees Count
</th>
</tr>
<tr>
<td>
America
</td>
<td>
Sales
</td>
<td>
</td>
<td>
</td>
<td>
70
</td>
</tr>
<tr>
<td>
America
</td>
<td>
Technical
</td>
<td>
Testers
</td>
<td>
</td>
<td>
35
</td>
</tr>
<tr>
<td>
America
</td>
<td>
Technical
</td>
<td>
Developers
</td>
<td>
Windows
</td>
<td>
105
</td>
</tr>
<tr>
<td>
America
</td>
<td>
Technical
</td>
<td>
Developers
</td>
<td>
Web
</td>
<td>
40
</td>
</tr>
<tr>
<td>
America
</td>
<td>
Management
</td>
<td>
</td>
<td>
</td>
<td>
40
</td>
</tr>
<tr>
<td>
America
</td>
<td>
Accounts
</td>
<td>
</td>
<td>
</td>
<td>
60
</td>
</tr>
<tr>
<td>
India
</td>
<td>
Technical
</td>
<td>
Testers
</td>
<td>
</td>
<td>
25
</td>
</tr>
<tr>
<td>
India
</td>
<td>
Technical
</td>
<td>
Developers
</td>
<td>
Windows
</td>
<td>
155
</td>
</tr>
<tr>
<td>
India
</td>
<td>
Technical
</td>
<td>
Developers
</td>
<td>
Web
</td>
<td>
60
</td>
</tr>
<tr>
<td>
Germany
</td>
<td>
Sales
</td>
<td>
Executive
</td>
<td>
</td>
<td>
30
</td>
</tr>
<tr>
<td>
Germany
</td>
<td>
Sales
</td>
<td>
Analyst
</td>
<td>
</td>
<td>
40
</td>
</tr>
<tr>
<td>
UK
</td>
<td>
Technical
</td>
<td>
Developers
</td>
<td>
Windows
</td>
<td>
100
</td>
</tr>
<tr>
<td>
UK
</td>
<td>
Technical
</td>
<td>
Developers
</td>
<td>
Web
</td>
<td>
30
</td>
</tr>
<tr>
<td>
UK
</td>
<td>
HR Executives
</td>
<td>
</td>
<td>
</td>
<td>
60
</td>
</tr>
<tr>
<td>
UK
</td>
<td>
Marketing
</td>
<td>
</td>
<td>
</td>
<td>
40
</td>
</tr>
</table>

Now, let us define a data model that represents the above data in [`SfSunburstChart`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSunburstChart.XForms~Syncfusion.SfSunburstChart.XForms.SfSunburstChart.html).

{% highlight c# %}
public class Model   
{   
    public string Category { get; set; }
    public string Country { get; set; }
    public string JobDescription { get; set; }
    public string JobGroup { get; set; }
    public string JobRole { get; set; }
    public double EmployeesCount { get; set; }
}
{% endhighlight %} 

Next, create a view model class and initialize a list of `Model` objects as shown below,

{% highlight c# %}
public class ViewModel
{
    public ObservableCollection<Model> Data { get; set; }
    public ViewModel()
    {
        Data = new ObservableCollection<Model>
        {
            new Model
            {
                Country = "America", JobDescription = "Sales",
                EmployeesCount = 70
            },
            new Model
            {
                Country = "America", JobDescription = "Technical",
                JobGroup = "Testers", EmployeesCount = 35
            },
            new Model
            {
                Country = "America", JobDescription = "Technical",
                JobGroup = "Developers", JobRole = "Windows", EmployeesCount = 105
            },
            new Model
            {
                Country = "America", JobDescription = "Technical",
                JobGroup = "Developers", JobRole = "Web", EmployeesCount = 40
            },
            new Model
            {
                Country = "America", JobDescription = "Management",
                EmployeesCount = 40
            },
            new Model
            {
                Country = "America", JobDescription = "Accounts",
                EmployeesCount = 60
            },
            new Model
            {
                Country = "India", JobDescription = "Technical",
                JobGroup = "Testers", EmployeesCount = 25
            },
            new Model
            {
                Country = "India", JobDescription = "Technical", JobGroup = "Developers",
            JobRole = "Windows", EmployeesCount = 155
            },
            new Model
            {
                Country = "India", JobDescription = "Technical", JobGroup = "Developers",
                JobRole = "Web", EmployeesCount = 60
            },
            new Model
            {
                Country = "Germany", JobDescription = "Sales", JobGroup = "Executive",
                EmployeesCount = 30
            },
            new Model
            {
                Country = "Germany", JobDescription = "Sales", JobGroup = "Analyst",
                EmployeesCount = 40
            },
            new Model
            {
                Country = "UK", JobDescription = "Technical", JobGroup = "Developers",
                JobRole = "Windows", EmployeesCount = 100
            },
            new Model
            {
                Country = "UK", JobDescription = "Technical", JobGroup = "Developers",
                JobRole = "Web", EmployeesCount = 30
            },
            new Model
            {
                Country = "UK", JobDescription = "HR Executives", EmployeesCount = 60
            },
            new Model
            {
                Country = "UK", JobDescription = "Marketing", EmployeesCount = 40
            }
        };
    }
}

{% endhighlight %} 

Set the `ViewModel` instance as the `BindingContext` of your Page; this is done to bind properties of `ViewModel` to [`SfSunburstChart`.](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSunburstChart.XForms~Syncfusion.SfSunburstChart.XForms.SfSunburstChart.html)
 
N> Add namespace of `ViewModel` class in your XAML page if you prefer to set `BindingContext` in XAML.

{% tabs %} 

{% highlight xaml %} 
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"

             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"

            x:Class="Sunburst.SunburstPage"

            xmlns:sunburst="clr-namespace:Syncfusion.SfSunburstChart.XForms;assembly=Syncfusion.SfSunburstChart.XForms"

            xmlns:local="clr-namespace:Sunburst">    

	<ContentPage.BindingContext>       

		<local:ViewModel></local:ViewModel>  

	</ContentPage.BindingContext>
 
</ContentPage>
{% endhighlight %}

{% highlight C# %} 
this.BindingContext = new ViewModel();
{% endhighlight %}

{% endtabs %} 

## Populate SunburstChart with data

Now, bind the Data property of the above ViewModel to the [`ItemsSource`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSunburstChart.XForms~Syncfusion.SfSunburstChart.XForms.SfSunburstChart~ItemsSource.html) property. 
Add [`SunburstHierarchicalLevel`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSunburstChart.XForms~Syncfusion.SfSunburstChart.XForms.SunburstHierarchicalLevel.html) to [`Levels`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSunburstChart.XForms~Syncfusion.SfSunburstChart.XForms.SfSunburstChart~Levels.html) property. Each hierarchy level is formed based on the property specified in [`GroupMemberPath`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSunburstChart.XForms~Syncfusion.SfSunburstChart.XForms.SunburstHierarchicalLevel~GroupMemberPath.html) property, and each arc segment size is calculated using [`ValueMemberPath`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSunburstChart.XForms~Syncfusion.SfSunburstChart.XForms.SfSunburstChart~ValueMemberPath.html).

{% tabs %}   

{% highlight xaml %}
<sunburst:SfSunburstChart ItemsSource="{Binding Data}" ValueMemberPath="EmployeesCount">
    <sunburst:SfSunburstChart.Levels>
        <sunburst:SunburstHierarchicalLevel GroupMemberPath="Country"/>
        <sunburst:SunburstHierarchicalLevel GroupMemberPath="JobDescription"/>
        <sunburst:SunburstHierarchicalLevel GroupMemberPath="JobGroup"/>
        <sunburst:SunburstHierarchicalLevel GroupMemberPath="JobRole"/>
    </sunburst:SfSunburstChart.Levels>
</sunburst:SfSunburstChart>
{% endhighlight %}

{% highlight C# %}
SfSunburstChart sunburst = new SfSunburstChart();
sunburst.ValueMemberPath = "EmployeesCount";
sunburst.SetBinding(SfSunburstChart.ItemsSourceProperty, "Data");
sunburst.Levels.Add(new SunburstHierarchicalLevel() {GroupMemberPath = "Country"});
sunburst.Levels.Add(new SunburstHierarchicalLevel() {GroupMemberPath = "JobDescription"});
sunburst.Levels.Add(new SunburstHierarchicalLevel() {GroupMemberPath = "JobGroup"});
sunburst.Levels.Add(new SunburstHierarchicalLevel() {GroupMemberPath = "JobRole"});
{% endhighlight %}

{% endtabs %}

## Add Title

You can add title to sunburst chart to provide quick information to the user about the data being plotted in the chart. You can set title using [`SfSunburstChart.Title`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSunburstChart.XForms~Syncfusion.SfSunburstChart.XForms.SfSunburstChart~Title.html) property as shown below.

{% tabs %} 

{% highlight xaml %}
<sunburst:SfSunburstChart>

    ...

    <sunburst:SfSunburstChart.Title>
        <sunburst:SunburstChartTitle Text="Employees Count"/>
    </sunburst:SfSunburstChart.Title>

    ...

</sunburst:SfSunburstChart >
{% endhighlight %}

{% highlight C# %} 
sunburst.Title=new SunburstChartTitle();
sunburst.Title.Text = "Employees Count";
{% endhighlight %}

{% endtabs %}

## Add legend

You can enable legend using [`SfSunburstChart.Legend`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSunburstChart.XForms~Syncfusion.SfSunburstChart.XForms.SfSunburstChart~Legend.html) property as shown below,

{% tabs %} 

{% highlight xaml %}
<sunburst:SfSunburstChart>

    ...
    
    <sunburst:SfSunburstChart.Legend>
        <sunburst:SunburstChartLegend/>
    </sunburst:SfSunburstChart.Legend>

    ...

</sunburst:SfSunburstChart>
{% endhighlight %}

{% highlight C# %} 
sunburst.Legend = new SunburstChartLegend (); 
{% endhighlight %}

{% endtabs %} 

## Add data labels

You can add data labels to improve the readability of the sunburst chart. This can be achieved using [`SfSunburstChart.DataLabel`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfSunburstChart.XForms~Syncfusion.SfSunburstChart.XForms.SfSunburstChart~DataLabel.html) property as shown below.

{% tabs %} 

{% highlight xaml %}
<sunburst:SfSunburstChart>

    ...

    <sunburst:SfSunburstChart.DataLabel>
        <sunburst:SunburstChartDataLabel/>
	</sunburst:SfSunburstChart.DataLabel>

    ...

</sunburst:SfSunburstChart>
{% endhighlight %}

{% highlight C# %} 
sunburst.DataLabel = new SunburstChartDataLabel();
{% endhighlight %}

{% endtabs %} 


Following is the final output screenshot,

![SfSunburstChart with data label and legend](Getting-Started_images/gettingstarted.png)

You can find the complete getting started sample from this [`link`](http://files2.syncfusion.com/Xamarin.Forms/Samples/SunburstChart_GettingStarted.zip).

