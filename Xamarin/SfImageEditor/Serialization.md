---
layout : post
title : Serialization in Syncfusion SfImageEditor control in Xamarin.Forms
description : Learn how to serialize and deserialize edited shapes  in ImageEditor for Xamarin.Forms
platform : Xamarin.Forms
control : ImageEditor
documentation : ug
---

# Serialization And Deserialization
 ImageEditor provides support to serialize and deserialize the shapes(Circle,Arrow,Rectangle), free hand drawing,Text and Toolbar settings. Save the current state of the Image Editor and Load it back when its needed.

## Serialization
  To serialize the shapes like circle,arrow,rectangle,text ,freehand drawing and toolbar settings by calling SaveEdits() method.Serialized object will be return in the form of JSON stream.

{% tabs %}

{% highlight C# %}
    
	 SfImageEditor editor = new   SfImageEditor();
	 Stream stream=editor.SaveEdits();
     this.Content = editor;
    
	
{% endhighlight %}

{% endtabs %}

   convert the stream into string and save as .txt format file and set as Embedded  resource in Xamarin.Forms.Text file like this
  [Chart.txt](http://www.syncfusion.com/downloads/support/directtrac/general/txt/Chart677841499.txt)
       


## Deserialization
   To deserialize serialized objects by calling LoadEdits(stream) method .Deserialize the object by using loaded JSON stream.

{% tabs %}

{% highlight C# %}
       
	  SfImageEditor editor;
        public MainPage()
        {
            InitializeComponent();
            editor = new SfImageEditor();
            this.Content = editor;
            DelayActionAsync(1500, LoadStream);
        }
        public async Task DelayActionAsync(int delay, Action action)
        {
            await Task.Delay(delay);
            action();
        }

        void LoadStream()
        {
            var assembly = typeof(App).GetTypeInfo().Assembly;
            Stream stream = new MemoryStream();
            var fileName = "SerializationUG.Chart.txt";
            stream = assembly.GetManifestResourceStream(fileName);
            if (stream != null)
                editor.LoadEdits(stream);

        }

{% endhighlight %}

{% endtabs %}

![SfImageEditor](ImageEditor_images/Serialization.png)





