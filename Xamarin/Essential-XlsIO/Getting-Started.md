---
layout: post
title: Getting-Started
description: getting started
platform: ios
control: Control Name undefined
documentation: ug
---

### Getting Started

The following steps demonstrate how to create a simple excel document in a Xamarin.Forms project using Essential XlsIO. You can also download the entire source code of this demo from the link - [http://files2.syncfusion.com/Installs/v12.2.0.40/Samples/Xamarin/XlsIO_GettingStarted.zip](http://files2.syncfusion.com/Installs/v12.2.0.40/Samples/Xamarin/XlsIO_GettingStarted.zip)

1. Create new Xamarin.Forms portable project.
2. Next, you need to reference Essential Studio components in your solution. 

XlsIO is packaged as a portable class library so currently there is no way to add reference to it from within the Xamarin component store IDE interface. You would need to obtain the required assemblies either through the Xamarin component store web interface or from Syncfusion.com. Typically you would add reference to XlsIO only in the PCL project of your Xamarin.Forms application. The required assembly references are



```

Syncfusion.Compression.Portable.dll

Syncfusion.XlsIO.Portable.dll



```

> ![C:/Users/ApoorvahR/Desktop/Note.png](Getting-Started_images/Getting-Started_img1.png)
{:.image }
_Note: If you had already referenced one of our UI components (Chart, Gauge or TreeMap) components from within the Xamarin component store IDE interface then the XlsIO assembly has already been downloaded and available in your solution folder, you can then manually add references from that folder._

```

Components/syncfusionessentialstudio-version/lib/pcl/



```

3. Use the following C# code to generate a simple excel file using Essential XlsIO

<table>
<tr>
<td>
<br>//Instantiate excel engineExcelEngine excelEngine = new ExcelEngine();//Excel applicationIApplication application = excelEngine.Excel;application.DefaultVersion = ExcelVersion.Excel2013;//A new workbook is created.[Equivalent to creating a new workbook in MS Excel]//The new workbook will have 1 worksheetIWorkbook workbook = application.Workbooks.Create(1);//The first worksheet object in the worksheets collection is accessed.IWorksheet sheet = workbook.Worksheets[0];sheet.Range["A1"].Text = "Hello World!";workbook.Version = ExcelVersion.Excel2013;//Saving workbook as streamMemoryStream stream = new MemoryStream();workbook.SaveAs(stream);//Closing workbookworkbook.Close();//Disposing excel engineexcelEngine.Dispose();</td></tr>
<tr>
<td>
</td></tr>
</table>


![](Getting-Started_images/Getting-Started_img2.png)
{:.image }












