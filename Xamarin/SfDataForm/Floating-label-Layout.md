---
layout: post
title: Floating-label-Layout | SfDataForm | Xamarin.Forms | Syncfusion
description: Floating label layout support in SfDataForm.
platform: xamarin
control: SfDataForm
documentation: UG
---

# Floating label layout

Dataform supports the floating label layout with support for assistive labels, leading and trailing icons, and a password toggle icon to show or hide a password. It provides three type of containers namely filled, outlined and none. Floating label layout can be enabled by setting `DataForm.LayoutOptions` as `TextInputLayout`.

## Layout options
By default, the dataform arranges the editors and their labels corresponding to fields in stack layout. However, to enable the floating label layout by setting `LayoutOptions` property of `DataForm` or `DataFormItem` as `TextInputLayout`.

{% tabs %}
{% highlight xaml %}       
 <dataForm:SfDataForm x:Name="dataForm" LayoutOptions="TextInputLayout">
 <dataForm:SfDataForm/>
{% endhighlight %}
{% highlight c# %}
dataForm.LayoutOptions = LayoutOptions.TextInputLayout;
{% endhighlight %}
{% endtabs %}

### Changing layout options of the DataFormItem
You can change layout option by using the `LayoutOptions` property in the `DataFormItem` and it will be handled in `AutoGeneratingDataFormItem` event.

{% tabs %}
{% highlight xaml %}      
<dataForm:SfDataForm x:Name="dataForm" DataObject="{Binding ContactsInfo}" AutoGeneratingDataFormItem="DataForm_AutoGeneratingDataFormItem">
</dataForm:SfDataForm>
{% endhighlight %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (e.DataFormItem.Name == "Address")
        {
            e.DataFormItem.LayoutOptions = LayoutOptions.TextInputLayout;
        }
        if (e.DataFormItem.Name == "DOB")
        {
            e.DataFormItem.LayoutOptions = LayoutOptions.TextInputLayout;
        }
    }
    if (e.DataFormItem != null && e.DataFormItem.Name == "Password")
    {
       e.DataFormItem.LayoutOptions = LayoutOptions.TextInputLayout;
    }
}

{% endhighlight %}
{% endtabs %}

## Support editors
Dataform supports the floating label layout for the below listed editors.
* Text editor
* Password editor
* Masked editor
* Numeric editor 
* MultilineText editor
* Date editor
* Time editor
* Picker editor

## Container types
Containers enhance the perspective of dataform editor views as provide some contrast between editor view and assistive labels, and its border and assistive label color will be changed based on dataform field validation.

By default, the container type is `Outlined`. By using `ContainerType` property in `DataForm` or in `DataFormItem` to modify the container type to `Filled` or `None`.

### Filled
The background color of dataform editor view will be filled with container color and it can be enabled by setting the `ContainerType` property to `Filled` in `DataForm` or in `DataFormItem`.

### Outlined
To enable the outlined container type, you can use `ContainerType` to `Outlined` in `DataForm` or in `DataFormItem` which covers the editor view with rounded-corner.

### None
When setting the `ContainerType` property to ` None ` in `DataForm` or in `DataFormItem` container will have empty background and enough spacing.

{% tabs %}
{% highlight xaml %}      
<dataForm:SfDataForm x:Name="dataForm" ContainerType="Outlined">
</dataForm:SfDataForm>                    
{% endhighlight %}
{% highlight c# %}
dataForm.LayoutOptions = ContainerType.Outlined;
{% endhighlight %}
{% endtabs %}

### Changing container type of the DataFormItem

You can change the container type of the `DataFormItem` by using the `ContainerType` property in the `DataFormItem` and it will be handled in `AutoGeneratingDataFormItem` event.

{% tabs %}
{% highlight xaml %}  
<dataForm:SfDataForm x:Name="dataForm" DataObject="{Binding ContactsInfo}" AutoGeneratingDataFormItem="DataForm_AutoGeneratingDataFormItem">
</dataForm:SfDataForm>
{% endhighlight %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (e.DataFormItem.Name == "Name")
        {
            e.DataFormItem.ContainerType = ContainerType.Filled;
        }
        if (e.DataFormItem.Name == "Address")
        {
            e.DataFormItem.ContainerType = ContainerType.None;
        }
    }
    if (e.DataFormItem != null && e.DataFormItem.Name == "Password")
    {
        e.DataFormItem.ContainerType = ContainerType.Outlined;
    }
}

{% endhighlight %}
{% endtabs %}

## Leading view
Floating label layout supports leading view which shows an icon view to the left side of editor. 
Unicode or font icons for the labels can be displayed as icons. By setting the LeadingView property, a label can be added as a leading icon for editor view. By setting the `LeadingViewPosition` property, it can be placed either inside or outside the container. It's positioned outside by default. 

N> Refer to the following links to learn more about font icons:
* [How to create font icons using our metro studio and export as ttf?](https://help.syncfusion.com/metro-studio/export-icon-font)
* [How to set font family for the custom fonts in labels?](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/text/fonts#using-a-custom-font)


{% tabs %}
{% highlight xaml %}  
<dataForm:SfDataForm x:Name="dataForm" DataObject="{Binding ContactsInfo}" AutoGeneratingDataFormItem="DataForm_AutoGeneratingDataFormItem">
</dataForm:SfDataForm>
{% endhighlight %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem1(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (e.DataFormItem.Name == "Name")
        {
            e.DataFormItem.TextInputLayoutSettings = new Syncfusion.SfDataForm.XForms.TextInputLayoutSettings()
            {
                LeadingView = new Label()
                {
                    VerticalTextAlignment = Device.RuntimePlatform == Device.iOS ? TextAlignment.Center : TextAlignment.Start,
                    FontSize = Device.RuntimePlatform == Device.iOS ? 18 : 24,
                    Text = "A",
                    FontFamily = Device.RuntimePlatform == Device.iOS ? "ContactsIcons" : Device.RuntimePlatform == Device.Android ? "ContactsIcons.ttf#ContactsIcons" : "Assets/Fonts/ContactsIcons.ttf#ContactsIcons"
                }
            };
        }
    }
}

{% endhighlight %}
{% endtabs %}


### Trailing view
Unicode or font icons for the labels can be displayed as icons.By setting the TrailingView property, a label can be added as a trailing icon for editor view. By setting the `TrailingViewPosition` property, it can be placed either inside or outside the container. It's positioned outside by default. 

N> Refer to the following links to learn more about font icons:
* [How to create font icons using our metro studio and export as ttf?](https://help.syncfusion.com/metro-studio/export-icon-font)
* [How to set font family for the custom fonts in labels?](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/text/fonts#using-a-custom-font)

{% tabs %}
{% highlight xaml %}  
<dataForm:SfDataForm x:Name="dataForm" DataObject="{Binding ContactsInfo}" AutoGeneratingDataFormItem="DataForm_AutoGeneratingDataFormItem">
</dataForm:SfDataForm>
{% endhighlight %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem1(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (e.DataFormItem.Name == "PhoneNumber")
        {
            e.DataFormItem.TextInputLayoutSettings = new Syncfusion.SfDataForm.XForms.TextInputLayoutSettings()
            {
                TrailingView = new Label()
                {
                    VerticalTextAlignment = Device.RuntimePlatform == Device.iOS ? TextAlignment.Center : TextAlignment.Start,
                    FontSize = Device.RuntimePlatform == Device.iOS ? 18 : 24,
                    Text = "I",
                    FontFamily = Device.RuntimePlatform == Device.iOS ? "ContactsIcons" : Device.RuntimePlatform == Device.Android ? "ContactsIcons.ttf#ContactsIcons" : "Assets/Fonts/ContactsIcons.ttf#ContactsIcons"
                }
            };
        }
    }
}

## Enable password visibility toggle for password editor

Password toggle visibility in floating label layout is used to show or hide the visibility of characters in the dataform password editor. You can enable this toggle by setting the `EnablePasswordVisibilityToggle` property to true in `DataFormTextItem`.

{% tabs %}
{% highlight xaml %}      
<dataForm:SfDataForm x:Name="dataForm" DataObject="{Binding ContactsInfo}"/>
{% endhighlight %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Password")
    {
        (e.DataFormItem as DataFormTextItem).EnablePasswordVisibilityToggle = true;
    }
}
{% endhighlight %}
{% endtabs %}

## Assistive label

Assistive labels comprise of floating label or hint label, helper label, counter label and validation label.

### Reserve space for assistive labels

The reserved spaces for assistive labels can be removed by setting the `ReserveSpaceForAssistiveLabels` property to false or it set to false automatically if there is no prompt value or water mark provider for `DataformItem` and/or no counter label added.

{% tabs %}
{% highlight xaml %}  
<dataForm:SfDataForm x:Name="dataForm" DataObject="{Binding ContactsInfo}" AutoGeneratingDataFormItem="DataForm_AutoGeneratingDataFormItem">
</dataForm:SfDataForm>
{% endhighlight %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem1(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        e.DataFormItem.TextInputLayoutSettings = new Syncfusion.SfDataForm.XForms.TextInputLayoutSettings()
        {
            ReserveSpaceForAssistiveLabels= true
        };
    }
}

### Hint label

Data field caption will be displayed as floating or hint label for the editor, and it will be enabled by using `Name` or `LabelText`  property.

### Helper label

Helper label used to display the water mark for the editor to provide hint for users and it can be set using [Prompt ] https://help.syncfusion.com/xamarin/sfdataform/working-with-dataform#setting-watermark.

### Validation label

Validation label used to display the dataform validation messages such as valid or invalid data. Please refer [validation](https://help.syncfusion.com/xamarin/sfdataform/validation) for more dataform validation.

### Counter label

Counter label can be used to notify the character count limitation in given validation. It can be enabled by setting the `ShowCharCount` property to `true`. Character limit can be set using the `StringLength` attribute.


{% tabs %}
{% highlight xaml %}
<dataForm:SfDataForm x:Name="dataForm" DataObject="{Binding ContactsInfo}" AutoGeneratingDataFormItem="DataForm_AutoGeneratingDataFormItem">
</dataForm:SfDataForm>
{% endhighlight %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Password")
    {
        e.DataFormItem.ShowCharCount = true;
    }
}

private string _Password;

[Required(AllowEmptyStrings = false, ErrorMessage = "Password should not be empty")]
[StringLength(10, ErrorMessage = "Password should not exceed 10 characters")]
public string Password
{
    get { return this._Password; }
    set
    {
        this._Password = value;
        this.RaisePropertyChanged("Password");
    }
}
{% endhighlight %}
{% endtabs %}

## Appearance customization
The assistive labels and border color can be customized based on the editor view states and data validation.


### Changing outline corner radius
When setting the OutlineCornerRadius property to double value, the corner radius of the container will be changed.

{% tabs %}
{% highlight xaml %}  
<dataForm:SfDataForm x:Name="dataForm" DataObject="{Binding ContactsInfo}" AutoGeneratingDataFormItem="DataForm_AutoGeneratingDataFormItem">
</dataForm:SfDataForm>
{% endhighlight %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem1(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        e.DataFormItem.TextInputLayoutSettings = new Syncfusion.SfDataForm.XForms.TextInputLayoutSettings()
        {
            OutlineCornerRadius = 30
        };
    }
}

### Focused color
When the given editor view is focused, the `FocusedColor` property value will be applied to the label text and border.

{% tabs %}
{% highlight xaml %}
<dataForm:SfDataForm x:Name="dataForm" DataObject="{Binding ContactsInfo}" AutoGeneratingDataFormItem="DataForm_AutoGeneratingDataFormItem">
</dataForm:SfDataForm>
{% endhighlight %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem1(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (e.DataFormItem.Name == "Name")
        {
            e.DataFormItem.FocusedColor = Color.Violet;
        }
    }
}

### Unfocused color
When the given editor view is unfocused, the FocusedColor property value will be applied to the label text and border.

{% tabs %}
{% highlight xaml %}
<dataForm:SfDataForm x:Name="dataForm" DataObject="{Binding ContactsInfo}" AutoGeneratingDataFormItem="DataForm_AutoGeneratingDataFormItem">
</dataForm:SfDataForm>
{% endhighlight %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem1(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (e.DataFormItem.Name == "Name")
        {
            e.DataFormItem.UnfocusedColor = Color.Silver;
        }
    }
}

### Error message color
In case of invalid data, the error message  color will be applied to the error label, hint label and border.

{% tabs %}
{% highlight xaml %}
<dataForm:SfDataForm x:Name="dataForm" DataObject="{Binding ContactsInfo}" AutoGeneratingDataFormItem="DataForm_AutoGeneratingDataFormItem">
</dataForm:SfDataForm>
{% endhighlight %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem1(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (e.DataFormItem.Name == "Name")
        {
            e.DataFormItem.ErrorMessageColor = Color.DarkRed;
        }
    }
}

### Valid message color
In case of valid data,the valid message color  will be applied to the valid message label , hint label and border.

{% tabs %}
{% highlight xaml %}
<dataForm:SfDataForm x:Name="dataForm" DataObject="{Binding ContactsInfo}" AutoGeneratingDataFormItem="DataForm_AutoGeneratingDataFormItem">
</dataForm:SfDataForm>
{% endhighlight %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem1(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (e.DataFormItem.Name == "Name")
        {
            e.DataFormItem.ValidMessageColor = Color.BlueViolet;
        }
    }
}

## Font customization
You can customize the font of assistive labels by setting the FontFamily, FontSize, and FontAttributes properties of the LabelStyle  property.

### Hint label style
You can customize text of hint label by setting the FontFamily, FontSize, and FontAttributes properties of HintLabelStyle in DataFormItem.

### Helper label style
You can customize text of helper label by setting the FontFamily, FontSize, and FontAttributes properties of HelperLabelStyle in DataFormItem.

### Validation label style
You can customize text of validation label by setting the FontFamily, FontSize, and FontAttributes properties of ValidationLabelStyle in DataFormItem.

{% tabs %}
{% highlight xaml %}      
<dataForm:SfDataForm x:Name="dataForm" DataObject="{Binding ContactsInfo}"/>
{% endhighlight %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "Password")
    {
        (e.DataFormItem.HintLabelStyle  = new LabelStyle() { FontFamily = Device.OnPlatform("Lobster-Regular", "Lobster-Regular.ttf#Lobster-Regular", "Assets/Fonts/Lobster-Regular.ttf#Lobster"), FontSize = 16};
    }
}
{% endhighlight %}
{% endtabs %}

## Limitations

* It is recommended not to use background color for editor view while customizing existing editor inside floating label layout.
* It is recommended not to use non editable custom editor views inside floating label layout such as range slider,etc.
* It is recommended not to use `LayoutOptions` attribute for setting default layout for data fields.
* It is recommended not to use null values in Date and Time picker  with text input layout in initial loading time and runtime in iOS platform.

## Non-supported editors
Floating label layout not support for the below listed non editable editors.

* Radiogroup editor
* Segment editor
* Checkbox editor
* Switch editor
* Dropdown editor
