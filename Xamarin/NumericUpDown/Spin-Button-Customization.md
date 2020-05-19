---
layout: post
title: Appearance and styling in Syncfusion NumericUpDown  for Xamarin.Forms
description: Learn spin buttons position customization, UpDownButtonSetting customization and Spin button validation customization in NumericUpDown.
platform: Xamarin
control: NumericUpDown
documentation: ug
---

# Spin Button Alignment

Spin Button position in the SfNumericUpDown control can be changed relative to the TextBox based on `SpinButtonAlignment` property. 

There are three built-in modes.

### Right

Spin Buttons will get aligned to the right side of the control.

{% tabs %}

{% highlight C# %}

	numericUpDown.SpinButtonAlignment = SpinButtonAlignment.Right;

{% endhighlight %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" SpinButtonAlignment="Right"/>
	
{% endhighlight %}

{% endtabs %}


![Display SfNumericUpDown control with SpinButtonAlignment right](images/right.png)

### Left

Spin Buttons will get aligned to the left side of the control.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" SpinButtonAlignment="Left"/>
	
{% endhighlight %}

{% highlight C# %}

	numericUpDown.SpinButtonAlignment = SpinButtonAlignment.Left;

{% endhighlight %}

{% endtabs %}


![Display SfNumericUpDown control with SpinButtonAlignment left](images/left.png)

### Both

Spin Buttons will get aligned to the both side of the control.

{% tabs %}

{% highlight xaml %}

	<numeric:SfNumericUpDown x:Name="numericUpDown" SpinButtonAlignment="Both"/>
	
{% endhighlight %}

{% highlight C# %}

	numericUpDown.SpinButtonAlignment = SpinButtonAlignment.Both;

{% endhighlight %}

{% endtabs %}


![Display SfNumericUpDown control with SpinButtonAlignment center](images/both.png)

N> By default the property value is Right.

## UpDownButtonSetting Customization

We can set the Up Down button of SfNumericUpDown control by using any of the below given ways.

1. View
2. Image
3. FontIconText

N> For image and Font icon we need to add the the respective image and TTF file.
		For android: Add image at Resource/Drawable/{Image} and .ttf file at Asserts/{.ttf}
		For iOS: Add image and .ttf file to Resource/{Image/.ttf} and To use FontIcons, add respective FontFamily name in info.plist file under Fonts provided by application category.
		For UWP: Add the image and .ttf file directly to the project.

### By using View


{% tabs %}

{% highlight xaml %}


<updown:SfNumericUpDown x:Name="upDown" SpinButtonAlignment="Both" TextAlignment="Center">
<updown:SfNumericUpDown.IncrementButtonSettings>
<updown:UpDownButtonSettings ButtonHeight="45" ButtonWidth="45">
<updown:UpDownButtonSettings.ButtonView>
<Grid HeightRequest="40" WidthRequest="40">
<Image Source="up.png" Aspect="AspectFit" />
</Grid>
</updown:UpDownButtonSettings.ButtonView>
</updown:UpDownButtonSettings>
</updown:SfNumericUpDown.IncrementButtonSettings>
<updown:SfNumericUpDown.DecrementButtonSettings>
<updown:UpDownButtonSettings ButtonHeight="45" ButtonWidth="45">
<updown:UpDownButtonSettings.ButtonView>
<Grid HeightRequest="40" WidthRequest="40">
<Image Source="down.png" Aspect="AspectFit" />
</Grid>
</updown:UpDownButtonSettings.ButtonView>
</updown:UpDownButtonSettings>
</updown:SfNumericUpDown.DecrementButtonSettings>
</updown:SfNumericUpDown>

{% endhighlight %}

{% highlight C# %}

 public partial class MainPage : ContentPage
    {
        SfNumericUpDown upDown;
        Grid incrementGrid, decrementGrid;
        UpDownButtonSettings incSettings, decrementSettings;
        Image incrementImage, decrementImage;
        public MainPage()
        {
            InitializeComponent();
            incrementGrid = new Grid
            {
                HeightRequest = 40,
                WidthRequest = 40,
                BackgroundColor = Color.Blue
            };
            incSettings = new UpDownButtonSettings
            {
                ButtonView = incrementGrid,
                ButtonHeight = 45,
                ButtonWidth = 45
            };
            incrementImage = new Image
            {
                HorizontalOptions = LayoutOptions.Center,
                VerticalOptions = LayoutOptions.Center,
                Source = (FileImageSource)ImageSource.FromFile("up.png"),
                Aspect = Aspect.AspectFit
            };
            decrementSettings = new UpDownButtonSettings
            {
                ButtonView = decrementGrid,
                ButtonHeight = 45,
                ButtonWidth = 45
            };
            decrementGrid = new Grid
            {
                HeightRequest = 40,
                WidthRequest = 40,
                BackgroundColor = Color.Red

            };
            decrementImage = new Image
            {
                Source = (FileImageSource)ImageSource.FromFile("down.png"),
                Aspect = Aspect.AspectFit,
                HorizontalOptions = LayoutOptions.Center,
                VerticalOptions = LayoutOptions.Center
            };
            upDown = new SfNumericUpDown
            {
                SpinButtonAlignment = SpinButtonAlignment.Left,
                IncrementButtonSettings = incSettings,
                DecrementButtonSettings = decrementSettings
            };
            incrementGrid.Children.Add(incrementImage);
            decrementGrid.Children.Add(decrementImage);
            this.Content = upDown;
        }
        
    }


{% endhighlight %}

{% endtabs %}

### By using Image with Button Height & Width

{% tabs %}

{% highlight xaml %}


<updown:SfNumericUpDown x:Name="upDown" SpinButtonAlignment="Both" TextAlignment="Center">
<updown:SfNumericUpDown.IncrementButtonSettings>
<updown:UpDownButtonSettings ButtonImage="up" ButtonHeight="35" ButtonWidth="35" />
</updown:SfNumericUpDown.IncrementButtonSettings>
<updown:SfNumericUpDown.DecrementButtonSettings>
<updown:UpDownButtonSettings ButtonImage="down" ButtonHeight="35" ButtonWidth="35" />
</updown:SfNumericUpDown.DecrementButtonSettings>
</updown:SfNumericUpDown> 

	
{% endhighlight %}

{% highlight C# %}

public partial class MainPage : ContentPage
    {
        SfNumericUpDown upDown;
        Grid incrementGrid, decrementGrid;
        UpDownButtonSettings incSettings, decrementSettings;
        Image incrementImage, decrementImage;
        public MainPage()
        {
            InitializeComponent();
           
            incSettings = new UpDownButtonSettings
            {
                ButtonImage = "up",
                ButtonHeight = 45,
                ButtonWidth = 45
            };
            decrementSettings = new UpDownButtonSettings
            {
                ButtonImage = "down",
                ButtonHeight = 45,
                ButtonWidth = 45
            };
            upDown = new SfNumericUpDown
            {
                SpinButtonAlignment = SpinButtonAlignment.Both,
                IncrementButtonSettings = incSettings,
                DecrementButtonSettings = decrementSettings
            }; 
            this.Content = upDown;
        }
        
    }

{% endhighlight %}

{% endtabs %}

![Display SfNumericUpDown control with Button properties](images/image.png)


### By using FontIconText

{% tabs %}

{% highlight xaml %}


<updown:SfNumericUpDown x:Name="upDown" SpinButtonAlignment="Both" TextAlignment="Center">
<updown:SfNumericUpDown.IncrementButtonSettings>
<updown:UpDownButtonSettings.ButtonFontFamily>
<OnPlatform
                x:TypeArguments="x:String">
                <On
                    Platform="Android"
                    Value="numeric.ttf">
                </On>
                <On
                    Platform="iOS"
                    Value="numeric">
                </On>
            </OnPlatform>
</updown:UpDownButtonSettings.ButtonFontFamily>
<updown:UpDownButtonSettings ButtonFontIcon="&#xe701;" ButtonHeight="35" ButtonWidth="35" />
</updown:SfNumericUpDown.IncrementButtonSettings>
<updown:SfNumericUpDown.DecrementButtonSettings>
<updown:UpDownButtonSettings.ButtonFontFamily>
<OnPlatform
                x:TypeArguments="x:String">
                <On
                    Platform="Android"
                    Value="numeric.ttf">
                </On>
                <On
                    Platform="iOS"
                    Value="numeric">
                </On>
            </OnPlatform>
</updown:UpDownButtonSettings.ButtonFontFamily>
<updown:UpDownButtonSettings ButtonFontIcon="&#xe700;" ButtonHeight="35" ButtonWidth="35" />
</updown:SfNumericUpDown.DecrementButtonSettings>
</updown:SfNumericUpDown> 

{% endhighlight %}

{% highlight C# %}

SfNumericUpDown upDown = new SfNumericUpDown();
upDown.SpinButtonAlignment = SpinButtonAlignment.Both;
UpDownButtonSettings incSettings = new UpDownButtonSettings();
incSettings.ButtonFontIcon = "\xe701";
    if (Device.OS == TargetPlatform.Android)
{
    incSettings.ButtonFontFamily = "numeric.ttf";
    decrementSettings.ButtonFontFamily = "numeric.ttf";
}

else
{
    incSettings.ButtonFontFamily = "numeric";
    decrementSettings.ButtonFontFamily = "numeric";
}
upDown.IncrementButtonSettings = incSettings;
UpDownButtonSettings decrementSettings = new UpDownButtonSettings();
decrementSettings.ButtonFontIcon = "\xe700";
decrementSettings.ButtonWidth = 45;
upDown.DecrementButtonSettings = decrementSettings;
this.Content = upDown;

{% endhighlight %}

{% endtabs %}

![Display the control with fonticon](images/FontTTf.png)

## Additional customization properties of UpDownButtonSettings

### BackgroundColor

This property is used to change the background color of increment and decrement buttons.

{% tabs %}

{% highlight xaml %}

<updown:SfNumericUpDown >
    <updown:SfNumericUpDown.IncrementButtonSettings>
    <updown:UpDownButtonSettings BackgroundColor="Red"/>
    </updown:SfNumericUpDown.IncrementButtonSettings>
    <updown:SfNumericUpDown.DecrementButtonSettings>
    <updown:UpDownButtonSettings BackgroundColor="Green"/>
    </updown:SfNumericUpDown.DecrementButtonSettings>
</updown:SfNumericUpDown>

{% endhighlight %}

{% highlight C# %}

 SfNumericUpDown numericUpDown = new SfNumericUpDown();
 UpDownButtonSettings incrementButtonSettings = new UpDownButtonSettings();
 UpDownButtonSettings decrementButtonSettings = new UpDownButtonSettings();
 numericUpDown.IncrementButtonSettings = incrementButtonSettings;
 numericUpDown.DecrementButtonSettings = decrementButtonSettings;
 incrementButtonSettings.BackgroundColor = Color.Red;
 decrementButtonSettings.BackgroundColor = Color.Green;

{% endhighlight %}

{% endtabs %}

![Display the value with maximum](images/buttonbackground.png)

### HighlightedBackgroundColor

This property is used to change the background color of when press the increment or decrement button.

{% tabs %}

{% highlight xaml %}

 <updown:SfNumericUpDown >
  <updown:SfNumericUpDown.IncrementButtonSettings>
  <updown:UpDownButtonSettings HighlightedBackgroundColor="Red"/>
  </updown:SfNumericUpDown.IncrementButtonSettings>
  <updown:SfNumericUpDown.DecrementButtonSettings>
  <updown:UpDownButtonSettings HighlightedBackgroundColor="Green"/>
  </updown:SfNumericUpDown.DecrementButtonSettings>
 </updown:SfNumericUpDown>

{% endhighlight %}

{% highlight C# %}

 SfNumericUpDown numericUpDown = new SfNumericUpDown();
 UpDownButtonSettings incrementButtonSettings = new UpDownButtonSettings();
 UpDownButtonSettings decrementButtonSettings = new UpDownButtonSettings();
 numericUpDown.IncrementButtonSettings = incrementButtonSettings;
 numericUpDown.DecrementButtonSettings = decrementButtonSettings;
 incrementButtonSettings.HighlightedBackgroundColor = Color.Red;
 decrementButtonSettings.HighlightedBackgroundColor = Color.Green;

{% endhighlight %}

{% endtabs %}

### ButtonFontColor

This property is used to change the text color of increment and decrement buttons.

{% tabs %}

{% highlight xaml %}

 <updown:SfNumericUpDown >
    <updown:SfNumericUpDown.IncrementButtonSettings>
    <updown:UpDownButtonSettings ButtonFontColor="Red"/>
    </updown:SfNumericUpDown.IncrementButtonSettings>
    <updown:SfNumericUpDown.DecrementButtonSettings>
    <updown:UpDownButtonSettings ButtonFontColor="Green"/>
    </updown:SfNumericUpDown.DecrementButtonSettings>
</updown:SfNumericUpDown>

{% endhighlight %}

{% highlight C# %}

 SfNumericUpDown numericUpDown = new SfNumericUpDown();
 UpDownButtonSettings incrementButtonSettings = new UpDownButtonSettings();
 UpDownButtonSettings decrementButtonSettings = new UpDownButtonSettings();
 numericUpDown.IncrementButtonSettings = incrementButtonSettings;
 numericUpDown.DecrementButtonSettings = decrementButtonSettings;
 incrementButtonSettings.ButtonFontColor = Color.Red;
 decrementButtonSettings.ButtonFontColor = Color.Green;

{% endhighlight %}

{% endtabs %}

### HighlightedButtonFontColor

This property is used to change the text color of button when press the increment or decrement button.

{% tabs %}

{% highlight xaml %}

<updown:SfNumericUpDown >
    <updown:SfNumericUpDown.IncrementButtonSettings>
    <updown:UpDownButtonSettings HighlightedButtonFontColor="Red"/>
    </updown:SfNumericUpDown.IncrementButtonSettings>
    <updown:SfNumericUpDown.DecrementButtonSettings>
    <updown:UpDownButtonSettings HighlightedButtonFontColor="Green"/>
    </updown:SfNumericUpDown.DecrementButtonSettings>
</updown:SfNumericUpDown>

{% endhighlight %}

{% highlight C# %}

 SfNumericUpDown numericUpDown = new SfNumericUpDown();
 UpDownButtonSettings incrementButtonSettings = new UpDownButtonSettings();
 UpDownButtonSettings decrementButtonSettings = new UpDownButtonSettings();
 numericUpDown.IncrementButtonSettings = incrementButtonSettings;
 numericUpDown.DecrementButtonSettings = decrementButtonSettings;
 incrementButtonSettings.HighlightedButtonFontColor = Color.Red;
 decrementButtonSettings.HighlightedButtonFontColor = Color.Green;

{% endhighlight %}

{% endtabs %}

## Spin validation

We can customize number increment/decrement mode in spin button interaction in two ways.

 * Default
 * Tapped

### Default

When [`SpinValidation`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfNumericUpDown.XForms~Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown~SpinValidation.html) property is set to `Default`, the numeric up down value gets updated on long press till the increment or decrement button gets disabled.

{% tabs %}

{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
numericUpDown.SpinValidation = SpinValidation.Default;

{% endhighlight %}

{% highlight xaml %}

<numeric:SfNumericUpDown x:Name="numericUpDown" SpinValidation="Default" />
	
{% endhighlight %}

{% endtabs %}

## Tapped

When [`SpinValidation`](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfNumericUpDown.XForms~Syncfusion.SfNumericUpDown.XForms.SfNumericUpDown~SpinValidation.html) property is set to `Tapped`, the numeric up down value gets updated on the increment or decrement button tap action.

{% tabs %}

{% highlight C# %}

SfNumericUpDown numericUpDown=new SfNumericUpDown();
numericUpDown.SpinValidation = SpinValidation.Tapped;

{% endhighlight %}

{% highlight xaml %}

<numeric:SfNumericUpDown x:Name="numericUpDown" SpinValidation="Tapped" />
	
{% endhighlight %}

{% endtabs %}

