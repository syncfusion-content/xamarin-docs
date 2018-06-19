# Overview

# Getting Started

# States

Based on the progress estimation, you can configure the states of the progress bar.

Determinate: This is the default state. You can use it when the progress estimation is known.

1. Indeterminate: By enabling the __**IsIndeterminate**____**[**____**link**____**]**__ property, the state of the progress bar can be changed to indeterminate when progress cannot be estimated or is not being calculated. It can be combined with determinate mode to let users know that the app is estimating progress before actual progress starts.



{% highlight xml %}
<!--Using linear progress bar-->

<progressBar:SfLinearProgressBar IsIndeterminate="True"/>

<!--Using circular progress bar-->

<progressBar:SfCircularProgressBar IsIndeterminate="True"/>



{% endhighlight %}

{% highlight c# %}
// Using linear progress bar. 

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar { IsIndeterminate = true};

// Using circular progress bar.

SfCircularProgressBar circularProgressBar = new SfCircularProgressBar { IsIndeterminate = true };







{% endhighlight %}

2. Buffer: The secondary task’s progress can be defined by using the __**SecondaryProgress**__[link] property as shown in the following code example.

{% highlight xml %}
<progressBar:SfLinearProgressBar x:Name="LinearProgressBar" Progress="25" SecondaryProgress="75"/>





{% endhighlight %}

{% highlight c# %}
this.LinearProgressBar.Progress = 75;

this.LinearProgressBar.SecondaryProgress = 25;









{% endhighlight %}

![](Progress_images/Progress_img1.jpeg)


# Custom content

In the circular progress bar, you can add any view to the center using the __**Content**____**[**____**link**____**]**__ property. 

For example, you can include add, start, or pause button to control the progress; add an image that indicates the actual task in progress or add custom text that conveys how far the task is completed. 

The following code example shows how to the add custom text content.

{% highlight xml %}
<progressBar:SfCircularProgressBar x:Name="CustomContentCircularProgressBar"

Progress="23" HorizontalOptions="Center" >

<progressBar:SfCircularProgressBar.Content>

<Grid>

<Grid.RowDefinitions>

<RowDefinition Height="3*"/>

<RowDefinition Height="*"/>

</Grid.RowDefinitions>

<Label x:Name="CustomContentProgressBarLabel" Grid.Row="0"

TextColor="#007cee" Text="{Binding Progress,StringFormat='{0}%'} HorizontalTextAlignment="Center" VerticalTextAlignment="End">                        

</Label>

<Label Grid.Row="1" TextColor="#007cee" Text="used" VerticalOptions="Start" Margin="0,-5,0,0" HorizontalTextAlignment="Center" VerticalTextAlignment="Start">

</Label>

</Grid>

</progressBar:SfCircularProgressBar.Content>

</progressBar:SfCircularProgressBar>





{% endhighlight %}

{% highlight c# %}
SfCircularProgressBar circularProgressBar = new SfCircularProgressBar();

circularProgressBar.Progress = 23;

Grid grid = new Grid();

grid.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(3, GridUnitType.Star) });

grid.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(1, GridUnitType.Star) });

Label label = new Label();

label.BindingContext = circularProgressBar;

Binding binding = new Binding();

binding.Path = "Progress";

binding.StringFormat = "{0}%";

label.SetBinding(Label.TextProperty, binding);

label.HorizontalTextAlignment = TextAlignment.Center;

label.VerticalOptions = LayoutOptions.End;

label.FontSize = 10;

label.TextColor = Color.FromHex("007cee");

Grid.SetRow(label, 0);

grid.Children.Add(label);

Label textLabel = new Label();

textLabel.Text = "used";

textLabel.HorizontalTextAlignment = TextAlignment.Center;

textLabel.VerticalOptions = LayoutOptions.Start;

textLabel.FontSize = 10;

textLabel.TextColor = Color.FromHex("007cee");

Grid.SetRow(textLabel, 1);

grid.Children.Add(textLabel);

circularProgressBar.Content = grid;









{% endhighlight %}

![](Progress_images/Progress_img2.jpeg)


By default, the progress value will be displayed at the center. You can hide the label in the circular progress bar by setting the **ShowProgressValue**[link] property to false. 

# Segments

To visualize the progress of multiple sequential tasks, split the progress bar into multiple segments by setting the **SegmentsCount**[link] property, as shown in the following code example.

{% highlight xml %}
<!--Using linear progress bar-->

<progressBar:SfLinearProgressBar x:Name="LinearProgressBar" Progress="25" SegmentCount="4" />

<!--Using circular progress bar-->

<progressBar:SfCircularProgressBar x:Name="CircularProgressBar" Progress="25" SegmentCount="7" />



{% endhighlight %}

{% highlight c# %}
// Using linear progress bar.

this.LinearProgressBar.SegmentCount = 4;

// Using circular progress bar.

this.CircularProgressBar.SegmentCount = 7;









{% endhighlight %}

![](Progress_images/Progress_img3.jpeg)


**Gap** **customization******

****You can also customize the default spacing between the segments using the **GapWidth**[link] property, as shown in following code example.

{% highlight xml %}
<!--Using linear progress bar-->

<progressBar:SfLinearProgressBar x:Name="LinearProgressBar" Progress="25" SegmentCount="4" GapWidth="5" />

<!--Using circular progress bar-->

<progressBar:SfCircularProgressBar x:Name="CircularProgressBar" Progress="25" SegmentCount="7" GapWidth="10" />





{% endhighlight %}

{% highlight c# %}
// Using linear progress bar.

this.LinearProgressBar.GapWidth = 5;

// Using circular progress bar.

this.CircularProgressBar.GapWidth = 10;









{% endhighlight %}

![](Progress_images/Progress_img4.jpeg)


# Defining range

Range represents the entire span of the progress bar, and it can be defined using the **Minimum** **[****link****]** and **Maximum** **[****link****]** properties. The default value of range is 0 to 100.

The following code example explains how to customize the range as factor value to the progress bar. 

{% highlight xml %}
<!--Using linear progress bar-->

<progressBar:SfLinearProgressBar x:Name="LinearProgressBar" Minimum="0" Progress="0.5" Maximum="1"/>

<!--Using circular progress bar-->

<progressBar:SfCircularProgressBar x:Name="CircularProgressBar" Minimum="0" Progress="0.5" Maximum="1"/>



{% endhighlight %}

{% highlight c# %}
// Using linear progress bar.

this.LinearProgressBar.Minimum = 0;

this.LinearProgressBar.Maximum = 1;

this.LinearProgressBar.Progress = 0.5;

// Using circular progress bar.

this.CircularProgressBar.Minimum = 0;

this.CircularProgressBar.Maximum = 1;

this.CircularProgressBar.Progress = 0.5;







{% endhighlight %}

![](Progress_images/Progress_img5.jpeg)


# Appearance

## Angle

The appearance of the circular progress bar can be customized to semi-circle, arc, etc. The start and sweep angles can be customized using the **StartAngle**[link] and **EndAngle**[link] properties. 

The following code example explains how to change the appearance of the circular progress bar to semi-circle.

{% highlight xml %}
<progressBar:SfCircularProgressBar x:Name="CircularProgressBar" Progress="75" StartAngle="180" EndAngle="360" />



{% endhighlight %}

{% highlight c# %}
SfCircularProgressBar circularProgressBar = new SfCircularProgressBar();

circularProgressBar.Progress = 75;

circularProgressBar.StartAngle = 180;

circularProgressBar.EndAngle = 360;









{% endhighlight %}

![](Progress_images/Progress_img6.jpeg)


## Range colors

You can also visualize multiple ranges with different colors that are mapped to each range to enhance readability of progress.



The colors can be mapped to the specific ranges using the __**RangeColors**__[link] property in the linear progress bar. It holds a collection of __**RangeColor**__[link]. 

The following properties in RangeColor[link] are used to map the colors to range:

* Color[link]: Represents the color to the specified range.
* Start[link]: Represents the start range of the color.
* End[link]: Represents the end range of the color.
* IsGradient[link]: Represents whether the gradient effect is applied to the color.

The following code example shows mapping the solid color range in the linear progress bar.

{% highlight xml %}
[XAML]

<progressBar:SfLinearProgressBar Progress="100">

<progressBar:SfLinearProgressBar.RangeColors>

<progressBar:RangeColorCollection>

<progressBar:RangeColor Color="#00bdaf" Start="0" End="25"/>

<progressBar:RangeColor Color="#2f7ecc" Start="25" End="50"/>

<progressBar:RangeColor Color="#e9648e" Start="50" End="75"/>

<progressBar:RangeColor Color="#fbb78a" Start="75" End="100"/>

</progressBar:RangeColorCollection>

</progressBar:SfLinearProgressBar.RangeColors>

</progressBar:SfLinearProgressBar>

[C#]

SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();

linearProgressBar.Progress = 100;

linearProgressBar.RangeColors.Add(new RangeColor() { Color = Color.FromHex("00bdaf"), Start = 0, End = 25 });

linearProgressBar.RangeColors.Add(new RangeColor() { Color = Color.FromHex("2f7ecc"), Start = 25, End = 50 });

linearProgressBar.RangeColors.Add(new RangeColor() { Color = Color.FromHex("e9648e"), Start = 50, End = 75 });

linearProgressBar.RangeColors.Add(new RangeColor() { Color = Color.FromHex("fbb78a"), Start = 75, End = 100 });





{% endhighlight %}

![](Progress_images/Progress_img7.jpeg)


The following code example shows how to apply gradient transition effect to the range colors in the linear progress bar.

{% highlight xml %}
<progressBar:SfLinearProgressBar Progress="100" >

<progressBar:SfLinearProgressBar.RangeColors>

<progressBar:RangeColorCollection>

<progressBar:RangeColor IsGradient="True" Color="#88A0D9EF" Start="0" End="25"/>

<progressBar:RangeColor IsGradient="True" Color="#AA62C1E5" Start="25" End="50"/>

<progressBar:RangeColor IsGradient="True" Color="#DD20A7DB" Start="50" End="75"/>

<progressBar:RangeColor IsGradient="True" Color="#FF1C96C5" Start="75" End="100"/>

</progressBar:RangeColorCollection>

</progressBar:SfLinearProgressBar.RangeColors>





{% endhighlight %}

{% highlight c# %}
SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();

linearProgressBar.Progress = 100;

linearProgressBar.RangeColors.Add(

new RangeColor() { Color = Color.FromHex("88A0D9EF"), IsGradient = true, Start = 0 , End = 25 });

linearProgressBar.RangeColors.Add(

new RangeColor() { Color = Color.FromHex("AA62C1E5"), IsGradient = true, Start = 25, End = 50 });

linearProgressBar.RangeColors.Add(

new RangeColor() { Color = Color.FromHex("DD20A7DB"), IsGradient = true, Start = 50, End = 75 });

linearProgressBar.RangeColors.Add(

new RangeColor() { Color = Color.FromHex("FF1C96C5"), IsGradient = true, Start = 75, End = 100 });









{% endhighlight %}

![](Progress_images/Progress_img8.jpeg)


## Thickness

**Linear** **progress** **bar******

****__**In**__ the linear progress bar, the height of the track and padding of the progress indicator can be customized using the __**TrackHeight**__[link] and __**Padding**__[link] properties, respectively.

{% highlight xml %}
<progressBar:SfLinearProgressBar Progress="100" TrackHeight="10" Padding="2">

</progressBar:SfLinearProgressBar>



{% endhighlight %}

{% highlight c# %}
SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();

linearProgressBar.Progress = 100;

linearProgressBar.TrackHeight = 10;

linearProgressBar.Padding = 2;









{% endhighlight %}

![](Progress_images/Progress_img9.jpeg)


**Circular** **progress** **bar******

****The following properties are used to customize the appearance of the circular progress bar:

* **IndicatorOuterRadius****[**link**]:** Defines the outer radius of the progress indicator.
* **IndicatorInnerRadius** [link]: Defines the inner radius of the progress indicator.
* **TrackOuterRadius** [link]: Defines the outer radius of the track indicator.
* **TrackInnerRadius** [link]: Defines the inner radius of the track indicator.

The following code example shows how to customize the appearance of circular progress bar.

{% highlight xml %}
<!--Circular progress bar with radius customization -->

<progressBar:SfCircularProgressBar x:Name="TrackOutsideProgressBar"

Grid.Column="0"

Grid.Row="0"

Progress="75"

Margin="0,10,0,0"

IndicatorOuterRadius="0.7"

IndicatorInnerRadius="0.65"

ShowProgressValue="False">

</progressBar:SfCircularProgressBar>       





{% endhighlight %}

{% highlight c# %}
SfCircularProgressBar trackOutsideProgressBar = new SfCircularProgressBar();

trackOutsideProgressBar.Progress = 75;

trackOutsideProgressBar.IndicatorOuterRadius = 0.7;

trackOutsideProgressBar.IndicatorInnerRadius = 0.65;

trackOutsideProgressBar.ShowProgressValue = false;







{% endhighlight %}

![](Progress_images/Progress_img10.jpeg)


## Corner radius

The **CornerRadius** property [link] is used to customize the rounded edges in the linear progress bar, as shown in the following code example.

{% highlight xml %}
<progressBar:SfLinearProgressBar Progress="50 TrackHeight="10" CornerRadius="10">

</progressBar:SfLinearProgressBar>



{% endhighlight %}

{% highlight c# %}
SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();

linearProgressBar.Progress = 50;

linearProgressBar.CornerRadius = 10;









{% endhighlight %}

![](Progress_images/Progress_img11.jpeg)


## Color customization

The following properties are used to customize the color in the progress bar:

* **ProgressColor**[link]: Represents the color of the progress indicator.
* **TrackColor**[link]: Represents the color of the track indicator.

The following code example shows the color customization in progress and track indicator.

{% highlight xml %}
<progressBar:SfLinearProgressBar Progress="75" TrackColor="#3351483a" ProgressColor="#FF51483a">

</progressBar:SfLinearProgressBar>



{% endhighlight %}

{% highlight c# %}
SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();

linearProgressBar.Progress = 75;

linearProgressBar.ProgressColor = Color.FromHex("FF51483a");

linearProgressBar.TrackColor = Color.FromHex("3351483a");









{% endhighlight %}

![](Progress_images/Progress_img12.jpeg)


The linear progress bar provides support to customize the color for the secondary progress bar using the **SecondaryProgressColor**[link] property, as shown in the following code example.

{% highlight xml %}
<progressBar:SfLinearProgressBar Progress="25" SecondaryProgress="75" SecondaryProgressColor="CornflowerBlue"></progressBar:SfLinearProgressBar>



{% endhighlight %}

{% highlight c# %}
SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();

linearProgressBar.Progress = 25;

linearProgressBar.SecondaryProgress = 75;

linearProgressBar.SecondaryProgressColor = Color.CornflowerBlue;







{% endhighlight %}

![](Progress_images/Progress_img13.jpeg)


## Animation

The progress bar provides animation support to visualize the progress value changes in an interactive way. 

The following properties are used to define the duration for animation for the specific states:

* **AnimationDuration** [link]: Represents animation duration of the determinate state’s progress indicator.
* **SecondaryAnimationDuration**[link]: Represents animation duration of the determinate state’s secondary progress indicator.
* **IndeterminateAnimationDuration**[link]: Represents animation duration of the indeterminate state’s indicator.

******Easing** **effects******

****The **EasingEffects**[link] property allows you specify the transfer function that controls animation speed while they are running. 

The following code example shows the **CubicInOut****[****link****]** easing function in the circular progress bar.

{% highlight xml %}
<progressBar:SfLinearProgressBar Progress="75" EasingEffect="CubicInOut">

</progressBar:SfLinearProgressBar>





{% endhighlight %}

{% highlight c# %}
SfLinearProgressBar linearProgressBar = new SfLinearProgressBar();

linearProgressBar.Progress = 75;

linearProgressBar.EasingEffect = EasingEffects.CubicInOut;







{% endhighlight %}

<gif image>

The **SetProgress****()** method[link] in the progress bar is used to set progress value along with animation duration and easing effect applicable for the specific method call. 

[C#]

void SetProgress(double progress, int animationDuration, Easing easingEffect)

Note: The animationDuration and easingEffect parameters will not affect the configuration of the **AnimationDuration**[link] and **EasingEffects**[link] properties.

## Events

**ValueChanged******

****This event is triggered when the progress value is changed. This event contains the following event argument.

* Progress[link]: Represents the progress value.

The following code example shows how to customize the color of a progress indicator based on progress using this event. 

{% highlight xml %}
<progressBar:SfLinearProgressBar Progress="100" x:Name="LinearProgressBar" ValueChanged="ProgressBarBase_OnValueChanged">

</progressBar:SfLinearProgressBar>



{% endhighlight %}

{% highlight c# %}
private void ProgressBarBase_OnValueChanged(object sender, ProgressValueEventArgs e)

{

if (e.Progress < 50)

{

this.LinearProgressBar.ProgressColor = Color.Red;

}

else if (e.Progress >= 50)

{

this.LinearProgressBar.ProgressColor = Color.Green;

}

}







{% endhighlight %}

******ProgressCompleted******

****This event is triggered when the progress attains the Maximum[link] value. This event contains the following argument.

* Progress [link]:  Represents the progress value.

The following code example shows how to customize the progress bar when progress reaches maximum using this event. 

{% highlight xml %}
<progressBar:SfCircularProgressBar x:Name="CircularProgressBar" Minimum="100" Maximum="500" Progress="500" ProgressCompleted="ProgressBarBase_OnProgressCompleted" >

<progressBar:SfCircularProgressBar.Content>

<Label Text="Start" FontSize="15" x:Name="Label"></Label>

</progressBar:SfCircularProgressBar.Content>

</progressBar:SfCircularProgressBar>



{% endhighlight %}

{% highlight c# %}
private void ProgressBarBase_OnProgressCompleted(object sender, ProgressValueEventArgs e)

{

if (e.Progress.Equals(this.CircularProgressBar.Maximum))

{

// Changed the label text when progress reaches maximum value.

this.Label.Text = "Completed";

}

}







{% endhighlight %}

