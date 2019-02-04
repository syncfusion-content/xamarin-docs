---
layout: post
title: Appearance and styling in Syncfusion NumericUpDown control for Xamarin.Forms
description: Learn how to add customize spin buttons position in NumericUpDown.
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


![](images/right.png)

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


![](images/left.png)

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


![](images/both.png)

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

	<StackLayout Padding="50" >

		<updown:SfNumericUpDown x:Name="upDown" SpinButtonAlignment="Both" TextAlignment="Center" />

	</StackLayout>
	
{% endhighlight %}

{% highlight C# %}

			UpDownButtonSettings incSettings = new UpDownButtonSettings();
			Grid incrementStack = new Grid();
			Image incrementImage = new Image();
			incrementImage.HorizontalOptions = LayoutOptions.Center;
			incrementImage.VerticalOptions = LayoutOptions.Center;
			incrementImage.Source = (FileImageSource)ImageSource.FromFile("up.png");
			incrementImage.Aspect = Aspect.AspectFit;
			incrementStack.Children.Add(incrementImage);
			incrementStack.Padding = new Thickness(5,7);
			incSettings.ButtonView = incrementStack;
			incSettings.ButtonHeight = 45;
			incSettings.ButtonWidth = 45;
			upDown.IncrementButtonSettings = incSettings;
			UpDownButtonSettings decrementSettings = new UpDownButtonSettings();
			Grid decrementStack = new Grid();
			Image decrementImage = new Image();
			decrementImage.Source = (FileImageSource)ImageSource.FromFile("down.png");
			decrementImage.Aspect = Aspect.AspectFit;
			decrementImage.HorizontalOptions = LayoutOptions.Center;
			decrementImage.VerticalOptions = LayoutOptions.Center;
			decrementStack.Children.Add(decrementImage);
			decrementStack.Padding = new Thickness(5,7);
			decrementSettings.ButtonView = decrementStack;
			decrementSettings.ButtonHeight = 45;
			decrementSettings.ButtonWidth = 45;
			upDown.DecrementButtonSettings = decrementSettings;

{% endhighlight %}

{% endtabs %}

### By using Image

{% tabs %}

{% highlight xaml %}

	<StackLayout Padding="50" >

		<updown:SfNumericUpDown x:Name="upDown" SpinButtonAlignment="Both" TextAlignment="Center" />

	</StackLayout>
	
{% endhighlight %}

{% highlight C# %}

			UpDownButtonSettings incSettings = new UpDownButtonSettings();
			Grid incrementStack = new Grid();
			incSettings.ButtonImage = "up";
			incSettings.ButtonHeight = 45;
			incSettings.ButtonWidth = 45;
			upDown.IncrementButtonSettings = incSettings;
			UpDownButtonSettings decrementSettings = new UpDownButtonSettings();
			Grid decrementStack = new Grid();
			decrementSettings.ButtonImage = "down";
			decrementSettings.ButtonHeight = 45;
			decrementSettings.ButtonWidth = 45;
			upDown.DecrementButtonSettings = decrementSettings;

{% endhighlight %}

{% endtabs %}

![](images/FontTTf.png)



### By using FontIconText

{% tabs %}

{% highlight xaml %}

	<StackLayout Padding="50" >

		<updown:SfNumericUpDown x:Name="upDown" SpinButtonAlignment="Both" TextAlignment="Center" />

	</StackLayout>
	
{% endhighlight %}

{% highlight C# %}

			UpDownButtonSettings incSettings = new UpDownButtonSettings();
            UpDownButtonSettings decrementSettings = new UpDownButtonSettings();
			incSettings.ButtonFontIcon = "\xe701";
            decrementSettings.ButtonFontIcon = "\xe700";
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
			upDown.DecrementButtonSettings = decrementSettings;

{% endhighlight %}

{% endtabs %}

![](images/image.png)