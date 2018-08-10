---
layout: post
title: SfDataForm Localization
description: Describes how to localize the SfDataForm display attribute values and validation attribute error messages based on culture.
platform: xamarin
control: SfDataForm
documentation: ug
---

# Localization 

You can localize the DataFormItem [Display](https://apisof.net/catalog/System.ComponentModel.DataAnnotations.DisplayAttribute) attribute values and validation ([Required](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.RequiredAttribute.html),[StringLength](http://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.StringLengthAttribute.html) ) attributes values by using ResourceType display
attribute or using the `AutoGeneratingDataFormItem` event.
 
Please refer the [Localization]( https://docs.microsoft.com/en-us/xamarin/xamarin-forms/app-fundamentals/localization/text?tabs=vswin) document  to localize the application.
 
Based on the culture specifies the corresponding culture string value of display attribute in Resource (.Resx) file as mentioned in document.

## Localizing data form item display values

Here, the display attributes or data form item display values get localized based on culture from Localization Resource File (.Resx).

### Using attribute

ResourceType [Display](https://apisof.net/catalog/System.ComponentModel.DataAnnotations.DisplayAttribute ) attribute specifies the Resources File (.Resx) which is used to localize the Display attribute of Name, ShortName, GroupName and Prompt values.

{% tabs %}
{% highlight c# %}

[Display(Name ="FirstName", Prompt = "EnterFirstName", ResourceType = typeof(Localization))]
public String FirstName { get; set; } 

{% endhighlight %}
{% endtabs %}

### Using event

You can also localize the DataFormItem LabelText, PlaceHolderText in the `AutoGeneratingDataFormItem` event of SfDataForm by using the Resources (.Resx) file.

Here, Localization Resource File (.Resx) and accessed the localized string directly from it.


{% tabs %}
{% highlight c# %}

dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (e.DataFormItem.LabelText == "FirstName")
        {
            e.DataFormItem.LabelText = Localization.FirstName;
            e.DataFormItem.PlaceHolderText = Localization.EnterFirstName;
        }
    }
}

{% endhighlight %}
{% endtabs %}

## Localizing validation error messages

Here, the validation (Required,StringLength)  attributes or data form error messages get localized based on culture from Localization Resource File (.Resx).

### Using attribute

The `Required` and `StringLength` attributes error message can be localized using [ErrorMessageResourceType](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.validationattribute.errormessageresourcetype.aspx ) and [ErrorMessageResourceName](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.validationattribute.errormessageresourcename.aspx ) properties which are used to get a localized error messages from Localization Resource File (.Resx) based on culture.

{% tabs %}
{% highlight c# %}

[Required(AllowEmptyStrings =false,ErrorMessageResourceType = typeof(Localization), ErrorMessageResourceName = "FirstNameEmpty")]
[StringLength(25,MinimumLength =5,ErrorMessageResourceType = typeof(Localization), ErrorMessageResourceName = "FirstNameLength")]
public String FirstName { get; set; } 

{% endhighlight %}
{% endtabs %}

### Using event

You can also localize the data form error message in the ` Validating` event of SfDataForm by using the Resources (.Resx) file.

Here, Localization Resource File (.Resx) and accessed the localized string directly from it.

{% tabs %}
{% highlight c# %}

dataForm.Validating += DataForm_Validating;
private void DataForm_Validating(object sender, ValidatingEventArgs e)
{
    if (e.PropertyName == "FirstName")
    {
        if (e.Value.ToString().Length == 0)
        {
            e.IsValid = false;
            e.ErrorMessage = Localization.FirstNameEmpty;
        }
        else if (e.Value != null && e.Value.ToString().Length > 0 && !(e.Value.ToString().Length >= 5))
        {
            e.IsValid = false;
            e.ErrorMessage = Localization.FirstNameLength;
        }
    }
}
{% endhighlight %}
{% endtabs %}

![](SfDataForm_images/DataFormLocalization.png)

You can download the entire source code of this demo for Xamarin.Forms using attributes from here [LocalizationThroughAttribute](http://www.syncfusion.com/downloads/support/directtrac/general/ze/DataFormLocalizationAttribute-18381862.zip) and using event from here [LocalizationThroughEvent](http://www.syncfusion.com/downloads/support/directtrac/general/ze/DataFormLocalizationEvent-184378035.zip).