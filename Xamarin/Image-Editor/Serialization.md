---
layout: post
title: Serialization in Xamarin Image Editor control | Syncfusion<sup>&reg;</sup>
description: Learn here all about Serialization support in Syncfusion<sup>&reg;</sup> Xamarin Image Editor (SfImageEditor) control and more.
platform: xamarin
control: ImageEditor
documentation: ug
---

# Serialization in Xamarin Image Editor (SfImageEditor)

The image editor control provides support to serialize and deserialize the shapes (circle, arrow, and rectangle), free hand drawing, text and toolbar settings. You can save the current state of the image editor and load it back when it is needed.

## Serialization

The SaveEdits() method is used to serialize the current edits of shapes. The serialized object will be returned in the form of JSON stream.

{% tabs %}

{% highlight C# %}
    
	SfImageEditor editor;
        public MainPage()
        {
            InitializeComponent();
            Grid grid = new Grid();
            editor = new SfImageEditor();
            Button saveEdits = new Button();
            saveEdits.Text = "Serialize";
            saveEdits.Clicked += SaveEdits_Clicked;
            grid.RowDefinitions.Add(new RowDefinition() { Height = 100 });
            grid.RowDefinitions.Add(new RowDefinition() { Height = GridLength.Star });
            grid.Children.Add(saveEdits, 0, 0);
            grid.Children.Add(editor, 0, 1);
            this.Content = grid;

        }
        void SaveEdits_Clicked(object sender, EventArgs e)
        {
            Stream stream = editor.SaveEdits();
        }
    
	
{% endhighlight %}

{% endtabs %}

You can save stream into .txt format file. If you save stream as .txt format file to deserialize the shapes, then set the Build action to `Embedded resource` in project.

Sample text file: [ImageEditor.txt](https://s3.amazonaws.com/files2.syncfusion.com/dtsupport/directtrac/general/txt/Chart677841499.txt?AWSAccessKeyId=AKIAWH6GYCX3TZ4I4YVB&Expires=1695709055&Signature=9L6xHfsas4aolVJk5ps3IkVEdBk%3D).

## Deserialization

The LoadEdits() method is used to deserialize the edits over an image.

{% tabs %}

{% highlight C# %}
       
	  SfImageEditor editor;
        public MainPage()
        {
            InitializeComponent();
            Grid grid = new Grid();
            editor = new SfImageEditor();
            Button LoadEdits = new Button();
            LoadEdits.Text = "Deserialize";
            LoadEdits.Clicked += LoadEdits_Clicked;
            grid.RowDefinitions.Add(new RowDefinition() { Height = 100 });
            grid.RowDefinitions.Add(new RowDefinition() { Height = GridLength.Star });
            grid.Children.Add(LoadEdits, 0, 0);
            grid.Children.Add(editor, 0, 1);
            this.Content = grid;

        }
        void LoadEdits_Clicked(object sender, EventArgs e)
        {
            var assembly = typeof(App).GetTypeInfo().Assembly;
            Stream stream = new MemoryStream();
            var fileName = "namespace_name.Chart.txt";
            stream = assembly.GetManifestResourceStream(fileName);
            if (stream != null)
                editor.LoadEdits(stream);
        }


{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/Serialization.png)
