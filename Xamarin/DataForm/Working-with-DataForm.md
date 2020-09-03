---
layout: post
title: Working with DataForm | SfDataForm | Xamarin.Forms | Syncfusion
description: Working with DataForm in Xamarin.Forms.
platform: xamarin
control: SfDataForm
documentation: UG
---

# Working with the data form

## Auto-generating DataFormItems for the data field

By default, the [DataFormItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItems.html) will be generated based on the property type. For example, the [DataFormNumericItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormNumericItem.html) will be created for the `int` type property. 

The [DataFormItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html) generation depends on the type and attribute defined for the property.
The following tables lists the several types of `DataFormItem` and its constraints for auto generation:

<table>
<tr>
<th>Generated DataFormItem Type</th>
<th>Editor</th>
<th>Data Type / Attribute</th>
</tr>
<tr>
<td>
{{'[DataFormTextItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormTextItem.html)'| markdownify }}
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
{{'[DataFormNumericItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormNumericItem.html)'| markdownify }}
</td>
<td>
Numeric
</td>
<td>
Generated for Int, Double, Float, Decimal, Long types and also its nullable property with [DataType(DataType.Currency)] and [DataType("Percent")] attributes. 

</td>
</tr>
<tr>
<td>
{{'[DataFormDateItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormDateItem.html)'| markdownify }}
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
{{'[DataFormTimeItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormTimeItem.html)'| markdownify }}
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
{{'[DataFormPickerItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormPickerItem.html)'| markdownify }}
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
{{'[DataFormDropDownItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormDropDownItem.html)'| markdownify }}
</td>
<td>
DropDown
</td>
<td>
Generated for Enum type property and the property with [EnumDataTypeAttribute] attribute. 
</td>
</tr><tr>
<td>
{{'[DataFormAutoCompleteItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormAutoCompleteItem.html)'| markdownify }}
</td>
<td>
AutoComplete
</td>
<td>
Generated for Enum type property and the property with [EnumDataTypeAttribute] attribute. 
</td>
</tr>
<tr>
<td>
{{'[DataFormMaskedEditTextItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormMaskedEditTextItem.html)'| markdownify }}
</td>
<td>
MaskedEditText
</td>
<td>
Generated for the PhoneNumber type property.
[DataType(DataType.PhoneNumber)]
</td>
</tr>
<tr>
<td>
{{'[DataFormItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html)'| markdownify }}
</td>
<td>
CheckBox
</td>
<td>
Bool type
</td>
</tr>
</table>

You can customize the property settings or cancel the generation of `DataFormItem` by handling the [AutoGeneratingDataFormItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html) event.

## Customize auto generated fields

You can customize or cancel the generated `DataFormItem` by handling the [AutoGeneratingDataFormItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html) event. This event occurs when the field is auto-generated for public and non-static property of the data object.

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

[AutoGeneratingDataFormItemEventArgs](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.AutoGeneratingDataFormItemEventArgs.html) provides the information about the auto-generated.  [AutoGeneratingDataFormItemEventArgs.DataFormItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.AutoGeneratingDataFormItemEventArgs.html#Syncfusion_XForms_DataForm_AutoGeneratingDataFormItemEventArgs__ctor_Syncfusion_XForms_DataForm_DataFormItem_)  property returns the newly created `DataFormItem`.

## Cancel DataFormItem generation of the data field

You can cancel the specific [DataFormItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html) adding to the data form by handling the `AutoGeneratingDataFormItem` event or by defining display attribute to avoid the particular data field being displayed.

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

You can change the editor of the [DataFormItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html) in the `AutoGeneratingDataFormItem` event.

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

You can change the property of [DataFormItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html) in the `AutoGeneratingDataFormItem` event.

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

### Changing DataFormItem visibility

You can change the [DataFormItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html) visibility by using the [IsVisible](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItemBase.html#Syncfusion_XForms_DataForm_DataFormItemBase_IsVisible) property in the `DataFormItem`.

Here, `Salary` data field will be hidden.

{% tabs %}
{% highlight c# %}
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null)
    {
        if (e.DataFormItem.Name == "Salary")
            e.DataFormItem.IsVisible = false;
    }
}
{% endhighlight %}
{% endtabs %}

### Changing DataFormItem FontSize

Using the [EditorFontSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html#Syncfusion_XForms_DataForm_DataFormItem_EditorFontSize), [LabelFontSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItemBase.html#Syncfusion_XForms_DataForm_DataFormItemBase_LabelFontSize), and [ValidationLabelFontSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html#Syncfusion_XForms_DataForm_DataFormItem_ValidationLabelFontSize) properties from `DataFormItem`, you can define the font size of the `Editor`, `Label`, and `ValidationLabel`. Changing the font size will be handled in the `AutoGeneratingDataFormItem` event.

You can define the font size as described as follows.
      
 * Set the value to font size directly or use the named font sizes such as `Small`, `Medium`, and `Large`.

{% tabs %}

{% highlight c# %}

dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;
private void DataForm_AutoGeneratingDataFormItem(object sender,AutoGeneratingDataFormItemEventArgs e)
{
   if (e.DataFormItem != null)
     {
          // Setting Fontsize using NamedSize.                
          e.DataFormItem.EditorFontSize = Device.GetNamedSize(NamedSize.Small, typeof(Label));
          e.DataFormItem.LabelFontSize = Device.GetNamedSize(NamedSize.Large, typeof(Label));
          e.DataFormItem.ValidationLabelFontSize = Device.GetNamedSize(NamedSize.Micro, typeof(Label));
          // Setting value to FontSize directly.                
          e.DataFormItem.EditorFontSize = 8;
          e.DataFormItem.LabelFontSize = 8;
          e.DataFormItem.ValidationLabelFontSize = 8; 
     }
}
{% endhighlight %}

{% endtabs %}

## Setting watermark

You can display the watermark in the editor by defining the display attribute or using the`AutoGeneratingDataFormItem` event.

### Using attribute

You can show the watermark in the editor by setting the [Prompt](https://help.syncfusion.com/cr/xamarin/) in display attribute.

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

You can show the watermark in the editor by using the [PlaceHolderText](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html#Syncfusion_XForms_DataForm_DataFormItem_PlaceHolderText) property in [DataFormItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html).

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

## Changing DataFormItem

You can change the created [DataFormItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItem.html) and assign new `DataFormItem` in the [AutoGeneratingDataFormItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html) event.

Here, [DataFormTextItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormTextItem.html) with number keyboard is loaded for numeric value instead of `DataFormNumericItem`.

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

If you want to remove or add data fields item at runtime, you can use the [RefreshLayout](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_RefreshLayout_System_Boolean_) method which auto-generates the DataFormItem where you can skip certain item from display. By default, it will generate the canceled items initially. If you want to regenerate all the items, you should pass argument as `true`.

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

![Initial rendering of data form items in Xamarin.Forms DataForm](SfDataForm_images/MoreFieldsOnLoad.png)

If you want to generate the MiddleName and LastName fields at runtime, you should set `refreshLayout` flag to `true` and call the [RefreshLayout](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_RefreshLayout_System_Boolean_) method which triggers `AutoGeneratingDataFormItem` event again and generates the items based on `refreshLayout` flag.

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

![Adding data form fields at run time in Xamarin.Forms DataForm](SfDataForm_images/MoreFieldsAdd.png)

The`GroupName`field is displayed initially in the data form. If you want to remove it at runtime, you should set refreshLayout flag to true and pass the argument as true in[RefreshLayout](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_RefreshLayout_System_Boolean_) method. It triggers `AutoGeneratingDataFormItem` event for all the fields where you can cancel `GroupName’ field item generation.

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

![Removing data form fields at run time in Xamarin.Forms DataForm](SfDataForm_images/MoreFieldsRemove.png)

You can download the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/MoreFields1624183179.zip).

## DataFormItemManager

The [DataFormItemManager](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItemManager.html) creates [DataFormItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItems.html) collection and handles value reflection and validation. It also overrides to handle the get and set property values from and to the data object.

### Manually generate DataFormItems for DataObject

By default, [DataFormItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItems.html) will be generated based on DataObject. If you need to generate `DataFormItems` manually, override the [DataFormItemManager](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItemManager.html) class and set it to [SfDataForm.ItemManager](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_ItemManager).

To create `DataFormItems`, override the [GenerateDataFormItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItemManager.html#Syncfusion_XForms_DataForm_DataFormItemManager_GenerateDataFormItems_Syncfusion_XForms_DataForm_PropertyInfoCollection_System_Collections_Generic_List_Syncfusion_XForms_DataForm_DataFormItemBase__) method.

{% highlight c# %}

// dataform item creating by setting DataObject.
dataForm.DataObject = new ContactsInfo();
dataForm.ItemManager = new DataFormItemManagerExt(dataForm);

public class DataFormItemManagerExt : DataFormItemManager
{       
    SfDataForm sfDataForm;
    public DataFormItemManagerExt(SfDataForm dataForm) : base(dataForm)
    {
        sfDataForm = dataForm;
    }
    protected override List<DataFormItemBase> GenerateDataFormItems(PropertyInfoCollection itemProperties, List<DataFormItemBase> dataFormItems)
    {
        var items = new List<DataFormItemBase>();
        foreach (var propertyInfo in itemProperties)
        {
            DataFormItem dataFormItem;
		    if (propertyInfo.Key == "ID")
				dataFormItem = new DataFormNumericItem() { Name = propertyInfo.Key, Editor = "Numeric", MaximumNumberDecimalDigits = 0 };
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

You can download the source code of this demo from [GenerateDataFormItemsForDataObject](https://github.com/SyncfusionExamples/generate-dataformitems-for-dataobject-in-xamarin-dataform)

### Manually generate DataFormItems for data dictionary

You can load the dataform with custom dictionary by generating DataFormItems manually. To create `DataFormItems` from dictionary, override the [GenerateDataFormItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItemManager.html#Syncfusion_XForms_DataForm_DataFormItemManager_GenerateDataFormItems_Syncfusion_XForms_DataForm_PropertyInfoCollection_System_Collections_Generic_List_Syncfusion_XForms_DataForm_DataFormItemBase__) method.

{% highlight c# %}

// dataform item creating using dictionary.
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

#### Handling reading and writing values to and from the dictionary

By default, the dictionary value will be shown in corresponding editor and value changes in editor will be committed again in dictionary value by using the [GetValue](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItemManager.html#Syncfusion_XForms_DataForm_DataFormItemManager_GetValue_Syncfusion_XForms_DataForm_DataFormItem_) and [SetValue](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItemManager.html#Syncfusion_XForms_DataForm_DataFormItemManager_SetValue_Syncfusion_XForms_DataForm_DataFormItem_System_Object_) override methods in [DataFormItemManager](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.DataFormItemManager.html).

Here, the value is read and written from/to dictionary instead of the data object.

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

Here, the dataform is loaded with field from dictionary.

You can download the source code of this demo from [GenerateDataFormItemsForDictionary](https://github.com/SyncfusionExamples/generate-dataformitems-for-dictionary-loaded-in-xamarin-dataform)

## Binding with dynamic data object

You can also load the dynamic object in SfDataForm `DataObject` and by default text editor will be generated for each dynamic object property. You can change the editor of DataFormItem for dynamic object property data type (default string) by using the AutoGeneratingDataFormItem event. You can find details about this [here](https://help.syncfusion.com/xamarin/sfdataform/working-with-dataform#changing-editor-type)

### Limitations

DynamicObject supports only in Xamarin.Forms Android and data form item will be created for each dynamic object property. Currently Dynamic object is not supported in UWP and iOS platform and you can find more details about this for iOS platform under the following links.

https://forums.xamarin.com/discussion/53941/expandoobject-crashing-ios 
https://developer.xamarin.com/guides/ios/advanced_topics/limitations/

{% tabs %}
{% highlight c# %}

dataForm.DataObject =new DynamicDataModel().ExpandoObject;
dataForm.AutoGeneratingDataFormItem += DataForm_AutoGeneratingDataFormItem;

private void DataForm_AutoGeneratingDataFormItem(object sender, AutoGeneratingDataFormItemEventArgs e)
{
    if (e.DataFormItem != null && e.DataFormItem.Name == "DateOfBirth")
        e.DataFormItem.Editor = "Date";
}

public class DynamicDataModel
{
    public dynamic ExpandoObject;

    public dynamic DynamicObject;
    public DynamicDataModel()
    {
        ExpandoObject = new ExpandoObject();
        ExpandoObject.FirstName = "John";
        ExpandoObject.LastName = "";
        ExpandoObject.DateOfBirth = DateTime.Now.Date;
        ExpandoObject.Email = "";

        DynamicObject = new Data();
        DynamicObject.FirstName = "John";
        DynamicObject.LastName = "";
        DynamicObject.DateOfBirth = DateTime.Now.Date;
        DynamicObject.Email = "";
    }
}

public class Data : DynamicObject, IDictionary<string, object>
{
    Dictionary<string, object> list = new Dictionary<string, object>();

    public override bool TrySetMember(SetMemberBinder binder, object value)
    {
        list[binder.Name] = value;
        return true;
    }

    public override bool TryGetMember(GetMemberBinder binder, out object result)
    {
        return list.TryGetValue(binder.Name, out result);
    }

    public override IEnumerable<string> GetDynamicMemberNames()
    {
        return list.Keys;
    }

    public void Add(string key, object value)
    {
        this.list.Add(key, value);
    }

    public bool ContainsKey(string key)
    {
        return this.list.ContainsKey(key);
    }

    public ICollection<string> Keys
    {
        get { return this.list.Keys; }
    }

    public bool Remove(string key)
    {
        return this.list.Remove(key);
    }

    public bool TryGetValue(string key, out object value)
    {
        return this.list.TryGetValue(key, out value);
    }

    public ICollection<object> Values
    {
        get { return this.list.Values; }
    }

    object IDictionary<string, object>.this[string key]
    {
        get { return this.list[key]; }
        set { this.list[key] = value; }
    }

    public void Add(KeyValuePair<string, object> item)
    {
        this.list.Add(item.Key, item.Value);
    }

    public void Clear()
    {
        this.list.Clear();
    }

    public bool Contains(KeyValuePair<string, object> item)
    {
        return this.list.Contains(item);
    }

    public void CopyTo(KeyValuePair<string, object>[] array, int arrayIndex)
    {

    }

    public int Count
    {
        get { return this.list.Count; }
    }

    public bool IsReadOnly
    {
        get { return false; }
    }

    public bool Remove(KeyValuePair<string, object> item)
    {
        return this.list.Remove(item.Key);
    }

    public IEnumerator<KeyValuePair<string, object>> GetEnumerator()
    {
        return this.list.GetEnumerator();
    }

    System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator()
    {
        return this.list.GetEnumerator();
    }
}
{% endhighlight %}
{% endtabs %}

![Binding with dynamic data object in Xamarin.Forms DataForm](SfDataForm_images/DynamicObject.png)

You can download the sample from [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/ComplexProperty-1726015503.zip)

## Adding custom DataFormItems

Support has been provided to generate custom DataFormItems for the defined business model using the [Items](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_Items) property of the `SfDataForm` class. You need to set the [AutoGenerateItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_AutoGenerateItems) property to false to restrict the auto generation of DataFormItems. 

{% tabs %}
{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
                        xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
                        xmlns:local="clr-namespace:GettingStarted"
                        xmlns:dataForm ="clr-namespace:Syncfusion.XForms.DataForm;assembly=Syncfusion.SfDataForm.XForms"
                        x:Class="GettingStarted.MainPage">
    <ContentPage.BindingContext>
        <local:ViewModel x:Name="bindingContext"/>
    </ContentPage.BindingContext>

    <ContentPage.Content>
        <dataForm:SfDataForm x:Name="dataForm" DataObject="{Binding Details}"  AutoGenerateItems="false"> 
            <dataForm:SfDataForm.Items> 
                <dataForm:DataFormTextItem Name="Name" Editor="Text"/> 
                <dataForm:DataFormTextItem Name="Password" Editor="Password"/> 
                <dataForm:DataFormMaskedEditTextItem Name="Phone" Editor="MaskedEditText"/> 
                <dataForm:DataFormTextItem Name="Address" Editor="MultilineText"/> 
                <dataForm:DataFormAutoCompleteItem Name="Countries" Editor="AutoComplete" ItemsSource = "{Binding CountryNames}"/> 
                <dataForm:DataFormDateItem Name="BirthTime" Editor="Date"/> 
            </dataForm:SfDataForm.Items> 
        </dataForm:SfDataForm>
    </ContentPage.Content>
</ContentPage>
{% endhighlight %}
{% highlight c# %}
ObservableCollection<DataFormItemBase> items = new ObservableCollection<DataFormItemBase>();
items.Add(new DataFormTextItem() { Name = "Name", Editor = "Text" });
items.Add(new DataFormTextItem() { Name = "Password", Editor = "Password" });
items.Add(new DataFormMaskedEditTextItem() { Name = "Phone", Editor = "MaskedEditText" });
items.Add(new DataFormTextItem() { Name = "Address", Editor = "MultilineText" });
items.Add(new DataFormAutoCompleteItem() { Name = "Countries", Editor = "AutoComplete", ItemsSource = this.GetItemSource("Countries")});
items.Add(new DataFormTimeItem() { Name = "BirthTime", Editor = "Time" }); 
dataForm.AutoGenerateItems = false; 
dataForm.Items = items; 

 public class ViewModel
    {
        private DataFormModel details;
        private IList<string> countryNames;
        public ViewModel()
        {
            details = new DataFormModel();
            countryNames = new List<string>
            {
                "United states",
                "United Kingdom",
                "France",
                "Belgium",
                "Germany"
            };
        }

        public DataFormModel Details
        {
            get { return this.details; }
            set { this.details = value; }
        }
        public IList<string> CountryNames
        {
            get { return this.countryNames; }
            set { this.countryNames = value; }
        }
    }

    private IList GetItemSource(string sourceName) 
    { 
        var list = new List<string>(); 
        if (sourceName == "Countries") 
        { 
            list.Add("Afghanistan");
            list.Add("Akrotiri");
            list.Add("Albania");
            list.Add("Algeria");
            list.Add("American Samoa");
            list.Add("Andorra");
            list.Add("Angola");
            list.Add("Anguilla");
            list.Add("Antarctica");
            list.Add("Antigua and Barbuda");
        } 
        return list; 
    }
{% endhighlight %}
{% endtabs %}

### Dynamically add custom dataform items
Support has been provided to dynamically add the dataform items to collections using the [Items](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_Items) property of `SfDataForm`.

{% tabs %}
{% highlight c# %}
dataForm.Items.Add(new DataFormDropDownItem() 
				  { Name = "StateName", 
					Editor = "DropDown", 
					ItemsSource = this.GetItemSource("StateName"), 
					PlaceHolderText = "Select a State" 
				  });
				
dataForm.Items.Add(new DataFormItem() 
				  { Name = "Save", 
				    Editor = "Switch" 
				  });
{% endhighlight %}
{% endtabs %}

![Adding data form items in Xamarin.Forms DataForm](SfDataForm_images/AddCustomItems.gif)

### Dynamically remove custom dataform items
Support has been provided to dynamically remove the dataform items from collections using the [Items](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_Items) property of `SfDataForm`.

{% tabs %}
{% highlight c# %}
dataForm.Items.RemoveAt(2);
{% endhighlight %}
{% endtabs %}

![Removing data form items in Xamarin.Forms DataForm](SfDataForm_images/RemoveCustomItems.gif)

### Dynamically clear custom dataform items
Support has been provided to dynamically clear the dataform items using the [Items](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_Items) property of `SfDataForm`.

{% tabs %}
{% highlight c# %}
dataForm.Items.Clear();
{% endhighlight %}
{% endtabs %}

![Clear data form items in Xamarin.Forms DataForm](SfDataForm_images/ClearCustomItems.gif)

### Dynamically reset custom dataform items
Support has been provided to reset the dataform items using the [Items](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_Items) property of `SfDataForm`.

{% tabs %}
{% highlight c# %}
var item = dataForm.Items[2];
item = new DataFormNumericUpDownItem() { Name = "Age", Editor = "NumericUpDown" };
dataForm.Items[2] = item;
{% endhighlight %}
{% endtabs %}


### Dynamically add custom dataform group items
Support has been provided to dynamically add custom group items using [Items](https://help.syncfusion.com/cr/xamarin/Syncfusion.XForms.DataForm.SfDataForm.html#Syncfusion_XForms_DataForm_SfDataForm_Items) property of `SfDataForm`.
{% tabs %}
{% highlight c# %}
DataFormGroupItem dataFormGroupItem = new DataFormGroupItem();
dataFormGroupItem.GroupName = "GroupItem";
dataFormGroupItem.IsExpanded = true;
dataFormGroupItem.DataFormItems = new DataFormItems();

dataFormGroupItem.DataFormItems.Add(new DataFormTextItem() { Name = "First Name", Editor = "Text", GroupName = "GroupItem" });
dataFormGroupItem.DataFormItems.Add(new DataFormTextItem() { Name = "Middle Name", Editor = "Text", GroupName = "GroupItem" });
dataFormGroupItem.DataFormItems.Add(new DataFormTextItem() { Name = "Last Name", Editor = "Text", GroupName = "GroupItem" });

dataForm.Items.Add(dataFormGroupItem);
{% endhighlight %}
{% endtabs %}

![Group data form items in Xamarin.Forms DataForm](SfDataForm_images/GroupItems.jpg)

