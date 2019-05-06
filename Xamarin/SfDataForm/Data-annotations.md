---
layout: post
title: Data annotations | SfDataForm | Xamarin.Forms | Syncfusion
description: Supported Data annotations in SfDataForm.
platform: Xamarin
control: SfDataForm
documentation: UG
---

# Data Annotations

The data form supports the following attribute, and these attributes can be accessible using `Syncfusion.SfDataForm.XForms`.

## Display attribute

<table>
<tr>
<th>Property</th>
<th>Details</th>
</tr>
<tr>
<td>
{{'[Name](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DisplayAttribute~Name.html)'| markdownify }}
</td>
<td>
Specifies the label text.
</td>
</tr>
<tr>
<td>
{{'[GroupName](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DisplayAttribute~GroupName.html)'| markdownify }}
</td>
<td>
Specifies the group name which groups the fields in the data form. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/layout#grouping-data-fields)'| markdownify }} for more details.
</td>
</tr>
<tr>
<td>
{{'[ShortName](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DisplayAttribute~ShortName.html)'| markdownify }}
</td>
<td>
Specifies the label text. It takes higher priority than Name.
</td>
</tr>
<tr>
<td>
{{'[AutoGenerateField](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DisplayAttribute~AutoGenerateField.html)'| markdownify }}
</td>
<td>
Specifies whether the field should be auto generated or not. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/working-with-dataform#cancel-dataformitem-generation-of-data-field)'| markdownify }} for more details.
</td>
</tr>
<tr>
<td>
{{'[Prompt](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DisplayAttribute~Prompt.html)'| markdownify }}
</td>
<td>
Specifies watermark text for the editor. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/working-with-dataform#setting-watermark)'| markdownify }} for more details.
</td>
</tr>
<tr>
<td>
{{'[Order](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DisplayAttribute~Order.html)'| markdownify }}
</td>
<td>
Specifies the order of field in the data form. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/layout#changing-order-of-the-dataformitem	)'| markdownify }} for more details.
</td>
</tr>
</table>

## Validation attributes

<table>
<tr>
<th>
Property
</th>
<th>
Details
</th>
</tr>
<tr>
<td>
MinLength
</td>
<td>
Specifies the required minimum length. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/validation#data-annotations)'| markdownify }} for more details.
</td>
</tr>
<tr>
<td>
MaxLength

</td>
<td>
Specifies the required maximum length. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/validation#data-annotations)'| markdownify }} for more details.
</td>
</tr>
<tr>
<td>
Required

</td>
<td>
Specifies the required data field value. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/validation#data-annotations)'| markdownify }} for more details.
</td>
</tr>
<tr>
<td>
Range

</td>
<td>
Specifies the maximum and minimum values. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/validation#data-annotations)'| markdownify }} for more details.
</td>
</tr>
</table>

## Bindable attribute

It specifies whether the field should be auto generated or not. Refer to [here](https://help.syncfusion.com/xamarin/sfdataform/working-with-dataform#cancel-dataformitem-generation-of-data-field) for more details.

## Editable attribute

It specifies whether the data field is editable or not.

## ReadOnly attribute

It specifies whether the data field is read only or not. Refer to [here](https://help.syncfusion.com/xamarin/sfdataform/editing#disable-editing) for more details.

## EnumDataType attribute

It specifies enum type for the data field.

## DataType attribute

It specifies data type for the field.

Supported data types are Text, MultilineText, Date, DateTime, Time, and Currency.

Refer to [here](https://help.syncfusion.com/xamarin/sfdataform/working-with-dataform#auto-generating-dataformitems-for-the-data-field) for more details.

## CustomDataType attribute

The Percent data type is supported. Refer to [here](https://help.syncfusion.com/xamarin/sfdataform/working-with-dataform#auto-generating-dataformitems-for-the-data-field) for more details.

### DisplayOptions attribute

<table>
<tr>
<th>
Property
</th>
<th>
Details
</th>
</tr>
<tr>
<td>
{{'[RowSpan](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DisplayOptionsAttribute~RowSpan.html)'| markdownify }}
</td>
<td>
Specifies the row span for the data form item. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/layout#row-span)'| markdownify }} for more details.
</td>
</tr>
<tr>
<td>
{{'[ColumnSpan](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DisplayOptionsAttribute~ColumnSpan.html)'| markdownify }}
</td>
<td>
Specifies the column span for the data form item. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/layout#column-span)'| markdownify }} for more details.
</td>
</tr>
<tr>
<td>
{{'[ValidMessage](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DisplayOptionsAttribute~ValidMessage.html)'| markdownify }}
</td>
<td>
Specifies positive message to be shown when validation is passed. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/validation#valid-or-positive-message)'| markdownify }} for more details.
</td>
</tr>
<tr>
<td>
{{'[ImageSource](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItem~ImageSource.html)'| markdownify }}
</td>
<td>
Specifies the image source for loading image instead of label. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/layout#loading-images-for-label)'| markdownify }} for more details.
</td>
</tr>
<tr>
<td>
{{'[ShowLabel](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DisplayOptionsAttribute~ShowLabel.html)'| markdownify }}
</td>
<td>
Specifies whether the label should be visible or not. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/layout#label-visibility)'| markdownify }} for more details.
</td>
</tr>
</table>

### Converter attribute

<table>
<tr>
<th>
Property
</th>
<th>
Details
</th>
</tr>
<tr>
<td>
{{'[ConverterType](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.ConverterAttribute~ConverterType.html)'| markdownify }}
</td>
<td>
Specifies the Converter type which converts the original value in different format or as different value. Refer to here for more details.
</td>
</tr>
</table>

### DateRange attribute

<table>
<tr>
<th>
Property
</th>
<th>
Details
</th>
</tr>
<tr>
<td>
{{'[MinYear](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DateRangeAttribute~MinYear.html)'| markdownify }}
</td>
<td>
Specifies the required minimum year.
</td>
</tr>
<tr>
<td>
{{'[MinMonth](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DateRangeAttribute~MinMonth.html)'| markdownify }}
</td>
<td>
Specifies the required minimum month.
</td>
</tr>
<tr>
<td>
{{'[MinDay](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DateRangeAttribute~MinDay.html)'| markdownify }}
</td>
<td>
Specifies the required minimum day.
</td>
</tr>
<tr>
<td>
{{'[MaxYear](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DateRangeAttribute~MaxYear.html)'| markdownify }}
</td>
<td>
Specifies the required maximum year.
</td>
</tr>
<tr>
<td>
{{'[MaxMonth](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DateRangeAttribute~MaxMonth.html)'| markdownify }}
</td>
<td>
Specifies the required maximum month.
</td>
</tr>
<tr>
<td>
{{'[MaxDay](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DateRangeAttribute~MaxDay.html)'| markdownify }}
</td>
<td>
Specifies the required maximum day.
</td>
</tr>
</table>

Refer to [here](https://help.syncfusion.com/xamarin/sfdataform/validation#data-annotations) for more details.
