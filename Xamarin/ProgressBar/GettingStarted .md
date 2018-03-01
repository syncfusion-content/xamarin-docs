# Getting Started

This section explains the steps required to work with progress bar in Xamarin.Forms.

## Add progress bar reference

Refer to this article to know how to obtain and reference Essential Studio components in your solution; then refer to this link to know about the assemblies required for adding progress bar to your project.

I>After adding the reference, an additional step is required for iOS and UWP projects. You should create an instance of the progress bar renderer in iOS and UWP projects as shown in this [KB article.]()

I>For UWP alone, one more additional step is required if the project is built-in release mode with .NET Native tool chain enabled. You can refer to the [KB article]() for more details.

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

![](overview_images/overview_img1.jpeg)


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
![](overview_images/overview_img2.jpeg)


## Apply colors

You can customize the color of the progress indicator and track by defining the **ProgressColor** and **TrackColor** properties respectively.

{% tabs %} 

{% highlight xaml %} 

<!--Using linear progress bar-->
<progressBar:SfLinearProgressBar Progress="75" TrackColor="Gray" ProgressColor="#00bdaf"/>
<progressBar:SfLinearProgressBar Progress="75" ProgressColor="#e9648e"/>

<!--Using circular progress bar-->
<progressBar:SfCircularProgressBar Progress="75" TrackColor="Gray" ProgressColor="#00bdaf"/>
<progressBar:SfCircularProgressBar Progress="75" ProgressColor="#e9648e"/>
{% endhighlight %}

{% highlight C# %} 

//// Using linear progress bar.
SfLinearProgressBar linearProgressBar = new SfLinearProgressBar{Progress = 75,TrackColor = Color.Gray,ProgressColor = Color.FromHex("#00bdaf")};
SfLinearProgressBar sfLinearProgressBar = new SfLinearProgressBar{Progress = 75,ProgressColor = Color.FromHex("#e9648e")};

//// Using circular progress bar.
SfCircularProgressBar circularProgressBar = new SfCircularProgressBar{Progress = 75,TrackColor = Color.Gray,ProgressColor = Color.FromHex("#00bdaf")};
SfCircularProgressBar sfCircularProgressBar = new SfCircularProgressBar{Progress = 75,ProgressColor = Color.FromHex("#e9648e")};
{% endhighlight %}

{% endtabs %} 
![](overview_images/overview_img3.jpeg)


