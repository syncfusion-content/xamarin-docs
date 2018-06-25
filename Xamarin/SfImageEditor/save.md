---
layout : post
title : Save image in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to save the image in ImageEditor for Xamarin.Forms
platform : xamarin.forms
control : ImageEditor
documentation : ug
---

# Save

You can save the image along with the changes to the device. Saving the image can be done in following two ways:

* From Toolbar
* Using Code

## From Toolbar

You can save the image from the toolbar by clicking the `Save` button in the top toolbar. The saved image will be added in default pictures folder of the device. 

Saved image location:

UWP :
Saved image will be added in default pictures library “C:\Users\your name\Pictures\Saved Pictures” .

Android:
Saved image will be added in default pictures library “Internal storage/Pictures/” .

## Using Code

Programmatically, you can make use of the `Save` method in the SfImageEditor control to save the image.

{% tabs %}

{% highlight C# %}

     editor.Save();

{% endhighlight %}

{% endtabs %}

## Events

The SfImageEditor has events when performing Save operation namely, ImageSaving and ImageSaved events.

### ImageSaving

This event occurs before saving the image. You can control the save functionality by using the Cancel argument.

{% tabs %}

{% highlight C# %}

    args.Cancel = true;

{% endhighlight %}

{% endtabs %}

### ImageSaved

This event occurs after the image has been saved. To get the location of the saved image, use the Location argument as shown below.

{% tabs %}

{% highlight C# %}

    string savedLocation = args.Location;

{% endhighlight %}

{% endtabs %}

# Reset

You can reset the changes and load the initial loaded image.

### From Toolbar

To reset the changes from the toolbar, click the `Reset` button in the top toolbar. The changes will be reset, and the initial loaded image will appear.

### Using Code

The `Reset` method resets the complete set of changes made in the image, and resets the original loaded image to the Image Editor control.


{% tabs %}

{% highlight C# %}

    editor.Reset();

{% endhighlight %}

{% endtabs %}

## Events

The SfImageEditor has events when performing Reset operation namely, BeginReset and EndReset.

### BeginReset

This event occurs before resetting the changes made in an image. You can control the reset functionality by using the Cancel argument.

{% tabs %}

{% highlight C# %}

     args.Cancel = true;

{% endhighlight %}

{% endtabs %}

### EndReset

This event occurs when reset has been completed.

### ImageLoaded Event

This event will be triggered once the image is loaded. By using this event we can add any shapes, text or crop over an image while initially loading the image. 

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


### ItemSelected Event

This event will be triggered whenever you tap the image editor selected shapes (Rectangle, Circle and Arrow) and Text. You can get the settings of each selected shapes and text with the help of ItemSelected argument. Also we can change the settings which will affect the selected shape.

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
