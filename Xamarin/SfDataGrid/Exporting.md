---
layout: post
title: Exporting | SfDataGrid | Xamarin | Syncfusion
description: How to export a SfDataGrid to excel and pdf and it's customizations.
platform: xamarin.iOS
control: SfDataGrid
documentation: ug
---

# Exporting

This section explains you how to export the SfDataGrid to Excel and PDF file and about the customizations that can be done while exporting. 

SfDataGrid provides support for exporting the data to Excel and PDF with several customization options like custom appearance, excluding specific columns, excluding headers, setting custom row height, setting custom column width, etc. It also provides support for Grouping, Filtering and Sorting when exporting.

In order to use export to Excel and export to PDF functionalities of SfDataGrid, add the required assembly references to your application as discussed in the [Assembly deployment](/xamarin/sfdatagrid/getting-started#assembly-deployment) section.


## Export to Excel

You can export data to Excel by using the `ExportToExcel` method by passing the SfDataGrid as an argument. The following code example illustrates exporting data to Excel using the ExportToExcel Method.

{% highlight c# %}
private void ExportToExcel()
{
    DataGridExcelExportingController excelExport = new DataGridExcelExportingController ();
    var excelEngine = excelExport.ExportToExcel (this.dataGrid);
    var workbook = excelEngine.Excel.Workbooks [0];
    MemoryStream stream = new MemoryStream ();
    workbook.SaveAs (stream);
    workbook.Close ();
    excelEngine.Dispose ();

    if (Device.OS == TargetPlatform.WinPhone || Device.OS == TargetPlatform.Windows)
        DependencyService.Get<ISaveWindowsPhone> ().Save ("DataGrid.xlsx", "application/msexcel", stream);
    else
        DependencyService.Get<ISave> ().Save ("DataGrid.xlsx", "application/msexcel", stream);
} 
{% endhighlight %}

### Exporting Options

You can also export data to Excel with various customizing options while exporting the SfDataGrid by passing the grid and [DataGridExcelExportingOption](http://help.syncfusion.com/cr/cref_files/xamarin/sfgridconverter/Syncfusion.SfGridConverter.XForms~Syncfusion.SfDataGrid.XForms.Exporting.DataGridExcelExportingOption.html) as arguments to the ExportToExcel method. The following code example illustrates this.

{% highlight c# %}
DataGridExcelExportingController excelExport = new DataGridExcelExportingController ();
DataGridExcelExportingOption exportOption = new DataGridExcelExportingOption ();
exportOption.ExportColumnWidth = false;
exportOption.DefaultColumnWidth = 150;
var excelEngine = excelExport.ExportToExcel (this.dataGrid, exportOption); 
{% endhighlight %}

SfDataGrid provides you with several [properties in DataGridExcelExportingOption](http://help.syncfusion.com/cr/cref_files/xamarin/sfgridconverter/Syncfusion.SfGridConverter.XForms~Syncfusion.SfDataGrid.XForms.Exporting.DataGridExcelExportingOption_properties.html) class to customize the grid while exporting it to Excel. 

### Events

The SfDataGrid provides you the following Events for exporting to Excel:

* [RowExporting](http://help.syncfusion.com/cr/cref_files/xamarin/sfgridconverter/Syncfusion.SfGridConverter.XForms~Syncfusion.SfDataGrid.XForms.Exporting.DataGridExcelExportingController~RowExporting_EV.html) – This Event is raised while exporting a row at the execution time before the row is exported.
* [CellExporting](http://help.syncfusion.com/cr/cref_files/xamarin/sfgridconverter/Syncfusion.SfGridConverter.XForms~Syncfusion.SfDataGrid.XForms.Exporting.DataGridExcelExportingController~CellExporting_EV.html) – This Event is raised while exporting a cell at the execution time before the cell is exported.

#### RowExporting

The [DataGridRowExcelExportingEventHandler](http://help.syncfusion.com/cr/cref_files/xamarin/sfgridconverter/Syncfusion.SfGridConverter.XForms~Syncfusion.SfDataGrid.XForms.Exporting.DataGridRowExcelExportingEventHandler.html) delegate allows you to customize the styles for record rows and group caption rows. The `RowExporting` event is triggered with [DataGridRowExcelExportingEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin/sfgridconverter/Syncfusion.SfGridConverter.XForms~Syncfusion.SfDataGrid.XForms.Exporting.DataGridRowExcelExportingEventArgs.html) that contains the following properties:

* Range – Specifies the Excel range to be exported. It provides full access to the exporting cell in Excel.
* Record – Gets the collection of underlying data objects that are exported.
* RowType – Specifies the row type by using `ExportRowType` Enum. You can use this property to check the row type and apply different styles based on the row type.
* Worksheet – Sets the Worksheet properties such as sheet protection, gridlines, and so on. 

You can use this event to customize the properties of the GridRows that are exported to excel. The following code example illustrates how to change the background color of the record rows and caption summary rows while exporting.

{% highlight c# %}
//HandlingRowExportingEvent for exporting to excel
DataGridExcelExportingController excelExport = new DataGridExcelExportingController ();
excelExport.RowExporting += excelExport_RowExporting; 

void excelExport_RowExporting (object sender, DataGridRowExcelExportingEventArgs e)
{
    if (e.RowType == ExportRowType.Record) {
        if ((e.Record.Data as OrderInfo).IsClosed)
            e.Range.CellStyle.FillBackground = Syncfusion.XlsIO.ExcelKnownColors.Yellow;
        else
            e.Range.CellStyle.FillBackground = Syncfusion.XlsIO.ExcelKnownColors.LightGreen;
    }

    if (e.RowType == ExportRowType.CaptionSummary) {
        e.Range.CellStyle.FillBackground = Syncfusion.XlsIO.ExcelKnownColors.Grey_25_percent;
    }
}
{% endhighlight %}

#### CellExporting

The [DataGridCellExcelExportingEventHandler](http://help.syncfusion.com/cr/cref_files/xamarin/sfgridconverter/Syncfusion.SfGridConverter.XForms~Syncfusion.SfDataGrid.XForms.Exporting.DataGridCellExcelExportingEventHandler.html) delegate allows you to customize the styles for header cells, record cells and group caption cells. The `CellExporting` event is triggered with [DataGridCellExcelExportingEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin/sfgridconverter/Syncfusion.SfGridConverter.XForms~Syncfusion.SfDataGrid.XForms.Exporting.DataGridCellExcelExportingEventArgs.html) that contains the following properties:

* CellType – Specifies the cell type by using ExportCellType Enum. You can use this property to check the cell type and apply different cell styles based on the cell type.
* CellValue – Contains the actual value that is exported to the Excel. You can use this value to apply formatting in Excel using Range property.
* ColumnName – Specifies the Column Name (MappingName) of the exporting cell. You can apply formatting for a particular column by checking the ColumnName.
* Handled – Determines whether the cell is exported to Excel or not.
* Range – Specifies the Excel range to be exported. It provides full access to the exporting cell in Excel.
* Record – Gets the collection of underlying data objects that are exported. 

You can use this event to customize the properties of the GridCells that are exported to excel. The following code example illustrates how to customize the background color, Foreground color and CellValue of the header cells, record cells and caption summary cells while exporting.

{% highlight c# %}
//HandlingCellExportingEvent for exporting to Excel
DataGridExcelExportingController excelExport = new DataGridExcelExportingController ();
excelExport.CellExporting += excelExport_CellExporting;  

void excelExport_CellExporting(object sender, DataGridCellExcelExportingEventArgs e)
{
    if (e.CellType == ExportCellType.HeaderCell) {
        e.Range.CellStyle.FillBackground = Syncfusion.XlsIO.ExcelKnownColors.Blue;
        e.Range.CellStyle.FillForeground = Syncfusion.XlsIO.ExcelKnownColors.White;
        e.CellValue = "HeaderCell";
    }

    if (e.CellType == ExportCellType.RecordCell) {
        e.Range.CellStyle.FillBackground = Syncfusion.XlsIO.ExcelKnownColors.Yellow;
        e.Range.CellStyle.FillForeground = Syncfusion.XlsIO.ExcelKnownColors.Black;
        if (e.CellValue is string)
            e.CellValue = "RecordCell";
    }

    if (e.CellType == ExportCellType.GroupCaptionCell) {
        e.Range.CellStyle.FillBackground = Syncfusion.XlsIO.ExcelKnownColors.Grey_25_percent;
        e.Range.CellStyle.FillForeground = Syncfusion.XlsIO.ExcelKnownColors.Blue;
        e.CellValue = "CaptionSummary";
    }
}
{% endhighlight %}


## Export to Pdf

You can Export data to PDF by using the ExportToPdf method by passing the SfDataGrid as an argument. The following code example illustrates exporting data to PDF using the ExportToPdf Method.

{% highlight c# %}
private void ExportToPdf()
{
    DataGridPdfExportingController pdfExport = new DataGridPdfExportingController ();
    MemoryStream stream = new MemoryStream ();
    var doc = pdfExport.ExportToPdf (this.dataGrid);
    doc.Save (stream);
    doc.Close (true);

    if (Device.OS == TargetPlatform.WinPhone || Device.OS == TargetPlatform.Windows)
        DependencyService.Get<ISaveWindowsPhone> ().Save ("DataGrid.pdf", "application/pdf", stream);
    else
        DependencyService.Get<ISave> ().Save ("DataGrid.pdf", "application/pdf", stream);
}
{% endhighlight %}

### Exporting Options

You can also Export data to PDF with various customizing options while exporting the SfDataGrid by passing the grid and [DataGridPdfExportingOption](http://help.syncfusion.com/cr/cref_files/xamarin/sfgridconverter/Syncfusion.SfGridConverter.XForms~Syncfusion.SfDataGrid.XForms.Exporting.DataGridPdfExportOption.html) as arguments to the ExportToPdf method. The following code example illustrates this.

{% highlight c# %}
DataGridPdfExportingController pdfExport = new DataGridPdfExportingController ();
DataGridPdfExportOption exportOption = new DataGridPdfExportOption ();
exportOption.FitAllColumnsInOnePage = true;
var doc = pdfExport.ExportToPdf (this.dataGrid, exportOption); 
{% endhighlight %}

SfDataGrid provides you with several [properties in DataGridPdfExportingOption](http://help.syncfusion.com/cr/cref_files/xamarin/sfgridconverter/Syncfusion.SfGridConverter.XForms~Syncfusion.SfDataGrid.XForms.Exporting.DataGridPdfExportOption_properties.html) class to customize the grid while exporting it to PDF. 

### Events

The SfDataGrid provides you the following Events for Exporting:

* [RowExporting](http://help.syncfusion.com/cr/cref_files/xamarin/sfgridconverter/Syncfusion.SfGridConverter.XForms~Syncfusion.SfDataGrid.XForms.Exporting.DataGridPdfExportingController~RowExporting_EV.html) – This Event is raised while exporting a row at the execution time before the row is exported.
* [CellExporting](http://help.syncfusion.com/cr/cref_files/xamarin/sfgridconverter/Syncfusion.SfGridConverter.XForms~Syncfusion.SfDataGrid.XForms.Exporting.DataGridPdfExportingController~CellExporting_EV.html) – This Event is raised while exporting a cell at the execution time before the cell is exported.

#### RowExporting

The [DataGridRowPdfExportingEventHandler](http://help.syncfusion.com/cr/cref_files/xamarin/sfgridconverter/Syncfusion.SfGridConverter.XForms~Syncfusion.SfDataGrid.XForms.Exporting.DataGridRowPdfExportingEventhandler.html) delegate allows you to customize the styles for record rows and group caption rows. The`RowExporting` event is triggered with [DataGridRowPdfExportingEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin/sfgridconverter/Syncfusion.SfGridConverter.XForms~Syncfusion.SfDataGrid.XForms.Exporting.DataGridRowPdfExportingEventArgs.html) that contains the following properties:

* PdfGrid – You can use this property to customize the PdfGrid’s properties such as Background, CellPadding, CellSpacing etc.
* PfdRow – Specifies the `PdfGridRow` to be exported. You can use this to customize the properties of particular row. 
* Record – Gets the collection of underlying data objects that are exported.
* RowType – Specifies the row type by using ExportRowType Enum. You can use this property to check the row type and apply different styles based on the row type.

You can use this event to customize the properties of the GridRows that are exported to pdf. The following code example illustrates how to change the background color of the record rows and caption summary rows while exporting.

{% highlight c# %}
//HandlingRowExportingEvent for exporting to PDF
DataGridPdfExportingController pdfExport = new DataGridPdfExportingController ();
pdfExport.RowExporting += pdfExport_RowExporting; 

void pdfExport_RowExporting (object sender, DataGridRowPdfExportingEventArgs e)
{
    if (e.RowType == ExportRowType.Record) {
        if ((e.Record.Data as OrderInfo).IsClosed)
            e.PdfRow.Style.BackgroundBrush = PdfBrushes.Yellow;
        else
        e.PdfRow.Style.BackgroundBrush = PdfBrushes.LightGreen;
    }

    if (e.RowType == ExportRowType.CaptionSummary) {
        e.PdfRow.Style.BackgroundBrush = PdfBrushes.LightGray;
    }
} 
{% endhighlight %}

#### CellExporting

The [DataGridCellPdfExportingEventHandler](http://help.syncfusion.com/cr/cref_files/xamarin/sfgridconverter/Syncfusion.SfGridConverter.XForms~Syncfusion.SfDataGrid.XForms.Exporting.DataGridCellPdfExportingEventhandler.html) delegate allows you to customize the styles for header cells, record cells and group caption cells. The `CellExporting` event is triggered with [DataGridCellPdfExportingEventArgs](http://help.syncfusion.com/cr/cref_files/xamarin/sfgridconverter/Syncfusion.SfGridConverter.XForms~Syncfusion.SfDataGrid.XForms.Exporting.DataGridCellPdfExportingEventArgs.html) that contains the following properties:

* CellType – Specifies the cell type by using ExportCellType Enum. You can use this property to check the cell type and apply different cell styles based on the cell type.
* CellValue – Contains the actual value that is exported to the PDF. You can use this value to apply formatting in PDF using Range property.
* ColumnName – Specifies the Column Name (MappingName) of the exporting cell. You can apply formatting for a particular column by checking the ColumnName.
* Handled – Determines whether the cell is exported to PDF or not.
* PdfGrid – Specifies the PDFGridCell to be exported. You can use this to customize the properties (Background, Foreground, Font, Alignment etc.,) of particular cell.
* Record – Gets the collection of underlying data objects that are exported.

You can use this event to customize the properties of the GridCells that are exported to PDF. The following code example illustrates how to customize the background color, Foreground color and CellValue of the header cells, record cells and caption summary cells while exporting.

{% highlight c# %}
//HandlingCellExportingEvent for exporting to PDF
DataGridPdfExportingController pdfExport = new DataGridPdfExportingController ();
pdfExport.CellExporting += pdfExport_CellExporting;  

void pdfExport_CellExporting(object sender, DataGridCellPdfExportingEventArgs e)
{
    if (e.CellType == ExportCellType.HeaderCell) {
        e.PdfGridCell.Style.BackgroundBrush = PdfBrushes.Blue;
        e.PdfGridCell.Style.TextBrush = PdfBrushes.White;
        e.CellValue = "HeaderCell";
    }

    if (e.CellType == ExportCellType.RecordCell) {
        e.PdfGridCell.Style.BackgroundBrush = PdfBrushes.Yellow;
        e.PdfGridCell.Style.TextBrush = PdfBrushes.Black;
        if (e.CellValue is string)
            e.CellValue = "RecordCell";
    }

    if (e.CellType == ExportCellType.GroupCaptionCell) {
        e.PdfGridCell.Style.BackgroundBrush = PdfBrushes.LightGray;
        e.PdfGridCell.Style.TextBrush = PdfBrushes.Blue;
        e.CellValue = "CaptionSummary";
    }
}
{% endhighlight %}
