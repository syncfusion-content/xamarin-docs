---
layout: post
title: Shapes in Xamarin Image Editor control | Syncfusion
description: Learn here all about Shapes support in Syncfusion Xamarin Image Editor (SfImageEditor) control and more.
platform: xamarin
control: ImageEditor
documentation: ug
---

# Shapes in Xamarin Image Editor (SfImageEditor)

You can annotate any shapes over an image using the [`AddShape`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_AddShape_Syncfusion_SfImageEditor_XForms_ShapeType_Syncfusion_SfImageEditor_XForms_PenSettings_) method. The following shapes are available in image editor:

* Circle
* Rectangle
* Arrow
* Path
* Line
* Dotted
* DoubleArrow
* DottedArrow
* DottedDoubleArrow

## Selecting a shape type

The [`ShapeType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ShapeType.html) is an enum property with values of [`Rectangle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ShapeType.html#Syncfusion_SfImageEditor_XForms_ShapeType_Rectangle), [`Circle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ShapeType.html#Syncfusion_SfImageEditor_XForms_ShapeType_Circle), [`Arrow`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ShapeType.html#Syncfusion_SfImageEditor_XForms_ShapeType_Arrow), [`Path`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ShapeType.html#Syncfusion_SfImageEditor_XForms_ShapeType_Path), [`Line`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ShapeType.html#Syncfusion_SfImageEditor_XForms_ShapeType_Line), [`Dotted`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ShapeType.html#Syncfusion_SfImageEditor_XForms_ShapeType_Dotted), [`DoubleArrow`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ShapeType.html#Syncfusion_SfImageEditor_XForms_ShapeType_DoubleArrow), [`DottedArrow`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ShapeType.html#Syncfusion_SfImageEditor_XForms_ShapeType_DottedArrow), and [`DottedDoubleArrow`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ShapeType.html#Syncfusion_SfImageEditor_XForms_ShapeType_DottedDoubleArrow). You can give the desired shape type as an argument to the [`AddShape`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_AddShape_Syncfusion_SfImageEditor_XForms_ShapeType_Syncfusion_SfImageEditor_XForms_PenSettings_) method.

{% highlight C# %}

      editor.AddShape(ShapeType.Circle);

{% endhighlight %}

By default, the toolbar contains the [`Rectangle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ImageEditorShapes.html#Syncfusion_SfImageEditor_XForms_ImageEditorShapes_Rectangle), [`Circle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ImageEditorShapes.html#Syncfusion_SfImageEditor_XForms_ImageEditorShapes_Circle), [`Arrow`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ImageEditorShapes.html#Syncfusion_SfImageEditor_XForms_ImageEditorShapes_Arrow) shapes. You can add other shapes to the toolbar items by using the [`VisibleShapesItems`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ToolbarSettings.html#Syncfusion_SfImageEditor_XForms_ToolbarSettings_VisibleShapesItems) in [`ToolbarSettings`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ToolbarSettings.html).

[`VisibleShapesItems`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ToolbarSettings.html#Syncfusion_SfImageEditor_XForms_ToolbarSettings_VisibleShapesItems) is a flagged enum property with values of [`Rectangle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ImageEditorShapes.html#Syncfusion_SfImageEditor_XForms_ImageEditorShapes_Rectangle), [`Circle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ImageEditorShapes.html#Syncfusion_SfImageEditor_XForms_ImageEditorShapes_Circle), [`Arrow`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ImageEditorShapes.html#Syncfusion_SfImageEditor_XForms_ImageEditorShapes_Arrow), [`Line`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ImageEditorShapes.html#Syncfusion_SfImageEditor_XForms_ImageEditorShapes_Line), [`Dotted`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ImageEditorShapes.html#Syncfusion_SfImageEditor_XForms_ImageEditorShapes_Dotted), [`DoubleArrow`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ImageEditorShapes.html#Syncfusion_SfImageEditor_XForms_ImageEditorShapes_DoubleArrow), [`DottedArrow`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ImageEditorShapes.html#Syncfusion_SfImageEditor_XForms_ImageEditorShapes_DottedArrow), and [`DottedDoubleArrow`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ImageEditorShapes.html#Syncfusion_SfImageEditor_XForms_ImageEditorShapes_DottedDoubleArrow). You can specify one or more shapes in the property to add shapes into the toolbar.

{% tabs %} 

{% highlight xaml %} 

            <editor:SfImageEditor.ToolbarSettings>
               <editor:ToolbarSettings VisibleShapesItems="Line,Dotted,DottedArrow,DottedDoubleArrow,DoubleArrow">
               </editor:ToolbarSettings>
            </editor:SfImageEditor.ToolbarSettings>  

{% endhighlight %}

{% highlight C# %}

      editor.ToolbarSettings.VisibleShapesItems = ImageEditorShapes.Line | ImageEditorShapes.Dotted | ImageEditorShapes.DottedArrow | ImageEditorShapes.DottedDoubleArrow | ImageEditorShapes.DoubleArrow;

{% endhighlight %}

{% endtabs %} 

![Shape types](ImageEditor_images/ShapeTypes.png)

N> If you add the shape when the SfImageEditor loaded in a view without image, then you need to call the [`AddShape`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_AddShape_Syncfusion_SfImageEditor_XForms_ShapeType_Syncfusion_SfImageEditor_XForms_PenSettings_) method after some time delay. If you add the shape when the SfImageEditor loaded in a view with image, then you need to call the [`AddShape`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_AddShape_Syncfusion_SfImageEditor_XForms_ShapeType_Syncfusion_SfImageEditor_XForms_PenSettings_) method in the [`ImageLoaded`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_ImageLoaded) event as shown in the following code sample.

{% highlight C# %}

            editor.ImageLoaded += (Object sender, ImageLoadedEventArgs args) =>
            {
                editor.AddShape(ShapeType.Circle);
            };

{% endhighlight %}

## Customizing a shape with pen settings

You can customize the appearance of each shape using the [`PenSettings`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.PenSettings.html) property:

### PenSettings

The [`PenSettings`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.PenSettings.html) property consists of the following properties:

* [`Color`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.PenSettings.html#Syncfusion_SfImageEditor_XForms_PenSettings_Color): Specifies the desired stroke color to a shape.
* [`FillColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.PenSettings.html#Syncfusion_SfImageEditor_XForms_PenSettings_FillColor): Specifies the desired fill color to a shape.
* [`StrokeWidth`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.PenSettings.html#Syncfusion_SfImageEditor_XForms_PenSettings_StrokeWidth): Allows to denote the stroke width for the desired shape.
* [`Mode`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.PenSettings.html#Syncfusion_SfImageEditor_XForms_PenSettings_Mode): Determines whether the shape color mode is [`Fill`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.Mode.html#Syncfusion_SfImageEditor_XForms_Mode_Fill) or [`Stroke`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.Mode.html#Syncfusion_SfImageEditor_XForms_Mode_Stroke). It is an enum value.
* [`Opacity`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.PenSettings.html#Syncfusion_SfImageEditor_XForms_PenSettings_Opacity): Denotes opacity for the desired shapes.
* [`Bounds`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.PenSettings.html#Syncfusion_SfImageEditor_XForms_PenSettings_Bounds): Allows to set frame for the newly added shapes (rectangle and circle). You can position the shapes wherever you want on the image.In percentage, the value of the shape frame should fall between 0 and 100.
* [`EnableDrag`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.PenSettings.html#Syncfusion_SfImageEditor_XForms_PenSettings_EnableDrag) - Controls the dragging of selected shape over the image.

N> The [`FillColor`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.PenSettings.html#Syncfusion_SfImageEditor_XForms_PenSettings_FillColor) property is applicable only if the ShapeType is [`Rectangle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ShapeType.html#Syncfusion_SfImageEditor_XForms_ShapeType_Rectangle) or [`Circle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ShapeType.html#Syncfusion_SfImageEditor_XForms_ShapeType_Circle).

* To add a [`Rectangle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ShapeType.html#Syncfusion_SfImageEditor_XForms_ShapeType_Rectangle), [`Circle`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ShapeType.html#Syncfusion_SfImageEditor_XForms_ShapeType_Circle), or [`Arrow`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ShapeType.html#Syncfusion_SfImageEditor_XForms_ShapeType_Arrow) over an image, specify the [`ShapeType`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.ShapeType.html) and the desired [`PenSettings`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.PenSettings.html) as shown in the following code snippet.

{% capture codesnippet1 %}

{% tabs %}

{% highlight C# %}

      editor.AddShape(ShapeType.Circle, new PenSettings() {Color = Color.Red, Mode= Mode.Stroke, Opacity=1f, Bounds = new Rectangle(20,20,35,35)});

{% endhighlight %}

{% endtabs %}

{% endcapture %}

{{ codesnippet1 | UnOrderList_Indent_Level_1 }} 

![SfImageEditor](ImageEditor_images/shapes.jpg)

* You can annotate any path on an image using free hand drawing as shown in the following code snippet.

{% capture codesnippet2 %}

{% tabs %}

{% highlight C# %}

      editor.AddShape(ShapeType.Path, new PenSettings() { StrokeWidth = 10 });

{% endhighlight %}

{% endtabs %}

{% endcapture %}

{{ codesnippet2 | UnOrderList_Indent_Level_1 }} 

![SfImageEditor](ImageEditor_images/path.jpg)

## Deleting a shape or text from view

You can delete the selected shape by using the [`Delete`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_Delete) method as shown in the following code snippet.


{% tabs %}

{% highlight C# %}

    editor.Delete();

{% endhighlight %}

{% endtabs %}

N> You cannot delete the path.

## Restricting the shape resize

You can restrict the shape resizing using the [`IsResizable`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.PenSettings.html#Syncfusion_SfImageEditor_XForms_PenSettings_IsResizable) property. By default, the value of the [`IsResizable`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.PenSettings.html#Syncfusion_SfImageEditor_XForms_PenSettings_IsResizable) property is true, so you can resize the shape added on an image. When the [`IsResizable`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.PenSettings.html#Syncfusion_SfImageEditor_XForms_PenSettings_IsResizable) property is disabled, shape added on an image cannot be resized and you can only drag the shape over an image as shown in the following code sample.

{% highlight c# %}

 editor.AddShape(ShapeType.Circle, new PenSettings() { IsResizable=false });

{% endhighlight %}

## See also

[How to add shapes to the image editor on initial loading](https://support.syncfusion.com/kb/article/9833/how-to-add-shapes-to-the-xamarin-forms-image-editor-on-initial-loading)

[How to add custom toolbar to add shapes or text dynamically in Xamarin.Forms SfImageEditor](https://support.syncfusion.com/kb/article/9151/how-to-add-custom-toolbar-to-add-shapes-or-text-dynamically-in-xamarin-forms-sfimageeditor)

[How to show dimension of shapes while resizing](https://support.syncfusion.com/kb/article/7812/how-to-show-dimension-of-shapes-while-resizing)

[How to update the color, stroke thickness for selected shape programmatically](https://support.syncfusion.com/kb/article/7818/how-to-update-the-color-stroke-thickness-for-selected-shape-programmatically)

[How to load shapes with custom bounds](https://support.syncfusion.com/kb/article/7804/how-to-load-shapes-with-custom-bounds)
