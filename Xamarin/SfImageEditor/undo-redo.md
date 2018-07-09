---
layout : post
title : Undo and Redo operations in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to perform undo and redo operations in ImageEditor for Xamarin.Forms
platform : xamarin.forms
control : ImageEditor
documentation : ug
---

# Undo–Redo support

One of the important features of the image editor control is to perform `Undo` and `Redo` operations for adding shapes, text, and drawing paths. 

## Undo

`Undo` method is used to revert the previous changes one by one, made over an image.

Undo can be performed for the following operations:

* Add/delete shapes or text
* Change positions
* Color/fill changes
* Path drawings

{% tabs %}

{% highlight C# %}

editor.Undo();

{% endhighlight %}

{% endtabs %}

## Redo

The `Redo` method is used to redo the changes, which are reverted by undo operation.

{% tabs %}

{% highlight C# %}

editor.Redo();

{% endhighlight %}

{% endtabs %}

N> Undo and Redo cannot be applied for cropping and transformations

![SfImageEditor](ImageEditor_images/undoredo.gif)
