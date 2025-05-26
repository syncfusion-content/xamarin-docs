---
layout: post
title: Event in Xamarin Button Control | Syncfusion
description: Discover event support in the Syncfusion Xamarin Button (SfButton) control and learn how to handle click events.
platform: Xamarin
control: SfButton
documentation: ug 

---

# Event in Xamarin Button (SfButton)

## Clicked Event

The click event occurs when the [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Buttons.SfButton.html) is clicked. The event argument is of type `EventArgs`.

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
