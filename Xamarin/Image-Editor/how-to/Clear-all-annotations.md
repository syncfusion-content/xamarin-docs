---
layout: post
title: How to clear all annotations programmatically | Syncfusion
description: Learn here about how to clear all the annotations (Text, Shapes, Paths, Custom views) alone added in the image editor.
platform: xamarin
control: SfImageEditor
documentation : ug
---

# Clear all annotations (Text, Shapes, Paths, etc) from Image Editor

By invoking the `ClearAnnotations` method of SfImageEditor, you can clear all the annotations (Text, Shapes, Path, and CustomView) added in the image editor without resetting the other edits (Rotation, Flip, Crop, Effects, etc).

The following code sample demonstrates this.

{% highlight xaml %}

<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="*" />
        <RowDefinition Height="Auto" />
    </Grid.RowDefinitions>
    <imageEditor:SfImageEditor x:Name="imageEditor"
                               Source="{Binding Image}"/>
    <StackLayout Grid.Row="1"
                 Orientation="Horizontal">
        <Button x:Name="ClearAnnotations"
                Text="ClearAnnotations"
                Clicked="ClearAnnotations_Clicked"/>
    </StackLayout>
</Grid>

{% endhighlight %}

{% highlight c# %}

private void ClearAnnotations_Clicked(object sender, EventArgs e)
{
    imageEditor.ClearAnnotations();
}

{% endhighlight %}

![ClearAnnotations support in Xamarin.Forms ImageEditor](images/ClearAnnotations.gif)