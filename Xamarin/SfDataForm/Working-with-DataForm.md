---
layout: post
title: Working with DataForm | SfDataForm | Xamarin.Forms | Syncfusion
description: Working with DataForm.
platform: xamarin
control: SfDataForm
documentation: UG
---

# Working with the data form

## Auto-generating DataFormItems for the data field

By default, the [DataFormItems](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItems.html) will be generated based on the property type. For example, the [DataFormNumericItem](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormNumericItem.html) will be created for the `int` type property. 

The [DataFormItem](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItem.html) generation depends on the type and attribute defined for the property.
The following tables lists the several types of `DataFormItem` and its constraints for auto generation:

<table>
<tr>
<th>Generated DataFormItem Type</th>
<th>Editor</th>
<th>Data Type / Attribute</th>
</tr>
<tr>
<td>
{{'[DataFormTextItem](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormTextItem.html)'| markdownify }}
</td>
<td>
Text
</td>
<td>
Default DataFormItem generated for the String type and the properties with [DataType(DataType.Text)], [DataType(DataType.MultilineText)] and [DataType(DataType.Password)] attributes. 

</td>
</tr>
<tr>
<td>
{{'[DataFormNumericItem](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormNumericItem.html)'| markdownify }}
</td>
<td>
Numeric
</td>
<td>
Generated for Int, Double, Float, Decimal, Long types and also its nullable property with [DataType(DataType.Currency)] and [DataType(Percent)] attributes. 

</td>
</tr>
<tr>
<td>
{{'[DataFormDateItem](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormDateItem.html)'| markdownify }}
</td>
<td>
Date
</td>
<td>
Generated for DateTime type and properties with [DataType(DataType.Date)] and [DataType(DataType.DateTime)] attributes. 

</td>
</tr>
<tr>
<td>
{{'[DataFormTimeItem](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormTimeItem.html)'| markdownify }}
</td>
<td>
Time
</td>
<td>
Generated for the property with [DataType(DataType.Time)] attribute. 

</td>
</tr>
<tr>
<td>
{{'[DataFormPickerItem](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormPickerItem.html)'| markdownify }}
</td>
<td>
Picker
</td>
<td>
Generated for Enum type property and the property with [EnumDataTypeAttribute] attribute. 
</td>
</tr>
<tr>
<td>
{{'[DataFormItem](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItem.html)'| markdownify }}
</td>
<td>
CheckBox
</td>
<td>
Bool type
</td>
</tr>
</table>

You can customize the property settings or cancel the generation of `DataFormItem` by handling the [AutoGeneratingDataFormItem](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.SfDataForm~AutoGeneratingDataFormItem_EV.html) event.

## Customize auto generated fields

You can customize or cancel the generated `DataFormItem` by handling the [AutoGeneratingDataFormItem](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.SfDataForm~AutoGeneratingDataFormItem_EV.html) event. This event occurs when the field is auto-generated for public and non-static property of the data object.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             xmlns:dataForm="clr-namespace:Syncfusion.XForms.DataForm;assembly=Syncfusion.SfDataForm.XForms"
             x:Class="GettingStarted.MainPage">
    <ContentPage.Content>
        <dataForm:SfDataForm x:Name="dataForm" AutoGeneratingDataFormItem="DataForm_AutoGeneratingDataFormItem"/>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{

}
{% endhighlight %}
{% endtabs %}

[AutoGeneratingDataFormItemEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.AutoGeneratingDataFormItemEventArgs.html) provides the information about the auto-generated.  [AutoGeneratingDataFormItemEventArgs.DataFormItem](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.AutoGeneratingDataFormItemEventArgs~DataFormItem.html)  property returns the newly created `DataFormItem`.

## Cancel DataFormItem generation of the data field

You can cancel the specific [DataFormItem](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItem.html) adding to the data form by handling the `AutoGeneratingDataFormItem` event or by defining display attribute to avoid the particular data field being displayed.

### Using attributes

You can set [AutoGenerateField](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.displayattribute.autogeneratefield.aspx) to `false` for canceling the `DataFormItem` generation.

{% tabs %}
{% highlight c# %}
private int id;
[Display(AutoGenerateField = false)]
public int ID
{
    get
    {
        return id;
    }
    set
    {
        id = value;
        RaisePropertyChanged("ID");
    }
}
{% endhighlight %}
{% endtabs %}

### Using event

In the following code, the `DataFormItem` generation for the `MiddleName` property is canceled by setting the `Cancel` property to true.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem.Name == "MiddleName")
        e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

## Changing editor type

You can change the editor of the [DataFormItem](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItem.html) in the `AutoGeneratingDataFormItem` event.

In the following code, the editor is changed for `IsAvailable` field from `Bool` to `Switch`.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem.Name == "IsAvailable")
        e.DataFormItem.Editor = "Switch";
}
{% endhighlight %}
{% endtabs %}

## Changing property settings

You can change the property of [DataFormItem](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItem.html) in the `AutoGeneratingDataFormItem` event.

Here, `Salary` data field is restricted from being edited in the data form.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (e.DataFormItem.Name == "Salary")
            e.DataFormItem.IsReadOnly = true;
    }
}
{% endhighlight %}
{% endtabs %}

## Setting watermark

You can display the watermark in the editor by defining the display attribute or using the`AutoGeneratingDataFormItem` event.

### Using attribute

You can show the watermark in the editor by setting the [Prompt](https://msdn.microsoft.com/en-us/library/system.componentmodel.dataannotations.displayattribute.prompt.aspx) in display attribute.

{% tabs %}
{% highlight c# %}
private string middleName;
[Display(Prompt = "Enter middle name")]
public string MiddleName
{
    get { return this.middleName; }
    set
    {
        this.middleName = value;
    }
}
{% endhighlight %}
{% endtabs %}

### Using event

You can show the watermark in the editor by using the [PlaceHolderText](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItem~PlaceHolderText.html) property in [DataFormItem](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItem.html).

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (e.DataFormItem.Name == "Description")
            e.DataFormItem.PlaceHolderText = "Enter description";
    }
}
{% endhighlight %}
{% endtabs %}

## Localization
 
You can localize the DataFormItem [Display](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DisplayAttribute.html
) attribute values by using ResourceType display
attribute or using the `AutoGeneratingDataFormItem` event.
 
Please refer the [Localization]( https://docs.microsoft.com/en-us/xamarin/xamarin-forms/app-fundamentals/localization/text?tabs=vswin) document  to localize the application.
 
Based on the culture specifies the corresponding culture string value of display attribute in Resource (.Resx) file as mentioned in document.
 
### Using attribute.
 
ResourceType [Display](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DisplayAttribute.html
) attribute specifies the Resources File (.Resx) which is used to localize the Display attribute of Name, ShortName, GroupName and Prompt values.
 
Here, Display attribute value get localized based on culture from Localization Resource File (.Resx).
 
{% highlight c# %}

[Display(Name = "ContactName", Prompt ="FirstName", ResourceType = typeof(Localization))]
public string ContactName
{
    get { return this.contactName; }
    set
    {
        this.contactName = value;
    }
}
{% endhighlight %}
 
### Using event.
 
You can localize the Name, GroupName and Prompt display attribute in the editor by using the Resources (.Resx) file in the `AutoGeneratingDataFormItem` event.
 
Here, Localization Resource File (.Resx) and accessed the localized string directly from it.
 
{% highlight c# %}
 
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
    {
        if (e.DataFormItem.Name.Equals("ContactName"))
        {
            e.DataFormItem.PlaceHolderText = Localization.FirstName;
            e.DataFormItem.Name = Localization.ContactName;
        }
    }
{% endhighlight %}

## Changing DataFormItem

You can change the created [DataFormItem](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItem.html) and assign new `DataFormItem` in the [AutoGeneratingDataFormItem](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.SfDataForm~AutoGeneratingDataFormItem_EV.html) event.

Here, [DataFormTextItem](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormTextItem.html) with number keyboard is loaded for numeric value instead of `DataFormNumericItem`.

{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
       if (e.DataFormItem.Name == "ID")
          e.DataFormItem = new DataFormTextItem() { Name = "ID", Editor = "Text", KeyBoard = Keyboard.Numeric };
    }
}
{% endhighlight %}

## Adding or removing the data field displayed in the dataForm at runtime

If you want to remove or add data fields item at runtime, you can use the [RefreshLayout](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.SfDataForm~RefreshLayout.html) method which auto-generates the DataFormItem where you can skip certain item from display. By default, it will generate the canceled items initially. If you want to regenerate all the items, you should pass argument as `true`.

In the following code snippet, items are auto generated based on `refreshLayout` flag where you can change flag at runtime and call `RefreshLayout` method to add or remove items being displayed in the data form at runtime.

{% tabs %}
{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:GettingStarted"
             xmlns:dataForm ="clr-namespace:Syncfusion.XForms.DataForm;assembly=Syncfusion.SfDataForm.XForms"
             x:Class="GettingStarted.MainPage">
    <ContentPage.Content>
        <Grid>
            <Grid.RowDefinitions>
                <RowDefinition Height="*"/>
                <RowDefinition Height="Auto"/>
            </Grid.RowDefinitions>
            <dataForm:SfDataForm Grid.Row="0" x:Name="dataForm" AutoGeneratingDataFormItem="DataForm_AutoGeneratingDataFormItem"/>
            <Button x:Name="Commit" Grid.Row="1" WidthRequest="100" HeightRequest="50" Text="MORE FIELDS" Clicked="Button_Clicked"/>
        </Grid>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}
{% highlight c# %}

dataForm.DataObject = new ContactsInfo();

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (!refreshLayout)
        {
            if (e.DataFormItem.Name.Equals("MiddleName") || e.DataFormItem.Name.Equals("LastName"))
                e.Cancel = true;
        }
        else
        {
            if (e.DataFormItem.Name == "GroupName")
                e.Cancel = true;
        }
    }
}
{% endhighlight %}
{% endtabs %}

![](SfDataForm_images/MoreFieldsOnLoad.png)

If you want to generate the MiddleName and LastName fields at runtime, you should set `refreshLayout` flag to `true` and call the [RefreshLayout](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.SfDataForm~RefreshLayout.html) method which triggers `AutoGeneratingDataFormItem` event again and generates the items based on `refreshLayout` flag.

{% tabs %}
{% highlight c# %}
private void Button_Click(object sender, System.EventArgs e)
{
    refreshLayout = true;
    dataForm.RefreshLayout();
}
{% endhighlight %}
{% endtabs %}

Here, the MiddleName and LastName fields are generated at runtime after clicking the more field button.

![](SfDataForm_images/MoreFieldsAdd.png)

The`GroupName`field is displayed initially in the data form. If you want to remove it at runtime, you should set refreshLayout flag to true and pass the argument as true in[RefreshLayout](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.SfDataForm~RefreshLayout.html) method. It triggers `AutoGeneratingDataFormItem` event for all the fields where you can cancel `GroupName’ field item generation.

{% tabs %}
{% highlight c# %}
private void Button_Click(object sender, System.EventArgs e)
{
    refreshLayout = true;
    dataForm.RefreshLayout(true);
}
{% endhighlight %}
{% endtabs %}

Here, the GroupName field is removed at runtime.

![](SfDataForm_images/MoreFieldsRemove.png)

You can download the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/MoreFields1624183179.zip).

## DataFormItemManager

The [DataFormItemManager](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItemManager.html) creates [DataFormItems](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItems.html) collection and handles value reflection and validation. It also overrides to handle the get and set property values from and to the data object.

### Manually defining DataFormItem

By default, [DataFormItems](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItems.html) will be generated based on data object. If you want to generate `DataFormItems` manually, you should override the [DataFormItemManager](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItemManager.html) class and set it to [SfDataForm.ItemManager](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.SfDataForm~ItemManager.html).

To create `DataFormItems`, you should override the [GenerateDataFormItems](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItemManager~GenerateDataFormItems.html) method.

{% highlight c# %}

// data form item creating by setting DataObject.
dataForm.DataObject = new ContactsInfo();
dataForm.ItemManager = new DataFormItemManagerExt(dataForm);

public class DataFormItemManagerExt : DataFormItemManager
{       
    public DataFormItemManagerExt(SfDataForm dataForm) : base(dataForm)
    {

    }
    protected override List<DataFormItemBase> GenerateDataFormItems(PropertyInfoCollection itemProperties, List<DataFormItemBase> dataFormItems)
    {
        var items = new List<DataFormItemBase>();
        foreach (var propertyInfo in itemProperties)
        {
           DataFormItem dataFormItem;
				if (propertyInfo.Key == "ID")
					dataFormItem = new DataFormTextItem() { Name = propertyInfo.Key, Editor = "Text" };
				else if (propertyInfo.Key == "Name")
					dataFormItem = new DataFormTextItem() { Name = propertyInfo.Key, Editor = "Text" };
				else
                    dataFormItem = new DataFormTextItem() { Name = propertyInfo.Key, Editor = "Text" };

				items.Add(dataFormItem);
			}

        return items;
    }
}

{% endhighlight %}

### Loading data form with dictionary

You can load the data form with custom dictionary by manually generating items and handling read and write values.

#### Manually defining DataFormItem

To create `DataFormItems` from dictionary , you should override the [GenerateDataFormItems](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItemManager~GenerateDataFormItems.html) method.

{% highlight c# %}

// data form item creating using dictionary.
dataForm.DataObject = new object();
var dictionary = new Dictionary<string, object>();
dictionary.Add("ID", 1);
dictionary.Add("Name", "John");
dataForm.ItemManager = new DataFormItemManagerExt(dataForm, dictionary);

public class DataFormItemManagerExt : DataFormItemManager
{
    Dictionary<string, object> dataFormDictionary;
    public DataFormItemManagerExt(SfDataForm dataForm, Dictionary<string, object> dictionary) : base(dataForm)
    {
        dataFormDictionary = dictionary;
    }

    protected override List<DataFormItemBase> GenerateDataFormItems(PropertyInfoCollection itemProperties, List<DataFormItemBase> dataFormItems)
    {
        var items = new List<DataFormItemBase>();
        foreach (var key in dataFormDictionary.Keys)
        {
            DataFormItem dataFormItem;
            if (key == "ID")
                dataFormItem = new DataFormNumericItem() { Name = key, Editor = "Numeric", MaximumNumberDecimalDigits = 0 };
            else if (key == "Name")
                dataFormItem = new DataFormTextItem() { Name = key, Editor = "Text" };
            else
                dataFormItem = new DataFormTextItem() { Name = key, Editor = "Text" };

            items.Add(dataFormItem);
        }
         
        return items;
    }
}

{% endhighlight %}

#### Handling reading and writing values to and from the data object

By default, the value will be shown in editor by getting it from the data object and after editing, the data object will be committed with the new value. If you want to customize the value, you should override [GetValue](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItemManager~GetValue.html) and [SetValue](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItemManager~SetValue.html) methods in [DataFormItemManager](https://help.syncfusion.com/cr/cref_files/xamarin/sfdataform/Syncfusion.SfDataForm.XForms~Syncfusion.XForms.DataForm.DataFormItemManager.html).

Here, the value is reading and writing from/to dictionary instead of the data object.

{% highlight c# %}
public class DataFormItemManagerExt : DataFormItemManager
{
    Dictionary<string, object> dataFormDictionary;
    public DataFormItemManagerExt(SfDataForm dataForm, Dictionary<string, object> dictionary) : base(dataForm)
    {
        dataFormDictionary = dictionary;
    }

    public override object GetValue(DataFormItem dataFormItem)
    {
        var value = dataFormDictionary[dataFormItem.Name];
        return value;
    }

    public override void SetValue(DataFormItem dataFormItem, object value)
    {
        dataFormDictionary[dataFormItem.Name] = value;
    }

}
{% endhighlight %}

Here, the data form is loaded with field from dictionary.