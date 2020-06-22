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
            <sign:SfSignaturePad HeightRequest="100" StrokeColor="Brown"/>
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
    sign.HeightRequest = 100;
    frame.Content = sign;
    stack.Children.Add(text);
    stack.Children.Add(frame);
    this.Content = stack;
    
{% endhighlight %}

{% endtabs %}

![stroke color](images/StrokeColor.png)

## Stroke width

The stroke width of the signature can be customized using the `MinimumStrokeWidth` and `MaximumStrokeWidth` properties, respectively.
N> The default value of `MinimumStrokeWidth` is 0.08 and `MaximumStrokeWidth` is 5.

{% tabs %}

{% highlight xaml %}

    <StackLayout Padding="10,40,10,10">
        <Label Text="Input Your Signature"/>
        <Frame>
            <sign:SfSignaturePad HeightRequest="100" 
                                 MinimumStrokeWidth="1" 
                                 MaximumStrokeWidth="4"/>
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
    sign.HeightRequest = 100;
    frame.Content = sign;
    stack.Children.Add(text);
    stack.Children.Add(frame);
    this.Content = stack;
    
{% endhighlight %}

{% endtabs %}

![Stroke width](images/StrokeWidth.png)

[Sample link](https://www.syncfusion.com/downloads/support/directtrac/general/ze/Customization1624062135)
