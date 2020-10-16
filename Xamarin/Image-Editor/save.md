---
layout: post
title: Save image in Syncfusion SfImageEditor control in Xamarin.Forms
description: Learn how to save the image in different ways as well as the use of different events in ImageEditor for Xamarin.Forms
platform: xamarin.forms
control: ImageEditor
documentation: ug
---

# Save in SfImageEditor

You can save the image along with the current edits to the device using the [`Save`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_Save_System_String_Xamarin_Forms_Size_) method.

The saved image will be added to the device for each platform in the following locations:

UWP :
The saved image will be added to default pictures library “C:\Users\your name\Pictures\Saved Pictures”.

Android:
The saved image will be added to default pictures library “Internal storage/Pictures/”.

N> Set the requestLegacyExternalStorage value as true in your app's manifest file, if the target version is 10. 

{% tabs %}

{% highlight xaml %}

<manifest ...>

  <application android:requestLegacyExternalStorage="true" ...>
    ...
  </application>
  
</manifest>

{% endhighlight %}

{% endtabs %}

iOS:
In iOS device, the saved image will be added to default pictures library.
In iOS simulator, the saved image will be added to (Library\developer\CoreSimulator\Devices) location. 

{% tabs %}

{% highlight C# %}

     editor.Save();

{% endhighlight %}

{% endtabs %}

## Save events

The SfImageEditor has events when performing the save operation namely [`ImageSaving`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html) and [`ImageSaved`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html).

### ImageSaving

This event occurs before saving the image.

`Cancel` : You can control the save functionality using the `Cancel` argument.

It restricts saving image to the default location when set `Cancel` value to `true`.

{% tabs %}

{% highlight xaml %}

            <imageeditor:SfImageEditor Source="{Binding Image}" ImageSaving="SfImageEditor_ImageSaving" />

{% endhighlight %}

{% highlight C# %}
            
            private void editor_ImageSaving(object sender, ImageSavingEventArgs args)
            {
                args.Cancel = true;  
            }

{% endhighlight %}

{% endtabs %}

`Stream` : You can get current image edits as stream using this argument.

{% highlight C# %}
           
            private void editor_ImageSaving(object sender, ImageSavingEventArgs args)
            {
                var stream = args.Stream;
            }

{% endhighlight %}

`FileName`: You can save the edited image in the specified name. 

{% highlight c# %}

          private void SfImageEditor_ImageSaving(object sender, ImageSavingEventArgs args)
          {
             args.FileName = "SavedImage";
          }

{% endhighlight %}

### ImageSaved

This event occurs after the image has been saved. To get the location of the saved image, use the location argument as shown in the following code.

{% highlight C# %}

          public MainPage()
            {               
                            . . .

                 editor.ImageSaved += editor_ImageSaved;

                            . . .
            }

         private void editor_ImageSaved(object sender, ImageSavedEventArgs args)
            {
                 string savedLocation = args.Location; // You can get the saved image location with the help of this argument
            }


{% endhighlight %}

## Saving Image with Custom Size and Format

The [`Save`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_Save_System_String_Xamarin_Forms_Size_) method in the SfImageEditor control allows user to save an image in different format such as `png`, `jpg`, and `bmp`.

To choose the format while Saving the image.

{% tabs %}

{% highlight C# %}

editor.Save(".png");

{% endhighlight %}

{% endtabs %}

To choose the format and size while Saving the image as follows.

{% tabs %}

{% highlight C# %}

editor.Save(".png",new Size(913,764));

{% endhighlight %}

{% endtabs %} 

N> Supported formats are `.png`, `.jpg`, and `.bmp`.

## Reset

The [`Reset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html#Syncfusion_SfImageEditor_XForms_SfImageEditor_Reset) method, resets the complete set of changes made in image and also resets the image to original loaded image.

{% tabs %}

{% highlight C# %}

    editor.Reset();

{% endhighlight %}

{% endtabs %}

## Reset events

The SfImageEditor has events when performing reset operation namely [`BeginReset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html) and [`EndReset`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfImageEditor.XForms.SfImageEditor.html).

### BeginReset

This event occurs before resetting the changes made in an image. You can control the reset functionality using the cancel argument.


{% highlight C# %}

        public MainPage()
            {               
                            . . .

                         editor.BeginReset += editor_BeginReset;

                            . . .
            }

        private void editor_BeginReset(object sender, BeginResetEventArgs args)
            {
                args.Cancel = true; //It restricts resetting image to initial loaded image.
            }

{% endhighlight %}

### EndReset

This event occurs when reset has been completed.

{% highlight C# %}

        public MainPage()
            {               
                            . . .

                             editor.EndReset += editor_EndReset;

                            . . .
            }

       private void editor_EndReset(object sender, EndResetEventArgs args)
        {
             Navigation.PushModalAsync(new NewImageEditorPage()); //Navigates to new page after completing the reset action.
        }

{% endhighlight %}

## ImageLoaded Event

This event will be triggered after the image has been loaded. By this event you can add any shapes or text over an image or crop an image while initially loading the image. 

{% highlight C# %}

        public MainPage()
            {               
                            . . .

                editor.ImageLoaded += Editor_ImageLoaded;

                            . . .
            }

        private void Editor_ImageLoaded(object sender, ImageLoadedEventArgs args)
            {
                editor.AddShape(ShapeType.Circle, new PenSettings() {Color = Color.Green,Mode = Mode.Stroke });
            }

{% endhighlight %}


## ItemSelected Event

This event will be triggered whenever you tap the selected shapes (rectangle, circle, and arrow) and text. You can get the settings of each selected shapes and text using the ItemSelected argument. You can also change the settings that will affect the selected shape.

{% highlight C# %}

        public MainPage()
            {               
                            . . .

                editor.ImageLoaded += Editor_ImageLoaded;
                editor.ItemSelected += Editor_ItemSelected;

                            . . .
            }

        private void Editor_ImageLoaded(object sender, ImageLoadedEventArgs args)
            {
                editor.AddShape(ShapeType.Circle, new PenSettings() {Color = Color.Green,Mode = Mode.Stroke });
            }

        private void Editor_ItemSelected(object sender, ItemSelectedEventArgs args)
            {
                var Settings = args.Settings;   

                if (Settings is PenSettings)
                {
                    (Settings as PenSettings).Color = color;
                }
                else
                {
                    (Settings as TextSettings).Color = color;
                }
     
            }

{% endhighlight %}

## ItemUnselected Event

This event will be triggered whenever you change the shape selections from one shape to another shape (rectangle, circle, arrow, and text). You can get the settings of previous selected shapes and text using the ItemUnselected event. You can also change the settings of previous selected shape.

{% highlight C# %}

public MainPage()
{
    editor.ItemUnselected += Editor_ItemUnselected;
}

private void Editor_ItemUnselected(object sender, ItemUnselectedEventArgs e)
{
    var Settings = e.Settings;
    if (Settings is PenSettings)
    {
        (Settings as PenSettings).Color = Color.Green;
    }
    else
    {
        (Settings as TextSettings).Color = Color.Green;
    }
}

{% endhighlight %}

## ImageEdited Event

This event occurs whenever you start to edit an image. You can know whether the current image is edited or not using the IsImageEdited argument.

{% highlight c# %}

public MainPage()
{               
    . . .
    editor.ImageEdited += ImageEditor_ImageEdited;
    . . .
}

private void ImageEditor_ImageEdited(object sender, ImageEditedEventArgs e)
{
    If (args.IsImageEdited)
    {
    }            
}

{% endhighlight %}

## See also

[How to import and export image from SQL DB](https://www.syncfusion.com/kb/9633/how-to-import-and-export-image-from-sql-db)

[How to retrieve image from saved location](https://www.syncfusion.com/kb/8871/how-to-retrieve-image-from-saved-location)

[How to change the image saving location](https://www.syncfusion.com/kb/8827/how-to-change-the-image-saving-location)

[How to resolve application crash while saving images to device gallery](https://www.syncfusion.com/kb/8304/how-to-resolve-application-crash-while-saving-images-to-device-gallery)
