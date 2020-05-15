---
layout: post
title: How to get notification on clicking  Syncfusion SfButton
description: How to get the notification of click event action in Syncfusion Xamarin.Forms Button (SfButton) control
platform: Xamarin.Forms
control: SfButton
documentation: ug 

---

# Events in Xamarin Button (SfButton)

## Clicked event

The Click event occurs when the [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton.html) is clicked. The event argument is of type `EventArgs`.

{% tabs %}
{% highlight xaml %}

 <buttons:SfButton x:Name="SfButton" Text="Button" Clicked="Button_Clicked"/>
{% endhighlight %}
{% highlight c# %}

       public MainPage()
        {
            InitializeComponent();
            SfButton button = new SfButton();
            button.Text = "Button";
            button.Clicked += Button_Clicked;
            ....
        }

        ...
        private void Button_Clicked(object sender, EventArgs e)
        {
           // Invoke your desired action here
        }

{% endhighlight %}
{% endtabs %}
