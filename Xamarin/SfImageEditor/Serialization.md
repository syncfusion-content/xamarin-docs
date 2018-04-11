---
layout : post
title : Serialization in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to serialize and deserialize edited shapes  in ImageEditor for Xamarin.Forms
platform : xamarin.forms
control : ImageEditor
documentation : ug
---

# Serialization And Deserialization
 ImageEditor provides support to serialize and deserialize the shapes(Circle, Arrow, Rectangle), free hand drawing, Text and Toolbar settings. Save the current state of the Image Editor and Load it back when its needed.

## Serialization
 SaveEdits() method used to serialize the current edits of shapes. Serialized object will be return in the form of JSON stream.

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

 you can save stream into .txt format file.if you saved as .txt format file to deserialize the shapes then set as Embedded resource in project.
  
  Please find sample text file shown below
  
  [Chart.txt](http://www.syncfusion.com/downloads/support/directtrac/general/txt/Chart677841499.txt)
       
## Deserialization
   LoadEdits() method used to deserialize the shapes.

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





