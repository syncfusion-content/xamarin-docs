---
layout: post
title: Data annotations | SfDataForm | Xamarin.Forms | Syncfusion
description: This section explains the display, validation, bindable, editable, read-only, enum data type attributes in data annotations.
platform: Xamarin
control: SfDataForm
documentation: UG
---

# Data annotations in Xamarin DataForm (SfDataForm)

The data form supports the following attribute, and these attributes can be accessible using `System.ComponentModel.DataAnnotation` assembly.

## Display attribute

<table>
<tr>
<th>Property</th>
<th>Details</th>
</tr>
<tr>
<td>
{{'[Name](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.name?view=netframework-4.8)'| markdownify }}
</td>
<td>
Specifies the label text.
</td>
</tr>
<tr>
<td>
{{'[GroupName](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.groupname?view=netframework-4.8)'| markdownify }}
</td>
<td>
Specifies the group name which groups the fields in the data form. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/layout#grouping-data-fields)'| markdownify }} for more details.
</td>
</tr>
<tr>
<td>
{{'[ShortName](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.shortname?view=netframework-4.8)'| markdownify }}
</td>
<td>
Specifies the label text. It takes higher priority than Name.
</td>
</tr>
<tr>
<td>
{{'[AutoGenerateField](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.autogeneratefield?view=netframework-4.8)'| markdownify }}
</td>
<td>
Specifies whether the field should be auto generated or not. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/working-with-dataform#cancel-dataformitem-generation-of-data-field)'| markdownify }} for more details.
</td>
</tr>
<tr>
<td>
{{'[Prompt](https://help.syncfusion.com/cr/xamarin/)'| markdownify }}
</td>
<td>
Specifies watermark text for the editor. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/working-with-dataform#setting-watermark)'| markdownify }} for more details.
</td>
</tr>
<tr>
<td>
{{'[Order](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.order?view=netframework-4.8)'| markdownify }}
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

## DisplayFormat attribute

It specifies how data fields are displayed and formatted.

Supported data types are currency, percentage, date, time.

<table>
<tr>
<th>Property</th>
<th>Details</th>
</tr>
<tr>
<td>
DataFormatString
</td>
<td>
Specifies the display format of the field value.
</td>
</tr>
</table>

<table>
<tr>
<th>Editor</th>
<th>FormatString</th>
</tr>
<tr>
<td>
Currency
</td>
<td>
{0:C}
</td>
</tr>
<tr>
<td>
Percentage
</td>
<td>
{0:P}
</td>
</tr>
<tr>
<td>
Date
</td>
<td>
{0:D}
</td>
</tr>
<tr>
<td>
Time
</td>
<td>
{0:T}
</td>
</tr>
</table>

{% tabs %}
{% highlight c# %}
dataForm.DataObject = new ContactInfo();

public class ContactInfo
{
    private int markPercentage;

    [DisplayFormat(DataFormatString ="{0:P}")]
    public String MarkPercentage
    {
        get
        {
            return markPercentage;
        }
        set
        {
            markPercentage = value;
        }
    }
}
{% endhighlight %}
{% endtabs %}

## CustomDataType attribute

The Percent data type is supported. Refer to [here](https://help.syncfusion.com/xamarin/sfdataform/working-with-dataform#auto-generating-dataformitems-for-the-data-field) for more details.

## Custom attribute
The data form supports the following custom attribute, and these attributes can be accessible using `Syncfusion.SfDataForm.XForms`.

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
{{'[RowSpan](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DisplayOptionsAttribute.html#Syncfusion_XForms_DataForm_DisplayOptionsAttribute_RowSpan)'| markdownify }}
</td>
<td>
Specifies the row span for the data form item. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/layout#row-span)'| markdownify }} for more details.
</td>
</tr>
<tr>
<td>
{{'[ColumnSpan](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DisplayOptionsAttribute.html#Syncfusion_XForms_DataForm_DisplayOptionsAttribute_ColumnSpan)'| markdownify }}
</td>
<td>
Specifies the column span for the data form item. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/layout#column-span)'| markdownify }} for more details.
</td>
</tr>
<tr>
<td>
{{'[ValidMessage](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DisplayOptionsAttribute.html#Syncfusion_XForms_DataForm_DisplayOptionsAttribute_ValidMessage)'| markdownify }}
</td>
<td>
Specifies positive message to be shown when validation is passed. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/validation#valid-or-positive-message)'| markdownify }} for more details.
</td>
</tr>
<tr>
<td>
{{'[ImageSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html#Syncfusion_XForms_DataForm_DataFormItem_ImageSource)'| markdownify }}
</td>
<td>
Specifies the image source for loading image instead of label. Refer to {{'[here](https://help.syncfusion.com/xamarin/sfdataform/layout#loading-images-for-label)'| markdownify }} for more details.
</td>
</tr>
<tr>
<td>
{{'[ShowLabel](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DisplayOptionsAttribute.html#Syncfusion_XForms_DataForm_DisplayOptionsAttribute_ShowLabel)'| markdownify }}
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
{{'[ConverterType](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.ConverterAttribute.html#Syncfusion_XForms_DataForm_ConverterAttribute_ConverterType)'| markdownify }}
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
{{'[MinYear](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DateRangeAttribute.html#Syncfusion_XForms_DataForm_DateRangeAttribute_MinYear)'| markdownify }}
</td>
<td>
Specifies the required minimum year.
</td>
</tr>
<tr>
<td>
{{'[MinMonth](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DateRangeAttribute.html#Syncfusion_XForms_DataForm_DateRangeAttribute_MinMonth)'| markdownify }}
</td>
<td>
Specifies the required minimum month.
</td>
</tr>
<tr>
<td>
{{'[MinDay](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DateRangeAttribute.html#Syncfusion_XForms_DataForm_DateRangeAttribute_MinDay)'| markdownify }}
</td>
<td>
Specifies the required minimum day.
</td>
</tr>
<tr>
<td>
{{'[MaxYear](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DateRangeAttribute.html#Syncfusion_XForms_DataForm_DateRangeAttribute_MaxYear)'| markdownify }}
</td>
<td>
Specifies the required maximum year.
</td>
</tr>
<tr>
<td>
{{'[MaxMonth](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DateRangeAttribute.html#Syncfusion_XForms_DataForm_DateRangeAttribute_MaxMonth)'| markdownify }}
</td>
<td>
Specifies the required maximum month.
</td>
</tr>
<tr>
<td>
{{'[MaxDay](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DateRangeAttribute.html#Syncfusion_XForms_DataForm_DateRangeAttribute_MaxDay)'| markdownify }}
</td>
<td>
Specifies the required maximum day.
</td>
</tr>
</table>

Refer to [here](https://help.syncfusion.com/xamarin/sfdataform/validation#data-annotations) for more details.
