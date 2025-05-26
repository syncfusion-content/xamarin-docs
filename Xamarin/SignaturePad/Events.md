---
layout: post
title: Events in Xamarin SignaturePad Control | Syncfusion
description: Learn about event support in Syncfusion Xamarin SignaturePad (SfSignaturePad) control, including how to handle StrokeStarted and StrokeCompleted events.
platform: Xamarin
control: SfSignaturePad
documentation: ug
---

# SignaturePad Events in Xamarin SignaturePad (SfSignaturePad)

## StrokeStarted 

The [`StrokeStarted`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html#Syncfusion_XForms_SignaturePad_SfSignaturePad_StrokeStarted) event is triggered when drawing begins.

- [`CancelEventArgs`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.Core.CancelEventArgs.html): The SignaturePad draw start action can be restricted by setting `e.Cancel` to `true`.

{% tabs %}

{% highlight xaml %}

    <signature:SfSignaturePad  StrokeStarted="Signature_StrokeStarted">
    </signature:SfSignaturePad>

{% endhighlight %}

{% highlight C# %}

     public MainPage()
     {
       InitializeComponent();
       Signature.StrokeStarted += this.Signature_StrokeStarted;
     }

     private void Signature_StrokeStarted(object sender, Syncfusion.XForms.Core.CancelEventArgs e)        
     {
            //To restrict the draw stroke, set e.Cancel to true.
               e.Cancel = true;
     }

{% endhighlight %}

{% endtabs %}

## StrokeCompleted

The [`StrokeCompleted`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html#Syncfusion_XForms_SignaturePad_SfSignaturePad_StrokeCompleted) event is triggered when drawing ends.

{% tabs %}

{% highlight xaml %}

     <signature:SfSignaturePad StrokeCompleted="Signature_StrokeCompleted">
     </signature:SfSignaturePad>

{% endhighlight %}

{% highlight C# %}

     public MainPage()
     {
       InitializeComponent();
       Signature.StrokeCompleted += Signature_StrokeCompleted;
     }

     private void Signature_StrokeCompleted(object sender, EventArgs e)
     {

     }

{% endhighlight %}

{% endtabs %}