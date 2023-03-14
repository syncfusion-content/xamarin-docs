---
layout: post
title: Rendering PDF pages using pdfium in Xamarin Pdf Viewer | Syncfusion
description: Learn here all about Rendering PDF pages using pdfium support in Syncfusion Xamarin Pdf Viewer (SfPdfViewer) control and more.
platform: xamarin
control: SfPdfViewer
documentation: UG
---

# Rendering PDF pages using pdfium in Xamarin Pdf Viewer (SfPdfViewer)

The [Xamarin PDF Viewer](https://www.syncfusion.com/xamarin-ui-controls/xamarin-pdf-viewer) allows using Pdfium to render the pages of a PDF document, which is a third-party open-source PDF rendering engine. 

## Rendering PDF pages using Pdfium in Android platform
By default, the PdfViewer uses native Android PDF rendering. However, using the Pdfium rendering engine will overcome the defects in the native Android PDF rendering.

### Creating Pdfium binding library

To use Pdfium in your application, the Pdfium binding library is needed. The Pdfium binding project can be created from the scratch using the following steps.

1.Download the pdfium-android-1.7.0.aar Android archive file from this link.
<https://mvnrepository.com/artifact/com.github.barteksc/pdfium-android/1.7.0>
2.To create the binding project from this archive file refer to this link. 
<https://developer.xamarin.com/guides/android/advanced_topics/binding-a-java-library/binding-an-aar/>
3.Install the `Xamarin.Android.Support.Compat` dependency package in the project.
4.Compile the project to generate the Pdfium library.

### Using Pdfium binding library in the application project

Refer to the created binding library in your android project. Add a new class named `CustomPdfRenderer` to the android application project. This class must implement the [ICustomPdfRenderer](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.ICustomPdfRendererService.html#Syncfusion_SfPdfViewer_XForms_ICustomPdfRendererService_AlternatePdfRenderer) interface defined in the `Syncfusion.SfPdfViewer.XForms.Droid` and `Syncfusion.SfPdfViewer.XForms` namespace.
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
<td>This overload renders the entire page specified by the pageIndex parameter. This method will be called when the page is not zoomed in.</td>
</tr>
<tr>
<td>Render(Bitmap bitmap, int pageIndex, int pageWidth, int pageHeight,  float xOffset = 0, float yOffset = 0)</td>
<td>When the page is zoomed in, the tile rendering is used in the PDF viewer to conserve memory. When the page is rendered using the tile rendering, this method will be called which renders only the portion of the page visible in the viewport of the device.</td>
</tr>
</table>

The [CustomPdfRenderer](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.SfPdfViewer.html#Syncfusion_SfPdfViewer_XForms_SfPdfViewer_CustomPdfRenderer) property should be assigned to the [AlternatePdfRenderer](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfPdfViewer.XForms.ICustomPdfRendererService.html#Syncfusion_SfPdfViewer_XForms_ICustomPdfRendererService_AlternatePdfRenderer) property of the `CustomPdfRenderer` class as like in the following code sample,

{% tabs %}
{% highlight c# %}
pdfViewer.CustomPdfRenderer = DependencyService.Get<ICustomPdfRendererService>().AlternatePdfRenderer;
{% endhighlight %}
{% endtabs %}

## Rendering PDF pages using Pdfium renderer in UWP platform
The  [SfPdfViewer](https://help.syncfusion.com/xamarin/pdf-viewer/overview) allows users to render the PDF pages using the PDFium rendering engine. The `ICustomPdfRenderer` interface defines the methods and properties that provide the necessary values and perform the necessary operations to render the pages using the PDFium library. The user needs to add a class to their application that must implement this interface and assign an instance of this class to the Renderer property of the SfPdfViewer.
The PDF page rendering using the PDFium rendering engine is shown in detail as follows.

### Loading the PDFium library
To render the PDF pages using PDFium, the pdfium.dll library for the corresponding platform configuration (x86, x64, or arm64) must be loaded in the application project. The library can either be loaded from a file path or it can be added as an embedded resource in the application project.

#### Loading the library from the file path
Load the library from the file path using the LoadLibrary external method while initializing the custom renderer.

{% tabs %}
{% highlight c# %}

/// Initializes the third-party PDF renderer library.
public void InitLibrary()
        {
            if (pdfiumLibrary != IntPtr.Zero)
            {
                return;
            }
            string executingNamespace = "PdfViewerSample.UWP.";
            string pdfiumResourcePath = "Pdfium.";
            string dirName = Path.Combine(Environment.GetFolderPath(Environment.SpecialFolder.LocalApplicationData), "Pdfium");
            if (System.IntPtr.Size == 8)
            {
                if (Environment.GetEnvironmentVariable("PROCESSOR_ARCHITECTURE") != "ARM64")
                {
                    pdfiumResourcePath += @"x64.pdfium.dll";
                    dirName += @"\x64\";
                }
                else
                {
                    pdfiumResourcePath += @"arm64.pdfium.dll";
                    dirName += @"\arm64\";
                }
            }
            else
            {
                pdfiumResourcePath += @"x86.pdfium.dll";
                dirName += @"\x86\";
            }
            if (!Directory.Exists(dirName))
                Directory.CreateDirectory(dirName);
            string dllPath = System.IO.Path.Combine(dirName, "pdfium.dll");
            if (!File.Exists(dllPath))
            {
                var assembly = typeof(CustomRenderer.UWP.App).GetTypeInfo().Assembly;
                using (Stream stream = assembly.GetManifestResourceStream(executingNamespace + pdfiumResourcePath))
                {
                    using (Stream outFile = File.Create(dllPath))
                    {
                        byte[] buffer = new byte[stream.Length];
                        while (true)
                        {
                            int numBytesToRead = stream.Read(buffer, 0, buffer.Length);
                            if (numBytesToRead < 1)
                                break;
                            outFile.Write(buffer, 0, numBytesToRead);
                        }
                        System.Array.Clear(buffer, 0, buffer.Length);
                        buffer = null;
                    }
                }
            }
            pdfiumLibrary = LoadLibrary(dllPath);
            if (pdfiumLibrary == IntPtr.Zero)
            {
                throw new Exception("Failed to load pdfium.dll");
            }
            else
            {
                try
                {
                    FPDF_InitLibrary();
                }
                catch(Exception)
                {
                    throw new Exception("Pdfium library failed to initilize");
                }
            }
        }
        
{% endhighlight %}
{% endtabs %}

### Adding the library as Embedded Resource

Add the pdfium.dll file to the project with BuildAction as Embedded Resource.

### Implementing the IPdfRenderer interface

Add a class to the application project and implement the `IPdfRenderer` interface in the class.

#### Implementing the IPdfRenderer interface

In the class, define the external methods for the necessary operations such as initializing the PDFium library, rendering the PDF pages, obtaining the page size, and more. The pdfium.dll library provides implementations for these external methods.

Each external method definition must be preceded by the DllImport attribute.

{% tabs %}
{% highlight c# %}

[UnmanagedFunctionPointer(CallingConvention.Cdecl)]
        public delegate int FPDF_GetBlockDelegate(IntPtr param, uint position, IntPtr buffer, uint size);
        public static readonly FPDF_GetBlockDelegate _getBlockDelegate = FPDF_GetBlock;
        [DllImport("kernel32", SetLastError = true, CharSet = CharSet.Auto)]
        private static extern IntPtr LoadLibrary([MarshalAs(UnmanagedType.LPTStr)] string lpFileName);
        [DllImport("pdfium.dll", EntryPoint = "FPDF_InitLibrary")]
        public static extern void FPDF_InitLibrary();
        [DllImport("pdfium.dll", EntryPoint = "FPDF_DestroyLibrary")]
        public static extern void FPDF_DestroyLibrary();
        [DllImport("pdfium.dll")]
        public static extern int FPDF_GetPageCount(IntPtr document);
        [DllImport("pdfium.dll", CharSet = CharSet.Ansi)]
        public static extern IntPtr FPDF_LoadDocument(string path, string password);
        [DllImport("pdfium.dll")]
        public static extern int FPDF_GetPageSizeByIndex(IntPtr document, int page_index, out double width, out double height);
        [DllImport("pdfium.dll")]
        public static extern IntPtr FPDFBitmap_CreateEx(int width, int height, int format, IntPtr first_scan, int stride);
        [DllImport("pdfium.dll")]
        public static extern void FPDFBitmap_FillRect(IntPtr bitmapHandle, int left, int top, int width, int height, uint color);
        [DllImport("pdfium.dll")]
        public static extern IntPtr FPDFBitmap_Destroy(IntPtr bitmapHandle);
        [DllImport("pdfium.dll")]
        public static extern void FPDF_RenderPageBitmap(IntPtr bitmapHandle, IntPtr page, int start_x, int start_y, int size_x, int size_y, int rotate, FPDF flags);
        [DllImport("pdfium.dll")]
        public static extern IntPtr FPDF_LoadPage(IntPtr document, int page_index);
        [DllImport("pdfium.dll")]
        public static extern IntPtr FPDF_ClosePage(IntPtr page);
        [DllImport("pdfium.dll")]
        public static extern int FPDF_CloseDocument(IntPtr doc);
        [DllImport("pdfium.dll", CharSet = CharSet.Ansi)]
        public static extern IntPtr FPDF_LoadCustomDocument([MarshalAs(UnmanagedType.LPStruct)] FPDF_FILEACCESS access, string password);
 [DllImport("Pdfium.dll")] 
        public object AlternatePdfRenderer => this;
        private IntPtr pdfiumLibrary;
        [StructLayout(LayoutKind.Sequential)]
        public class FPDF_FILEACCESS
        {
            public uint m_FileLen;
            public IntPtr m_GetBlock;
            public IntPtr m_Param;
        }
        private static int FPDF_GetBlock(IntPtr param, uint position, IntPtr buffer, uint size)
        {
            Stream stream = fileStream;
            if (stream == null)
                return 0;
            byte[] managedBuffer = new byte[size];
            stream.Position = position;
            int read = stream.Read(managedBuffer, 0, (int)size);
            if (read != size)
                return 0;
            Marshal.Copy(managedBuffer, 0, buffer, (int)size);
            return 1;
        }  
        [Flags]
        public enum FPDF
        {
            ANNOT = 0x01,
            LCD_TEXT = 0x02,
            NO_NATIVETEXT = 0x04,
            GRAYSCALE = 0x08,
            DEBUG_INFO = 0x80,
            NO_CATCH = 0x100,
            RENDER_LIMITEDIMAGECACHE = 0x200,
            RENDER_FORCEHALFTONE = 0x400,
            PRINTING = 0x800,
            REVERSE_BYTE_ORDER = 0x10,
        }


{% endhighlight %}
{% endtabs %}
#### Implement the LoadDocument method

The following code sample shows implementation of `LoadDocument` method. It will be called every time when a PDF is Loaded.

{% tabs %}
{% highlight c# %}
/// Loads the given PDF stream into the third-party PDF renderer and returns the document pointer.
/// <param name="inputStream">The stream of the PDF document to be loaded.</param>
/// <param name="password">The password for the encrypted document.</param>
public static Stream fileStream = null;
        public IntPtr LoadDocument(Stream fileInputStream, string password)
        {
            fileStream = fileInputStream;
            FPDF_FILEACCESS access = new FPDF_FILEACCESS
            {
                m_FileLen = (uint)fileStream.Length,
                m_GetBlock = Marshal.GetFunctionPointerForDelegate(_getBlockDelegate),
                m_Param = (IntPtr)2,
            };
            IntPtr document = FPDF_LoadCustomDocument(access, password);
            if (document == IntPtr.Zero)
            {
                throw new Exception("Document cannot be loaded");
            }
            return document;
        }


{% endhighlight %}
{% endtabs %}

#### Implement the GetPageCount method

The `GetPageCount` method must return the total page count by calling the external method defined earlier. When a new PDF is loaded, the previous PDF must be closed, and the page count should be reset.

{% tabs %}
{% highlight c# %}
/// Gets the page count of the given PDF document.
/// <param name="document">The pointer to the PDF document.</param>
public int GetPageCount(IntPtr document)
        {
            if (document != IntPtr.Zero)
            {
                pageCount = FPDF_GetPageCount(document);
                return pageCount;
            }
            else
            {
                return 0;
            }
        }

{% endhighlight %}
{% endtabs %}

#### Implement the GetPageSize method

The `GetPageSize` method must call the external method and return the size of the PDF page corresponding to the given index.

{% tabs %}
{% highlight c# %}
/// Gets the page size of the given page index.
/// <param name="document">The pointer to the PDF document.</param>
/// <param name="pageIndex">The page index to get the size. This is a 0 based index.</param>
public Windows.Foundation.Size GetPageSize(IntPtr document, int pageIndex)
        {
            if (document == IntPtr.Zero)
            {
                throw new ArgumentNullException("document");
            }
            if (pageIndex < 0 || pageIndex > pageCount)
            {
                throw new ArgumentOutOfRangeException("pageIndex");
            }
            double pageHeight = 0, pageWidth = 0;
            FPDF_GetPageSizeByIndex(document, pageIndex, out pageWidth, out pageHeight);
            Windows.Foundation.Size size;
            size.Width = (int)pageWidth;
            size.Height = (int)pageHeight;
            return size;
        }

{% endhighlight %}
{% endtabs %}

#### Render the PDF page

The `RenderPageBitmap` method must call the external methods which render the PDF page and return the rendered SoftwareBitmap.

{% tabs %}
{% highlight c# %}

/// Renders the page of the specified index and returns the rendered bitmap.
/// <param name="document">The pointer to the PDF document.</param>
/// <param name="pageIndex">The page index to get the size. This is a 0 based index.</param>
/// <param name="pageWidth">Width of the page to be rendered.</param>
/// <param name="pageHeight">Height of the page to be rendered.</param>
public SoftwareBitmap RenderPageBitmap(IntPtr document, int pageIndex, int pageWidth, int pageHeight)
        {
            if (document == IntPtr.Zero)
            {
                throw new ArgumentNullException("document");
            }
            if (pageIndex < 0 || pageIndex > pageCount)
            {
                throw new ArgumentOutOfRangeException("pageIndex");
            }
            var page = FPDF_LoadPage(document, pageIndex);
            byte[] buffer = new byte[pageWidth * pageHeight * 4];
            unsafe
            {
                fixed (byte* p = buffer)
                {
                    IntPtr createdpages = FPDFBitmap_CreateEx(pageWidth, pageHeight, 4, (IntPtr)p, pageWidth * 4);
                    uint background = 0xFFFFFFFF;
                    FPDFBitmap_FillRect(createdpages, 0, 0, pageWidth, pageHeight, background);
                    FPDF_RenderPageBitmap(createdpages, page, 0, 0, pageWidth, pageHeight, 0, FPDF.ANNOT);
                    FPDFBitmap_Destroy(createdpages);
                    FPDF_ClosePage(page);
                }
            }
            SoftwareBitmap softwareBitmap = new SoftwareBitmap(BitmapPixelFormat.Bgra8, pageWidth, pageHeight, BitmapAlphaMode.Straight);
            softwareBitmap.CopyFromBuffer(buffer.AsBuffer());
            return softwareBitmap;
        }

{% endhighlight %}
{% endtabs %}

#### Close the PDF document

When a new PDF is to be loaded, the previous PDF must be closed, implementation of `CloseDocument` method is shown below.

{% tabs %}
{% highlight c# %}

/// Closes the given PDF document.
/// <param name="document">The pointer to the PDF document.</param>
public void CloseDocument(IntPtr document)
        {
            if (document != IntPtr.Zero)
            {
                FPDF_CloseDocument(document);
            }
        }

{% endhighlight %}
{% endtabs %}

### Setting the Renderer property

Set the `CustomPdfRenderer` property to a new instance of the class created above. If the CustomPdfRenderer  property is not set, the pages are rendered using the default rendering of a SfPdfViewerControl.

{% tabs %}
{% highlight c# %}

/// Provides functionality to render PDF pages using third-party PDF renderers.
pdfViewer.CustomPdfRenderer = DependencyService.Get<ICustomPdfRendererService>().AlternatePdfRenderer;

{% endhighlight %}
{% endtabs %}

## PDFium renderer sample
The sample that illustrates loading a PDF using the Pdfium renderer in Android and UWP can be downloaded from the link below.

https://www.syncfusion.com/downloads/support/directtrac/general/ze/PdfiumDemoSample-2002924505

N>At present, this feature is available on the Android and UWP Platforms.

N>You can also explore our [Xamarin.Forms PDF Viewer example](https://github.com/syncfusion/xamarin-demos/tree/master/Forms/PdfViewer) to knows the functionalities of each feature.
