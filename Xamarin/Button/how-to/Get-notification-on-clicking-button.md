---
layout: post
title: How to get notification on clicking  Syncfusion SfButton
description: How to get click action in  SfButton.
platform: xamarin.forms
control: sfbutton
documentation: ug
---

# Getting notification on clicking button

Similar like a framework button, here also while clickingthe [`SfButton`](https://help.syncfusion.com/cr/xamarin/Syncfusion.Buttons.XForms~Syncfusion.XForms.Buttons.SfButton.html), that corresponding Click event will be raised.

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