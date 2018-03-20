---
layout : post
title : Undo and Redo operations in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to perform undo and redo operations in ImageEditor for Xamarin.Forms
platform : xamarin.forms
control : ImageEditor
documentation : ug
---

# Undo–Redo support

One of the important features of the image editor control is to perform `Undo` and `Redo` operations for adding shapes, text, and drawing paths. The undo and redo operations can be done in the following two ways:

* From Toolbar
* Using Code

N> Undo and Redo cannot be applied for cropping and transformations

## Undo

### From Toolbar

The top toolbar in the Image Editor control contains the undo and redo buttons in between the `Save` and `Reset` buttons. The Undo and Redo buttons will be disabled by default. When you add a shape, text, or draw path, the undo button will be enabled. Clicking the `Undo` button clears the last performed operation. Undo can be performed for the following operations:

* Add/delete shapes or text
* Change positions
* Color/fill changes
* Path drawings

### Using Code

Programmatically, you can make use of the `Undo` method in the SfImageEditor control to revert the changes.

{% tabs %}

{% highlight C# %}

editor.Undo();

{% endhighlight %}

{% endtabs %}



## Redo

### From Toolbar

The Redo button will be disabled by default. The redo button will be enabled only when an undo operation is performed. Clicking the `Redo` button negates the undo operations.

### Using Code

The `Redo` method is used to redo the changes, which are reverted by undo operation.

{% tabs %}

{% highlight C# %}

editor.Redo();

{% endhighlight %}

{% endtabs %}


![SfImageEditor](ImageEditor_images/undoredo.gif)
