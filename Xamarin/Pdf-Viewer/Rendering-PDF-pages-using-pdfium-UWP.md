---
layout: post
title: Rendering PDF pages using pdfium in Xamarin Pdf Viewer | Syncfusion
description: Learn here all about Rendering PDF pages using pdfium support on UWP platform in Syncfusion Xamarin Pdf Viewer (SfPdfViewer) control and more.
platform: xamarin
control: SfPdfViewer
documentation: UG
---
# Render PDF Pages using the PDFium renderer in UWP

The [Xamarin PDF Viewer](https://www.syncfusion.com/xamarin-ui-controls/xamarin-pdf-viewer) allows users to render the PDF pages using the PDFium rendering engine. The ICustomPdfRenderer interface defines the methods and properties that provide the necessary values and perform the necessary operations to render the pages using the PDFium library. The user needs to add a class to their application that must implement this interface and assign an instance of this class to the CustomPdfRenderer property of the SfPdfViewer as explained [here](https://help.syncfusion.com/xamarin/pdf-viewer/rendering-pdf-pages-using-pdfium).

The PDF page rendering using the PDFium rendering engine is shown in detail as follows.

## Loading the PDFium library

To render the PDF pages using PDFium, the pdfium.dll library for the corresponding platform configuration (x86, x64, or arm64) must be loaded in the application project. The library can either be loaded from a file path or it can be added as an embedded resource in the application project.

### Loading the library from the file path
The library files for each platform (x86, x64, or arm64) could be placed inside the application project in separate folders. Load the library from the file path using the `LoadLibrary` external method while initializing the custom renderer. 

{% tabs %}
{% highlight c# %}
        // Initializes the third-party PDF renderer library.
        public void InitLibrary()
        {
            if (pdfiumLibrary != IntPtr.Zero)
            {
                return;
            }
            // Namespace of the current application
            string executingNamespace = "PdfViewerSample.UWP.";
            // Folder in Application where the libraries are placed.
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

N>The namespace name and resource path in the above code is provided for illustration purpose. Please change them accordingly.

## Adding the library as Embedded Resource

Add the pdfium.dll file to the project with BuildAction as Embedded Resource.

## Implementing the IPdfRenderer interface

Add a class to the application project and implement the `IPdfRenderer` interface in the class.

### Add definitions of the external methods

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
### Implement the LoadDocument method

The following code sample shows implementation of `LoadDocument` method. It will be called every time when a PDF is Loaded.

{% tabs %}
{% highlight c# %}
        // Loads the given PDF stream into the third-party PDF renderer and returns the document pointer.
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

### Implement the GetPageCount method

The `GetPageCount` method must return the total page count by calling the external method defined earlier. When a new PDF is loaded, the previous PDF must be closed, and the page count should be reset.

{% tabs %}
{% highlight c# %}
        // Gets the page count of the given PDF document.
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

### Implement the GetPageSize method

The `GetPageSize` method must call the external method and return the size of the PDF page corresponding to the given index.

{% tabs %}
{% highlight c# %}
        // Gets the page size of the given page index.
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

### Render the PDF page

The `RenderPageBitmap` method must call the external methods which render the PDF page and return the rendered SoftwareBitmap.

{% tabs %}
{% highlight c# %}
        // Renders the page of the specified index and returns the rendered bitmap
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

### Close the PDF document

When a new PDF is to be loaded, the previous PDF must be closed, implementation of `CloseDocument` method is shown below.

{% tabs %}
{% highlight c# %}
        // Closes the given PDF document.
        public void CloseDocument(IntPtr document)
        {
            if (document != IntPtr.Zero)
            {
                FPDF_CloseDocument(document);
            }
        }

{% endhighlight %}
{% endtabs %}