---
layout: post
title: Layout | SfDataForm | Xamarin.Forms | Syncfusion
description: Floating label layout support in SfDataForm.
platform: xamarin
control: SfDataForm
documentation: UG
---

# Item layout

Improved design of DataForm editors integrated with the Text Input Layout control, which provides floating and assistive labels, leading and trailing icons, and a password toggle icon to show or hide a password. Support is provided to choose either a filled or outlined container for DataForm editors based on the requirements and appearance of the application.

## Support editors
We have enabled the floating label support for the below listed editors based on editor view.
* Text editor
* Password editor
* Masked editor
* Numeric editor 
* MultilineText editor
* Date editor
* Time editor
* Picker editor


## LayoutOptions
By default, the data form arranges the editors and their labels corresponding to fields in stack layout. However, in order to enable floating label ,you need to use the `LayoutOptions` in DataForm or in each `DataFormItem` as `TextInputLayout` to layout the editor inside text input layout, which comprised of a floating label, editor view.

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

You can change layout option by using the  `LayoutOptions` property in the `DataFormItem` and which will be handle in `AutoGeneratingDataFormItem` event.

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

## Container Type
Containers enhance the perspective of editor views as provide some contrast between editor view and assistive components.

By default, the container type is `Outlined`. By choosing `ContainerType` property in DataForm or in `DataFormItem` to modify the container type to `Filled` or `None`.

### Filled
To allow filled container type you can choose `ContainerType` to `Filled` which fills the background of editor view with container color.

### Outlined
To allow outlined container type you can choose `ContainerType` to `Outlined` which covers the editor view with rounded-corner.

### None
To allow outlined container type you can choose `ContainerType` to `None` where you will have empty background and enough spacing.

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

You can change the container type of the `DataFormItem` by using the  `ContainerType` property in the `DataFormItem` and which will be handle in `AutoGeneratingDataFormItem` event.

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

## Customizing floating label layout
Data form control provides user-friendly options for text input layout customization. In this section, it is explained how to customize the text input layout for each item in the data form through `TextInputLayoutSettings` available in DataForm control including leading view , trailing view and deals with allocating space for assistive labels.

### Leading view
By setting the LeadingView property, a label can be added as a leading icon for editor view. By setting the `LeadingViewPosition` property, it can be placed either inside or outside the container. It's positioned outside by default.

Unicode or font icons for the labels can be displayed as icons.

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
By setting the TrailingView property, a label can be added as a trailing icon for editor view. By setting the `TrailingViewPosition` property, it can be placed either inside or outside the container. It's positioned outside by default.

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

### Reserve space for assistive labels
The reserved spaces for assistive labels can be removed by setting the `ReserveSpaceForAssistiveLabels` property to false or it set to false automatically if there is no prompt value or water mark provider for `DataformItem` and/or no counter label attached.

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

## Assistive label
Assistive labels comprises of Helper text, floating label or hint label , counter label and validation label.

### Helper text
Helper text carries the information which conveys how the text of editor view need to be used and it can be set using [Prompt] https://help.syncfusion.com/xamarin/sfdataform/working-with-dataform#setting-watermark.

### Validation message
Validation message comprises of both invalid message and valid message. The valid message and invalid message replace one another based on [validation](https://help.syncfusion.com/xamarin/sfdataform/validation)

### Counter label
Couter label can be used to notify the charcter count limitation in given text.It can be enabled by setting the `ShowCharCount` property to `true`.Character limit can be set using the `StringLength` attribute.

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

## Color customizing
The hint label and border color can be customized based on the editor view states.

### Focused color
When the given editor view is focused, the FocusedColor property value will be applied to the label text and border.

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
In case of invalid data,the error message color will be applied to the error message.

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
In case of valid data,the valid message color will be applied to the valid message.

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
You can customize the font of assistive labels by setting the FontFamily, FontSize, and FontAttributes properties of the LabelStyle property.

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

## Enable password visibility toggle for password editor
When password editor is inserted inside text input layout, the password visibility toggle is used to show or hide the visibility of characters in the editor view. You can enable this toggle by setting the `EnablePasswordVisibilityToggle` property to true in `DataFormTextItem`.

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

## Limitations

* It is recommended not to use background color for editor view while customizing existing editor inside textinputlayout.
* It is recommended not to use non editable custom editor views inside textinputlayout such as range slider,etc.
* It is recommended not to use `LayoutOptions` attribute for setting default layout.
* It is recommended not to use null values in Date and Time picker with text input layout in initial loading time and runtime in iOS platform.

## Non-supported editors
The non-support editors in DataForm are listed below which are preferred not to use inside TextInputLayout which may affect the functioning of the current dataform.
* Radiogroup editor
* Segmente editor
* Checkbox editor
* Swich editor
* Dropdown editor
