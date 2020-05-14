---
layout: post
title: How to get notification on clicking  Syncfusion SfButton
description: How to get the notification of click event action in Syncfusion Xamarin.Forms Button (SfButton) control
platform: xamarin.forms
control: sfbutton
documentation: ug
---

# Getting the notification on clicking button

Similar like a framework button, here also while clicking the [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton.html), that corresponding Click event will be raised.

{%tabs%}
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


You can find the complete getting started sample here: [Getting started](http://www.syncfusion.com/downloads/support/directtrac/general/ze/Button_GettingStarted-1596781257.zip).