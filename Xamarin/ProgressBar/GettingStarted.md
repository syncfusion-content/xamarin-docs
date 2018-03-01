# Getting Started

This section explains the steps required to work with progress bar in Xamarin.Forms.

## Add progress bar reference

Refer to this article to know how to obtain and reference Essential Studio components in your solution; then refer to this link to know about the assemblies required for adding progress bar to your project.

I>After adding the reference, an additional step is required for iOS and UWP projects. You should create an instance of the progress bar renderer in iOS and UWP projects as shown in this [KB article](https://www.syncfusion.com/kb/8560/how-to-resolve-progress-bar-not-rendering-issue-in-ios-and-uwp).

I>For UWP alone, one more additional step is required if the project is built-in release mode with .NET Native tool chain enabled. You can refer to the [KB article](https://www.syncfusion.com/kb/8508/how-to-make-syncfusion-xamarin-forms-progress-bar-to-work-in-uwp-in-release-mode-when-net-native-tool) for more details.

## Initialize the progress bar

Import the progress bar namespace as shown in the following codes in your respective page,

{% tabs %} 

{% highlight xaml %} 
xmlns:progressBar="clr-namespace:Syncfusion.XForms.ProgressBar;assembly=Syncfusion.SfProgressBar.XForms"

{% endhighlight %}

{% highlight C# %} 

using Syncfusion.XForms.ProgressBar;

{% endhighlight %}

{% endtabs %} 

There are two variants of progress bar: SfLinearProgressBar and SfCircularProgressBar. Each render the progress in its own shape such as rectangle and circle respectively. Initialize both the progress bar with a progress value using Progress property as shown in the following code snippet.

N>By default, the value of progress should be specified between 0 and 100. If you need to specify progress value between 0 and 1, you should specify Minimum property to 0 and Maximum property to 1.

{% tabs %} 

{% highlight xaml %} 
<!--Using linear progress bar-->
<progressBar:SfLinearProgressBar Progress="75"/>

<!--Using circular progress bar-->
<progressBar:SfCircularProgressBar Progress="75"/>
{% endhighlight %}

{% highlight C# %} 

//// Using linear progress bar. 
SfLinearProgressBar linearProgressBar = new SfLinearProgressBar { Progress = 75 };

//// Using circular progress bar.
SfCircularProgressBar circularProgressBar = new SfCircularProgressBar { Progress = 75 };

{% endhighlight %}

{% endtabs %} 

Run the project, and check if you get following output to make sure that you have configured your project properly to add the progress bar.

![](overview_images/progressbar.png)


## Enable indeterminate state

When the progress of a task cannot be shown determinately, you can enable indeterminate state using IsIndeterminate property to let user know that some progress is happening in the background.

{% tabs %} 

{% highlight xaml %} 

<!--Using linear progress bar-->
<progressBar:SfLinearProgressBar IsIndeterminate="True"/>

<!--Using circular progress bar-->
<progressBar:SfCircularProgressBar IsIndeterminate="True"/>

{% endhighlight %}

{% highlight C# %} 

//// Using linear progress bar.
SfLinearProgressBar linearProgressBar = new SfLinearProgressBar { IsIndeterminate = true };

//// Using circular progress bar.
SfCircularProgressBar circularProgressBar = new SfCircularProgressBar { IsIndeterminate = true };
{% endhighlight %}

{% endtabs %} 

## Enable segments

To visualize the progress of a multiple sequential task, split the progress bar into the multiple segments by defining the **SegmentCount** property as shown in the following code.

{% tabs %} 

{% highlight xaml %} 
<!--Using linear progress bar-->
<progressBar:SfLinearProgressBar SegmentCount="4" Progress="75"/>

<!--Using circular progress bar-->
<progressBar:SfCircularProgressBar SegmentCount="4" Progress="75"/>
{% endhighlight %}

{% highlight C# %} 

//// Using linear progress bar.
SfLinearProgressBar linearProgressBar = new SfLinearProgressBar { Progress = 75, SegmentCount = 4 };

//// Using circular progress bar.
SfCircularProgressBar circularProgressBar = new SfCircularProgressBar { Progress = 75, SegmentCount = 4 };
{% endhighlight %}

{% endtabs %} 
![](overview_images/indeterminate.png)


## Apply colors

You can customize the color of the progress indicator and track by defining the **ProgressColor** and **TrackColor** properties respectively.

{% tabs %} 

{% highlight xaml %} 

<!--Using linear progress bar-->
<progressBar:SfLinearProgressBar Progress="75" TrackColor="#33ffbe06" ProgressColor="#FFffbe06"/>
<progressBar:SfLinearProgressBar Progress="75"  TrackColor="#3351483a" ProgressColor="#FF51483a"/>

<!--Using circular progress bar-->
 <progressBar:SfCircularProgressBar Progress="75" TrackColor="#33c15244" ProgressColor="#FFc15244"/>
<progressBar:SfCircularProgressBar Progress="75" TrackColor="#3390a84e" ProgressColor="#FF90a84e"/>
{% endhighlight %}

{% highlight C# %} 

//// Using linear progress bar.
SfLinearProgressBar linearProgressBar = new SfLinearProgressBar{Progress = 75,TrackColor = Color.FromHex("#33ffbe06"),ProgressColor = Color.FromHex("#FFffbe06")};
SfLinearProgressBar sfLinearProgressBar = new SfLinearProgressBar{Progress = 75,TrackColor = Color.FromHex("#3351483a"),ProgressColor = Color.FromHex("#FF51483a")};

//// Using circular progress bar.
SfCircularProgressBar circularProgressBar = new SfCircularProgressBar{Progress = 75,TrackColor = Color.FromHex("#33c15244"),ProgressColor = Color.FromHex("#FFc15244")};
SfCircularProgressBar sfCircularProgressBar = new SfCircularProgressBar{Progress = 75,TrackColor = Color.FromHex("#3390a84e"),ProgressColor = Color.FromHex("#FF90a84e")};
{% endhighlight %}

{% endtabs %} 
![](overview_images/style.png)


You can find the complete Getting Started sample from this [link](http://www.syncfusion.com/downloads/support/directtrac/general/ze/ProgressBar-929614915.zip).
