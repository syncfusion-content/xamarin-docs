---

layout: post
title: Customization of Syncfusion SfSignaturePad control for Xamarin.Forms
description: This section explains the details about the customization of Syncfusion SfSignaturePad control for Xamarin.Forms
platform: xamarin
control: SfSignaturePad
documentation: ug

---

# SfSignaturePad Customization

The `SignaturePad` control supports to customize the stroke color and stroke width using the following properties:

## Stroke color

The stroke color of the signature can be customized using the [`Stroke`].

{% tabs %}

{% highlight xaml %}

  <StackLayout Padding="10,40,10,10">
        <Label Text="Input Your Signature"/>
        <Frame>
            <sign:SfSignaturePad HeightRequest="250" StrokeColor="Brown"/>
        </Frame>
    </StackLayout>

{% endhighlight %}

{% highlight c# %}

    StackLayout stack = new StackLayout();
    stack.Padding = new Thickness(10, 40, 10, 10);
    Label text = new Label() { Text = "Input Your Signature" };
    Frame frame = new Frame();
    SfSignaturePad sign = new SfSignaturePad();
    sign.StrokeColor = Color.Brown;
    sign.HeightRequest = 250;
    frame.Content = sign;
    stack.Children.Add(text);
    stack.Children.Add(frame);
    this.Content = stack;
    
{% endhighlight %}

{% endtabs %}

![stroke color](images/StrokeColor.png)

## Stroke width

The stroke width of the signature can be customized by setting the MinimumStrokeWidth and MaximumStrokeWidth API. The MinimumStrokeWidth defines the minimum thickness of the stroke that can be drawn and the MaximumStrokeWidth defines the maximum thickness the stroke can draw based on the speed and impression we provide through gesture.

N> The default value of `MinimumStrokeWidth` is 0.08 and `MaximumStrokeWidth` is 5.

{% tabs %}

{% highlight xaml %}

    <StackLayout Padding="10,40,10,10">
        <Label Text="Input Your Signature"/>
        <Frame>
            <sign:SfSignaturePad HeightRequest="250" 
                                 MinimumStrokeWidth="1" 
                                 MaximumStrokeWidth="15"/>
        </Frame>
    </StackLayout>

{% endhighlight %}

{% highlight c# %}

    StackLayout stack = new StackLayout();
    stack.Padding = new Thickness(10, 40, 10, 10);
    Label text = new Label() { Text = "Input Your Signature" };
    Frame frame = new Frame();
    SfSignaturePad sign = new SfSignaturePad();
    sign.MinimumStrokeWidth = 1;
    sign.MaximumStrokeWidth = 4;
    sign.HeightRequest = 250;
    frame.Content = sign;
    stack.Children.Add(text);
    stack.Children.Add(frame);
    this.Content = stack;
    
{% endhighlight %}

{% endtabs %}

![Stroke width](images/StrokeWidth.png)

[Sample link](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Customization1624062135)
