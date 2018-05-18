---

layout: post
title: Accessing Header in Syncfusion SfCircularGauge control for Xamarin.Forms
description:  Learn how to set header in Syncfusion SfCircularGauge control
platform: xamarin
control: SfCircularGauge
documentation: ug

---

# Header

The [`Header`](https://help.syncfusion.com/cr/cref_files/xamarin/sfgauge/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.Header.html) support allows you to show text inside the gauge control. A circular gauge can be made self-descriptive about the data. It can be  measured with use of the header.

## Adding header in circular gauge

###  Header

The [`Header`](https://help.syncfusion.com/cr/cref_files/xamarin/sfgauge/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.Header.html) can be used to set a unique header for the circular gauge. You can add text as headers in a circular gauge. Multiple headers also can be added in a circular gauge.

{% tabs %}

{% highlight xaml %}

     <gauge:SfCircularGauge>
	  
         <gauge:SfCircularGauge.Headers>
            <gauge:Header Text="Speedometer"/>
        </gauge:SfCircularGauge.Headers>
     </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge(); 
    Header header = new Header();
    header.Text = "Speedometer";
    circularGauge.Headers.Add(header); 

{% endhighlight %}

{% endtabs %}

![](header_images/header.png)

##  Setting position for header

The [`Position`](https://help.syncfusion.com/cr/cref_files/xamarin/sfgauge/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.Header~Position.html) property is used to place the header in a circular gauge. The value for [`Position`](https://help.syncfusion.com/cr/cref_files/xamarin/sfgauge/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.Header~Position.html) should be specified in offset value. In the Point value, which has been given for the `Position`, first value represent x-coordinate and second value represents y-coordinate. By default, it is placed at (0.5, 0.7).

{% tabs %}

{% highlight xaml %}
 
     <gauge:SfCircularGauge>
        <gauge:SfCircularGauge.Headers>
            <gauge:Header Text="Speedometer" Position="0.5,0.5" />
        </gauge:SfCircularGauge.Headers>
     </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge(); 
    Header header = new Header();
    header.Text = "Speedometer";
    header.Position = new Point(0.5, 0.5);
    circularGauge.Headers.Add(header); 
    
{% endhighlight %}

{% endtabs %}

![](header_images/header-position.png)

##  Customization of header

You can customize the header's text by using the [`FontFamily`](https://help.syncfusion.com/cr/cref_files/xamarin/sfgauge/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.Header~FontFamily.html), [`FontAttribute`](https://help.syncfusion.com/cr/cref_files/xamarin/sfgauge/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.Header~FontAttributes.html) and [`TextSize`](https://help.syncfusion.com/cr/cref_files/xamarin/sfgauge/Syncfusion.SfGauge.XForms~Syncfusion.SfGauge.XForms.Header~TextSize.html) properties.

{% tabs %}

{% highlight xaml %}
 
    <gauge:SfCircularGauge>
         <gauge:SfCircularGauge.Headers>
             <gauge:Header Text="Speedometer" TextSize="20" ForegroundColor="Blue" FontAttributes="Bold">
			        <gauge:Header.FontFamily>
                        <OnPlatform x:TypeArguments="x:String" iOS="Chalkduster" Android="algerian.ttf" WinPhone="Chiller" />
                    </gauge:Header.FontFamily>
		     </gauge:Header>
        </gauge:SfCircularGauge.Headers>
    </gauge:SfCircularGauge>

{% endhighlight %}

{% highlight c# %}

    SfCircularGauge circularGauge = new SfCircularGauge(); 
    Header header = new Header();
    header.Text = "Speedometer";
    header.TextSize = 20;
    header.FontAttributes = FontAttributes.Bold;
    header.FontFamily = Device.RuntimePlatform == Device.iOS ? "Chalkduster" : Device.RuntimePlatform == Device.Android ? "algerian.ttf" : "Chiller";
    header.ForegroundColor = Color.Blue;   
    circularGauge.Headers.Add(header); 
    this.content = circularGauge;
    
{% endhighlight %}

{% endtabs %}

![](header_images/header-customise.png)