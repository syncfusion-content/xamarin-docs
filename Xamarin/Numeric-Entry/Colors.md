---
layout: post
title: Colors in Xamarin Numeric Entry Control | Syncfusion
description: Discover how to customize color properties in the Syncfusion Xamarin Numeric Entry (SfNumericTextBox) control.
platform: Xamarin
control: NumericTextBox
documentation: ug
---
# Colors in Xamarin Numeric Entry (SfNumericTextBox)

You can customize the [`SfNumericTextBox`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html) control's background, text, and border colors using the following bindable properties:

- [`TextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_TextColor): Sets the color of the numeric value displayed.
- `BackgroundColor`: Sets the background color of the NumericTextBox frame.
- [`BorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_BorderColor): Defines the border color of the NumericTextBox.
- [`WatermarkColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_WatermarkColor): Sets the color for the watermark text.

## Text Color in SfNumericTextBox

To set the [`TextColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_TextColor), use XAML or C#:

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox Value="123" TextColor="Green" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.TextColor = Color.Green;
numericTextBox.Value = 123;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Display SfNumericTextBox with TextColor](images/textcolor.png)

## Background Color in SfNumericTextBox

To set the `BackgroundColor` using XAML or C#:

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox Value="123" BackgroundColor="Maroon" TextColor="White"/>
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.BackgroundColor = Color.Maroon;
numericTextBox.TextColor = Color.White;
numericTextBox.Value = 123;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Display SfNumericTextBox with BackgroundColor](images/backgroundcolor.png)

## Border Color in SfNumericTextBox

To set the [`BorderColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_BorderColor) using XAML or C#:

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox Value="123" BorderColor="Red" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.BorderColor = Color.Red;
numericTextBox.Value = 123;
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Display SfNumericTextBox with BorderColor](images/bordercolor.png)

## Watermark Color in SfNumericTextBox

To set the [`WatermarkColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_WatermarkColor) using XAML or C#:

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox AllowNull="true" WatermarkColor="Blue" Watermark="Enter value"/>
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.AllowNull=true;
numericTextBox.WatermarkColor = Color.Blue;
numericTextBox.Watermark = "Enter value"
this.Content = numericTextBox;

{% endhighlight %}

{% endtabs %}

![Display SfNumericTextBox with WatermarkColor](images/watermarkcolor.png)

## Restrict Editing

You can restrict dynamic editing in the numeric entry using the [`IsReadOnly`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_IsReadOnly) property. Changes to the control text can still be made programmatically via the bindable [`Value`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.SfNumericTextBox.html#Syncfusion_SfNumericTextBox_XForms_SfNumericTextBox_Value) property.
	
## Visual States

The [SfNumericTextBox](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNumericTextBox.XForms.html) is customizable based on [VisualStates](https://learn.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/visual-state-manager).

**Available Visual States:**
- Normal
- Focused
- Disabled

> **Note:** The focused visual state is available only on Android and iOS platforms.

{% tabs %}

{% highlight xaml %}

    <StackLayout HorizontalOptions="Center" VerticalOptions="Center">
        <numeric:SfNumericTextBox  WidthRequest="100" Value="50">

        <VisualStateManager.VisualStateGroups>
            <VisualStateGroup x:Name="CommonStates">
                <VisualState x:Name="Normal">
                    <VisualState.Setters>
                        <Setter Property="BackgroundColor" Value="White" />
                    </VisualState.Setters>
                </VisualState>
                <VisualState x:Name="Disabled">
                    <VisualState.Setters>
                        <Setter Property="BackgroundColor" Value="DarkGray" />
                    </VisualState.Setters>
                </VisualState>
                <VisualState x:Name="Focused">
                    <VisualState.Setters>
                        <Setter Property="BackgroundColor" Value="Yellow" />
                    </VisualState.Setters>
                </VisualState>
            </VisualStateGroup>
        </VisualStateManager.VisualStateGroups>
	</numeric:SfNumericTextBox>
  </StackLayout>

{% endhighlight %}

{% highlight c# %}

            StackLayout stackLayout = new StackLayout
            {
                HorizontalOptions = LayoutOptions.Center,
                VerticalOptions = LayoutOptions.Center
            };
            SfNumericTextBox numericTextBox = new SfNumericTextBox
            {
                Value = 50,
                WidthRequest = 100
            };

            VisualStateGroupList visualStateGroupList = new VisualStateGroupList();

            VisualStateGroup commonStateGroup = new VisualStateGroup();
            VisualState normalState = new VisualState
            {
                Name = "Normal"
            };
            normalState.Setters.Add(new Setter { Property = SfNumericTextBox.BackgroundColorProperty, Value = Color.White });

            VisualState disabledState = new VisualState
            {
                Name = "Disabled"
            };
            disabledState.Setters.Add(new Setter { Property = SfNumericTextBox.BackgroundColorProperty, Value = Color.DarkGray });

            VisualState fousedState = new VisualState
            {
                Name = "Focused"
            };
            fousedState.Setters.Add(new Setter { Property = SfNumericTextBox.BackgroundColorProperty, Value = Color.Yellow });

            commonStateGroup.States.Add(normalState);
            commonStateGroup.States.Add(disabledState);
            commonStateGroup.States.Add(fousedState);
            visualStateGroupList.Add(commonStateGroup);
            VisualStateManager.SetVisualStateGroups(numericTextBox, visualStateGroupList);

            stackLayout.Children.Add(numericTextBox);
            this.Content = stackLayout;
			
{% endhighlight %}

{% endtabs %}

**Normal Visual State**
![SfNumericTextBox with Normal Visual State](images/NormalState.PNG)

**Disabled Visual State**
![SfNumericTextBox with Disabled Visual State](images/DisabledState.PNG)

**Focused Visual State**
![SfNumericTextBox with Focused Visual State](images/FocusState.PNG)

## See Also

- [How to customize the border of SfNumericTextBox](https://support.syncfusion.com/kb/article/6848/how-to-custom-the-border-of-numerictextbox)
- [How to customize the color appearance of SfNumericTextBox](https://support.syncfusion.com/kb/article/10060/how-to-customize-the-color-appearance-of-numeric-entry-in-xamarinforms)
