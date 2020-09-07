---
layout: post
title: Undo and Redo operations in Syncfusion SfImageEditor in Xamarin.Forms
description: Learn how to perform the undo and redo operations in SfImageEditor control for Xamarin.Forms platform
platform: xamarin.forms
control: ImageEditor
documentation: ug
---

# Undo and Redo operations in SfImageEditor

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
