---
layout: post
title: Getting-Started
description: getting started
platform: xamarin
control: Essential-DocIO
documentation: ug
---

# Getting Started

The following steps demonstrate how to create a simple word document in a Xamarin.Forms project using Essential DocIO. You can also download the entire source code of this demo from [here](http://files2.syncfusion.com/Installs/v12.2.0.40/Samples/Xamarin/DocIO_GettingStarted.zip).

1. Create new Xamarin.Forms portable project.
2. Next, you need to reference Essential Studio components in your solution. 

DocIO is packaged as a portable class library so currently there is no way to add reference to it from within the Xamarin component store IDE interface. You would need to obtain the required assemblies either through the Xamarin component store web interface or from Syncfusion.com. Typically you would add reference to DocIO only in the PCL project of your application. The required assembly references are

```

Syncfusion.Compression.Portable.dll

Syncfusion.DocIO.Portable.dll



```

If you had already referenced one of our UI components (Chart, Gauge or Treemap) components from within the Xamarin component store IDE interface then the DocIO assembly has already been downloaded and available in your solution folder, you can then manually add references from that folder.



```

Components/syncfusionessentialstudio-version/lib/pcl/



```



A new Word document can be easily created from scratch by using the Essential DocIO library by instantiating a new instance of the WordDocument class. This class is the root node for all other nodes in the Document Object Model for Essential DocIO library. Using this DOM, you can add, edit, and remove content from documents by iterating elements.

You can ensure to preserve a Word document with at least a section and a paragraph, while creating a new blank document by invoking the EnsureMinimal method of WordDocument class. The following code example illustrates how to create a Word document with minimal content.

{% highlight c# %}

//Creates a new Word document instance.

WordDocument doc = new WordDocument();

//Adds one section and one paragraph to the document.

doc.EnsureMinimal();
{% endhighlight %}


You can add a new section at the end of a document by invoking the AddSection method of WordDocument class. The following code example illustrates how to add a new section to a Word document.

{% highlight c# %}

//Adds a new section to the document.

WSection section = doc.AddSection();
{% endhighlight %}


You can add a new paragraph at the end of section by invoking the AddParagraph method of WSection class; also, you can add a new table at the end of section by invoking the AddTable method of WSection class. The following code example illustrates how to add a new Paragraph and Table to a Word document.

{% highlight c# %}

//Adds a new Paragraph to the section.

IWParagraph para = section.AddParagraph();

//Adds a new Table to the section.

IWTable table = section.AddTable();

{% endhighlight %}

You can append text to a paragraph by invoking the AppendText method of WParagraph class.

The following code example illustrates how to append text to a Word document.

{% highlight c# %}

//Appends text to the paragraph.

paragraph.AppendText("Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.");
{% endhighlight %}


You can save a Word document by invoking the Save method of WordDocument class.

The following code example illustrates how to save a Word document.

{% highlight c# %}

//Saves the generated Word document.

MemoryStream stream = new MemoryStream();

doc.Save(stream, FormatType.Word2013);

//Releases the resources used by the WordDocument instance.

doc.Close();

{% endhighlight %}



![](Getting-Started_images/Getting-Started_img1.jpg)










