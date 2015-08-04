---
layout: post
title: Getting-Started
description: getting started	
platform: ios
control: Control Name undefined
documentation: ug
---

### Getting Started	

The following steps demonstrate how create a simple PDF document in a Xamarin.Forms project using Essential PDF. You can also download the entire source code of this demo from the link - [http://files2.syncfusion.com/Installs/v12.2.0.40/Samples/Xamarin/PDF_GettingStarted.zip](http://files2.syncfusion.com/Installs/v12.2.0.40/Samples/Xamarin/PDF_GettingStarted.zip)

1. Create a new Xamarin.Forms portable project.
2. Next, you need to reference Essential Studio components in your solution. 

Essential PDF is packaged as a portable class library so currently there is no way to add reference to it from within the Xamarin component store IDE interface. You would need to obtain the required assemblies either through the Xamarin component store web interface or from Syncfusion.com. Typically you would add reference to Essential PDF only in the PCL project of your application. The required assembly references are



```

Syncfusion.Compression.Portable.dll

Syncfusion.Pdf.Portable.dll



```

> ![C:/Users/ApoorvahR/Desktop/Note.png](Getting-Started_images/Getting-Started_img1.png)
{:.image }
_Note: If you had already referenced one of our UI components (Chart, Gauge or Treemap) components from within the Xamarin component store IDE interface then the DocIO assembly has already been downloaded and available in your solution folder, You can then manually add references from that folder._



```

Components/syncfusionessentialstudio-version/lib/pcl/



```

3. Use the following C# code to generate a simple PDF using Essential PDF



//Create a new PDF document.

PdfDocument document = new PdfDocument();



//Add a page

PdfPage page = document.Pages.Add();



//Creates Pdf graphics for the page

PdfGraphics graphics = page.Graphics;



//Creates a solid brush.

PdfBrush brush = new PdfSolidBrush(Color.Black);



//Sets the font.

PdfFont font = new PdfStandardFont(PdfFontFamily.Helvetica, fontSize);



//Draws the text.

graphics.DrawString("Lorem Ipsum is simply dummy text of the

printing and typesetting industry. Lorem Ipsum has been the

standard dummy text ever since the 1500s, when an unknown printer

took a galley of type and scrambled it to make a type specimen

book.", font, brush, new RectangleF(0,0, page.GetClientSize().

Width,200));



//Saves the document.

MemoryStream stream = new MemoryStream();

document.Save(stream);

document.Close(true);

```



![](Getting-Started_images/Getting-Started_img2.png)
{:.image }
![](Getting-Started_images/Getting-Started_img3.png)
{:.image }
![](Getting-Started_images/Getting-Started_img4.png)
{:.image }
![](Getting-Started_images/Getting-Started_img5.png)
{:.image }




