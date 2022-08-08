---
layout: post
title: Events in Xamarin SignaturePad control | Syncfusion
description: Learn here all about SignaturePad Events support in Syncfusion Xamarin SignaturePad (SfSignaturePad) control and more.
platform: Xamarin
control: SignaturePad
documentation: ug
---

# SignaturePad Events in Xamarin Signature (SfSignaturePad)

## StrokeStarted 

The [`StrokeStarted`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html#Syncfusion_XForms_SignaturePad_SfSignaturePad_StrokeStarted) event will be triggered when drawing is started.

CancelEventArgs - SignaturePad draw start action can be restricted by setting the e.cancel to true.

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

The [`StrokeCompleted`](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.SignaturePad.SfSignaturePad.html#Syncfusion_XForms_SignaturePad_SfSignaturePad_StrokeCompleted) event will be triggered when drawing is ended.

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