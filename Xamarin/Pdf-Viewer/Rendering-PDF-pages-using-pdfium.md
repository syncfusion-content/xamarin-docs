---
layout: post
title: Rendering PDF pages using pdfium in PDF Viewer Xamarin.Forms Android Platform | Syncfusion
description: PDF Viewer in Xamarin.Forms Android Platform supports rendering PDF pages using pdfium.
platform: xamarin
control: SfPdfViewer
documentation: UG
---

#Rendering PDF pages using pdfium in PDF Viewer Xamarin.Forms Android Platform

The PdfViewer allows using Pdfium to render the pages of a PDF document, which is a third-party open-source PDF rendering engine. By default, the PdfViewer uses native Android PDF rendering. However, using the Pdfium rendering engine will overcome the defects in the native Android PDF rendering.

##Creating Pdfium binding library

To use Pdfium in your application, the Pdfium binding library is needed. The Pdfium binding project can be created from the scratch using the following steps.

1.Download the pdfium-android-1.7.0.aar Android archive file from this link.
 
https://mvnrepository.com/artifact/com.github.barteksc/pdfium-android/1.7.0 

2.To create the binding project from this archive file refer to this link. 
https://developer.xamarin.com/guides/android/advanced_topics/binding-a-java-library/binding-an-aar/ 

3.Install the Xamarin.Android.Support.Compat dependency package in the project.

4.Compile the project to generate the Pdfium library.

##Using Pdfium binding library in the application project

Refer to the created binding library in your android project. 

Add a new class named `CustomPdfRenderer` to the android application project. This class must implement the [ICustomPdfRenderer](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.ICustomPdfRendererService.html#Syncfusion_SfPdfViewer_XForms_ICustomPdfRendererService_AlternatePdfRenderer) interface defined in the `Syncfusion.SfPdfViewer.XForms.Droid` and `Syncfusion.SfPdfViewer.XForms` namespace.

The entire CustomPdfRenderer class is given as follows. 

{% tabs %}
{% highlight c# %}

internal class CustomPdfRenderer : ICustomPdfRenderer
{
   internal PdfiumCore m_pdfiumCore;
   internal PdfDocument m_pdfDocument;
   internal int m_pageCount;
   internal Bitmap.Config m_bitmapConfig;
  
   /// <summary>
   /// Gets or sets the total page count of the PDF document.
   /// </summary>
   public int PageCount
   {
    get
    {
     return m_pageCount;
    }
    set
    {
     m_pageCount = value;
    }
   }
   
   /// <summary>
   /// Gets or sets the Bitmap.Config to render the bitmap from the PDF document.
   /// </summary>
   public Bitmap.Config BitmapConfig
   {
    get
    {
     return m_bitmapConfig;
    }
    set
    {
     m_bitmapConfig = value;
    }
   }

    /// <summary>
    /// Initializes the required object.
    /// </summary>
    /// <param name="context">Context of the application.</param>
    /// <param name="inputStream">PDF document stream.</param>
    public void Initialize(Context context, Stream inputStream)
    {
      if (inputStream == null)
      {
         throw new System.NullReferenceException("object reference is not set to an instance: inputStream");
      }
          
	  //Initializes the PdfiumCore instance.
      m_pdfiumCore = new PdfiumCore(context);
      byte[] byteArray = ReadBytes(inputStream);
      
	  if (m_pdfiumCore == null)
      {
       throw new System.NullReferenceException("object reference is not set to an instance: m_pdfiumCore");
      }
          
      //Creates the PdfDocument instance from the PDF byte array.
      m_pdfDocument = m_pdfiumCore.NewDocument(byteArray);
     
	  if (m_pdfDocument == null)
      {
       throw new System.NullReferenceException("object reference is not set to an instance: m_pdfDocument");
      }
  
      if (m_bitmapConfig == null)
      {
       m_bitmapConfig = Bitmap.Config.Rgb565;
      }
      
	  //Gets the total number of pages in the PDF document.
      m_pageCount = m_pdfiumCore.GetPageCount(m_pdfDocument);	    
      
	}
     
	 /// <summary>
     /// Converts the stream to byte array to render the PDF document using Pdfium renderer.
     /// </summary>
     /// <param name="inputStream">PDF document stream to convert into byte array.</param>
     /// <returns>byte array of PDF document</returns>
     private static byte[] ReadBytes(Stream input)
     {
        if (input.CanSeek)
        {
         input.Position = 0;
        }
       
	    byte[] buffer = new byte[16 * 1024];
		
        using (MemoryStream ms = new MemoryStream())
        {
         int read;
         while ((read = input.Read(buffer, 0, buffer.Length)) > 0)
         {
           ms.Write(buffer, 0, read);
         }
         return ms.ToArray();     
        }
      }
	  
      /// <summary>
      /// Renders the PDF page as a bitmap with specified page index.
      /// </summary>
      /// <param name="bitmap">Bitmap to render the content of the PDF page. </param>
      /// <param name="pageIndex">Index of the page in the PDF document being rendered.</param>
      /// <param name="pageWidth">Width of the page to be drawn on to the bitmap.</param>
      /// <param name="pageHeight">Height of the page to be drawn on to the bitmap.</param>
      public void Render(Bitmap bitmap, int pageIndex, int pageWidth, int pageHeight)
      {
        if (bitmap == null)
        {
           throw new System.NullReferenceException("object reference is not set to an instance: bitmap");
        }
			
        if (m_pdfiumCore == null)
        {
           throw new System.NullReferenceException("object reference is not set to an instance: m_pdfiumCore");
        }
        else if (m_pdfDocument == null)
        {
           throw new System.NullReferenceException("object reference is not set to an instance: m_pdfDocument");
        }
        else if (pageIndex < 0 && pageIndex > m_pageCount - 1)
        {
           throw new System.ArgumentOutOfRangeException("pageIndex", "Index was out of range. Must be non-negative and less than the size of the PageCount.");
        }
        else
        {
           //Sets the config of Bitmap format, we required to render the PDF pages.
           bitmap.SetConfig(m_bitmapConfig);
				
           //Opens the PDF page with the specified page index to render the page as a bitmap.
           m_pdfiumCore.OpenPage(m_pdfDocument, pageIndex);
				
           m_pdfiumCore.RenderPageBitmap(m_pdfDocument, bitmap, pageIndex, 0, 0, pageWidth, pageHeight);
        }
       }
		 
      /// <summary>
      /// Gets the size of the page with the provided index in the PDF document.
      ///</summary>
      /// <param name="pageIndex">Page index to the get page size.</param>
      /// <returns>Size of the page of PDF document.</returns>
      public Android.Util.Size GetPageSize(int pageIndex)
      {
        if (m_pdfiumCore == null)
        {
          throw new System.NullReferenceException("object reference is not set to an instance: m_pdfiumCore");
        }
        else if (m_pdfDocument == null)
        {
          throw new System.NullReferenceException("object reference is not set to an instance: m_pdfDocument");
        }
        else if (pageIndex < 0 && pageIndex > m_pageCount - 1)
        {
          throw new System.ArgumentOutOfRangeException("pageIndex", "Index was out of range. Must be non-negative and less than the size of the PageCount.");
        }
        else
        {
          //Opens the PDF page with specified index to get its size.
          m_pdfiumCore.OpenPage(m_pdfDocument, pageIndex);
				
          int pageHeight = m_pdfiumCore.GetPageHeightPoint(m_pdfDocument, pageIndex);
          int pageWidth = m_pdfiumCore.GetPageWidthPoint(m_pdfDocument, pageIndex);
          return new Android.Util.Size(pageWidth, pageHeight);
        }
       }
              
	    /// <summary>
        /// Renders the PDF page as a bitmap with the specified page index.
        /// </summary>
        /// <param name="bitmap">Bitmap to render the content of the PDF page. </param>
        /// <param name="pageIndex">Index of the page in the PDF document being rendered.</param>
        /// <param name="pageWidth">Width of the page to be drawn on to the bitmap.</param>
        /// <param name="pageHeight">Height of the page to be drawn on to the bitmap.</param>
        /// <param name="x">The x coordinate of the origin of the region to be rendered.</param>	
        /// <param name="y">The y coordinate of the origin of the region to be rendered.</param>
        public void Render(Bitmap bitmap, int pageIndex, int pageWidth, int pageHeight,  float xOffset= 0, float yOffset = 0)
        {
           if (bitmap == null)
           {
              throw new System.NullReferenceException("object reference is not set to an instance: bitmap");
           }
           
		   if (m_pdfiumCore == null)
           {
               throw new System.NullReferenceException("object reference is not set to an instance: m_pdfiumCore");
           }
           else if (m_pdfDocument == null)
           {
               throw new System.NullReferenceException("object reference is not set to an instance: m_pdfDocument");
           }
           else if (pageIndex < 0 && pageIndex > m_pageCount - 1)
           {
               throw new System.ArgumentOutOfRangeException("pageIndex", "Index was out of range. Must be non-negative and less than the size of the PageCount.");
           }
           else
           {
               //Sets the config of Bitmap format, we required to render the PDF pages
               bitmap.SetConfig(m_bitmapConfig);
               //Opens the PDF page with the specified page index to render the page as a bitmap.
               m_pdfiumCore.OpenPage(m_pdfDocument, pageIndex);
               m_pdfiumCore.RenderPageBitmap(m_pdfDocument, bitmap, pageIndex, xOffset, yOffset, pageWidth, pageHeight);
            }
        }
		
        /// <summary>
        /// Closes the initialized object to release memory.
        /// </summary>
        public void Close()
        {
           //Closes the created PdfDocument instance.
           m_pdfiumCore.CloseDocument(m_pdfDocument);
           //Disposes the PdfiumCore instance.
           m_pdfiumCore.Dispose();	
        }
    }			
{% endhighlight %}
{% endtabs %}

Regarding the above code example, there are two overloads of the `Render` method.

<table>
<tr>
<td>Render(Bitmap bitmap, int pageIndex, int pageWidth, int pageHeight)</td>
<td/>This overload renders the entire page specified by the pageIndex parameter. This method will be called when the page is not zoomed in. </td>
</tr>
<tr>
<td>Render(Bitmap bitmap, int pageIndex, int pageWidth, int pageHeight,  float xOffset = 0, float yOffset = 0)</td>
<td>When the page is zoomed in, the tile rendering is used in the PDF viewer to conserve memory. When the page is rendered using the tile rendering, this method will be called which renders only the portion of the page visible in the viewport of the device. </td>
</tr>
</table>

The [CustomPdfRenderer](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_CustomPdfRenderer) property should be assigned to the [AlternatePdfRenderer] (https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.ICustomPdfRendererService.html#Syncfusion_SfPdfViewer_XForms_ICustomPdfRendererService_AlternatePdfRenderer) property of the `CustomPdfRenderer` class as like in the following code sample,

{% tabs %}
{% highlight c# %}
pdfViewer.CustomPdfRenderer = DependencyService.Get<ICustomPdfRendererService>().AlternatePdfRenderer;
{% endhighlight %}
{% endtabs %}

N>At present, this feature is available only on the Android Platform.