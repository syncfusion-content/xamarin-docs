---
layout : post
title : Save image in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to save the image in ImageEditor for Xamarin.Forms
platform : xamarin.forms
control : ImageEditor
documentation : ug
---

## Save

You can save the image along with the current edits to the device using the `Save` method.

The saved image will be added to device for each platform in the following locations:

UWP :
The saved image will be added in default pictures library “C:\Users\your name\Pictures\Saved Pictures”.

Android:
The saved image will be added in default pictures library “Internal storage/Pictures/”.

{% tabs %}

{% highlight C# %}

     editor.Save();

{% endhighlight %}

{% endtabs %}

## Save events

The SfImageEditor has events when performing save operation namely `ImageSaving` and `ImageSaved`.

### ImageSaving

This event occurs before saving the image. You can control the save functionality using the `Cancel` argument.

* Cancel: 

It restricts saving image to the default location when set `Cancel` value to `true`.

{% highlight C# %}

          public MainPage()
            {               
                            . . .

                  editor.ImageSaving += editor_ImageSaving;

                            . . .
            }

        private void editor_ImageSaving(object sender, ImageSavingEventArgs args)
            {
                args.Cancel = true;  
            }


{% endhighlight %}

* Stream

You can get current image edits as stream using this argument.

{% highlight C# %}
         
        private void editor_ImageSaving(object sender, ImageSavingEventArgs args)
            {
                var stream = args.Stream;
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


## Reset

The `Reset` method resets the complete set of changes made in image and resets the image to original loaded image.

{% tabs %}

{% highlight C# %}

    editor.Reset();

{% endhighlight %}

{% endtabs %}

## Reset events

The SfImageEditor has events when performing reset operation namely `BeginReset` and `EndReset`.

### BeginReset

This event occurs before resetting the changes made in an image. You can control the reset functionality using the Cancel argument.


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

This event will be triggered after the image has been loaded. By using this event, you can add any shapes or text over an image or crop an image while initially loading the image. 

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
