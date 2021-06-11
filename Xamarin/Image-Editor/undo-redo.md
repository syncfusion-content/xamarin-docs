---
layout: post
title: Undo Redo in Xamarin Image Editor control | Syncfusion
description: Learn here all about Undo Redo support in Syncfusion Xamarin Image Editor (SfImageEditor) control and more.
platform: xamarin
control: ImageEditor
documentation: ug
---

# Undo Redo in Xamarin Image Editor (SfImageEditor)

One of the important features of the image editor control is to perform `Undo` and `Redo` operations for adding shapes, text, effects, and drawing paths. 

## Undo

The [`Undo`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_Undo) method is used to revert the changes done previously over an image.

Undo can be performed for the following operations:

* Add or delete shapes or text
* Change positions
* Color or fill changes
* Path drawings
* Applying effects

{% tabs %}

{% highlight C# %}

editor.Undo();

{% endhighlight %}

{% endtabs %}

## Redo

The [`Redo`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_Redo) method is used to redo the changes that are reverted by undo operation.

{% tabs %}

{% highlight C# %}

editor.Redo();

{% endhighlight %}

{% endtabs %}

N> Undo and redo cannot be applied for cropping and transformations.
