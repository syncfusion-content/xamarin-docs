---
layout: post
title: Editing | SfDataGrid | Xamarin | Syncfusion
description: Editing the cell values with SfDataGrid.
platform: xamarin
control: SfDataGrid
documentation: ug
---

# Editing

The SfDataGrid supports for editing the cell values by setting the [SfDataGrid.AllowEditing](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~AllowEditing.html) property.

To enable editing, follow the code example:

{% tabs %}
{% highlight xaml %}
<syncfusion:SfDataGrid x:Name="dataGrid"
                       AllowEditing="True"
                       AutoGenerateColumns="True"
                       ItemsSource="{Binding Orders}" />
{% endhighlight %}
{% highlight c# %}
dataGrid.AllowEditing = true;
{% endhighlight %}
{% endtabs %}

![](SfDataGrid_images/Editing_Column_Forms.png)

## Column editing

To enable or disable editing for a particular column, set the [GridColumn.AllowEditing](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~AllowEditing.html) property.

{% tabs %}
{% highlight xaml %}
<syncfusion:GridTextColumn AllowEditing="True" MappingName="OrderID" />
{% endhighlight %}
{% highlight c# %}
GridTextColumn column = new GridTextColumn();
column.MappingName="OrderID";
column.AllowEditing = false;
{% endhighlight %}
{% endtabs %}

N>The `GridColumn.AllowEditing` takes higher priority than the `SfDataGrid.AllowEditing`.

## Entering into edit mode

To enter into edit mode by just tapping or double tapping the grid cells, set the [SfDataGrid.EditTapAction](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~EditTapAction.html) property.

{% tabs %}
{% highlight xaml %}
<sfgrid:SfDataGrid x:Name="dataGrid"
                           AllowEditing="True"
                           AutoGenerateColumns="True"
                           EditTapAction="OnTap">
{% endhighlight %}
{% highlight c# %}
//Enter edit mode in single tap
this.dataGrid.EditTapAction = TapAction.OnTap;
//Enter edit mode in double tap
this.dataGrid.EditTapAction = TapAction.OnDoubleTap;
{% endhighlight %}
{% endtabs %}

N> The keyboard will be collapsed when editing grid cell gets unfocused.

## Cursor behavior

When the cell enters into edit mode, cursor is placed based on the [SfDataGrid.EditorSelectionBehavior](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~EditorSelectionBehavior.html) property.

 * SelectAll: Selects the text of edit element loaded inside cell.
 * MoveLast: Places the cursor to the end of edit element loaded inside cell.

{% tabs %}
{% highlight xaml %}
<sfgrid:SfDataGrid x:Name="dataGrid"
                           AllowEditing="True"
                           AutoGenerateColumns="True"
                           EditTapAction="OnTap"
                           EditorSelectionBehavior="SelectAll">
{% endhighlight %}
{% highlight c# %}
//Selects all the text in the edit mode
this.dataGrid.EditorSelectionBehavior = EditorSelectionBehavior.SelectAll;
//Places the cursor at the last
this.dataGrid.EditorSelectionBehavior = EditorSelectionBehavior.MoveLast;
{% endhighlight %}
{% endtabs %}

N> Editing supports for GridTemplateColumn and GridUnboundColumn are not provided yet.

## Support for IEditableObject

The SfDataGrid supports to commit and roll back the changes in row level when underlying data object implements the [IEditableObject](https://msdn.microsoft.com/en-us/library/system.componentmodel.ieditableobject.aspx) interface.

The editing changes in a row will be committed only when tapping on next row.

The `IEditableObject` has the following methods to capture editing:

 * [BeginEdit](https://msdn.microsoft.com/en-us/library/system.componentmodel.ieditableobject.beginedit.aspx): Gets called to begin edit on underlying data object when cells in a row enters into edit mode.
 * [CancelEdit](https://msdn.microsoft.com/en-us/library/system.componentmodel.ieditableobject.canceledit.aspx): Gets called when you cancel editing to discard the changes in a row since last BeginEdit call.
 * [EndEdit](https://msdn.microsoft.com/en-us/library/system.componentmodel.ieditableobject.endedit.aspx): Gets called when you move to the next row by tapping to commit changes in underlying data object since last BeginEdit call.

The following code snippet explains the simple implementation of `IEditableObject`:

{% highlight c# %}
public class OrderInfo : INotifyPropertyChanged, IEditableObject
{
    public OrderInfo()
    {
    }

    #region private variables

    private int _orderID;
    private int _employeeID;
    private int _customerID;
    private bool _isClosed;
    private string _firstName;
    private string _lastName;
    private string _gender;
    private string _shipCity;
    private string _shipCountry;
    private string _freight;
    private DateTime _shippingDate;

    #endregion

    #region Public Properties

    public int OrderID
    {
        get { return _orderID; }
        set
        {
            this._orderID = value;
            RaisePropertyChanged("OrderID");
        }
    }

    public int EmployeeID
    {
        get { return _employeeID; }
        set
        {
            this._employeeID = value;
            RaisePropertyChanged("EmployeeID");
        }
    }

    public int CustomerID
    {
        get { return _customerID; }
        set
        {
            this._customerID = value;
            RaisePropertyChanged("CustomerID");
        }
    }

    public bool IsClosed
    {
        get { return _isClosed; }
        set
        {
            this._isClosed = value;
            RaisePropertyChanged("IsClosed");
        }
    }

    public string FirstName
    {
        get { return _firstName; }
        set
        {
            this._firstName = value;
            RaisePropertyChanged("FirstName");
        }
    }

    public string LastName
    {
        get { return _lastName; }
        set
        {
            this._lastName = value;
            RaisePropertyChanged("LastName");
        }
    }

    public string Gender
    {
        get { return _gender; }
        set
        {
            this._gender = value;
            RaisePropertyChanged("Gender");
        }
    }

    public string ShipCity
    {
        get { return _shipCity; }
        set
        {
            this._shipCity = value;
            RaisePropertyChanged("ShipCity");
        }
    }

    public string ShipCountry
    {
        get { return _shipCountry; }
        set
        {
            this._shipCountry = value;
            RaisePropertyChanged("ShipCountry");
        }
    }

    public string Freight
    {
        get { return _freight; }
        set
        {
            this._freight = value;
            RaisePropertyChanged("Freight");
        }
    }

    public DateTime ShippingDate
    {
        get { return _shippingDate; }
        set
        {
            this._shippingDate = value;
            RaisePropertyChanged("ShippingDate");
        }
    }

    #endregion

    #region INotifyPropertyChanged implementation

    public event PropertyChangedEventHandler PropertyChanged;

	private void RaisePropertyChanged (String Name)
	{
		if (PropertyChanged != null)
			this.PropertyChanged (this, new PropertyChangedEventArgs (Name));
	}

    private Dictionary<string, object> storedValues;


    public void BeginEdit()
    {
        this.storedValues = this.BackUp();
    }

    public void CancelEdit()
    {
        if (this.storedValues == null)
            return;

        foreach (var item in this.storedValues)
        {
            var itemProperties = this.GetType().GetTypeInfo().DeclaredProperties;
            var pDesc = itemProperties.FirstOrDefault(p => p.Name == item.Key);
            if (pDesc != null)
                pDesc.SetValue(this, item.Value);
        }
    }

    public void EndEdit()
    {
        if (this.storedValues != null)
        {
            this.storedValues.Clear();
            this.storedValues = null;
        }
        Debug.WriteLine("End Edit Called");
    }

    protected Dictionary<string, object> BackUp()
    {
        var dictionary = new Dictionary<string, object>();
        var itemProperties = this.GetType().GetTypeInfo().DeclaredProperties;
        foreach (var pDescriptor in itemProperties)
        {
            if (pDescriptor.CanWrite)
                dictionary.Add(pDescriptor.Name, pDescriptor.GetValue(this));
        }
        return dictionary;
    }

    #endregion
}
{% endhighlight %}


## Editing events

The SfDataGrid triggers the following events while editing:

### CurrentCellBeginEdit

The [SfDataGrid.CurrentCellBeginEdit](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~CurrentCellBeginEdit_EV.html) event occurs when the CurrentCell enters into edit mode. The [GridCurrentCellBeginEditEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridCurrentCellBeginEditEventArgs.html) has the following members which provides information for `SfDataGrid.CurrentCellBeginEdit` event:

 * [Cancel](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true): When this member set to ‘true’, the event is canceled and the CurrentCell does not enter into the edit mode.
 * [RowColumnIndex](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridCurrentCellBeginEditEventArgs~RowColumnIndex.html): Gets the current row and column index of the DataGrid.
 * [Column](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridCurrentCellBeginEditEventArgs~Column.html): Gets the Grid Column of the SfDataGrid.

To hook the `SfDataGrid.CurrentCellBeginEdit` event, follow the code example:

{% highlight c# %}
this.dataGrid.CurrentCellBeginEdit += DataGrid_CurrentCellBeginEdit;

private void DataGrid_CurrentCellBeginEdit(object sender, GridCurrentCellBeginEditEventArgs args)
{
    // Editing prevented for the cell at RowColumnIndex(2,2).
    if (args.RowColumnIndex == new Syncfusion.GridCommon.ScrollAxis.RowColumnIndex(2, 2))
        args.Cancel = true;
}
{% endhighlight %}

### CurrentCellEndEdit

The [CurrentCellEndEdit](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~CurrentCellEndEdit_EV.html) event occurs when the CurrentCell exits the edit mode. The [GridCurrentCellEndEditEventArgs](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridCurrentCellEndEditEventArgs.html) has following members which provides information for `SfDataGrid.CurrentCellEndEdit` event:

 * [RowColumnIndex](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridCurrentCellEndEditEventArgs~RowColumnIndex.html): Gets the current row and column index of the DataGrid.
 * [Cancel](https://msdn.microsoft.com/query/dev10.query?appId=Dev10IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true): When this member set to ‘true’, the event is canceled and the edited value is not committed in the underlying collection.

To hook the `SfDataGrid.CurrentCellEndEdit` event, follow the code example:

{% highlight c# %}
this.dataGrid.CurrentCellEndEdit += DataGrid_CurrentCellEndEdit;

private void DataGrid_CurrentCellEndEdit(object sender, GridCurrentCellEndEditEventArgs args)
{
    // Editing prevented for the cell at RowColumnIndex(1,3).
    if (args.RowColumnIndex == new Syncfusion.GridCommon.ScrollAxis.RowColumnIndex(1,3))
        args.Cancel = true;
}
{% endhighlight %}

## Programmatically edit a cell

### Begin editing

The SfDataGrid allows to edit the cell programmatically by calling the [SfDataGrid.BeginEdit](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~BeginEdit.html) method. By calling this method, the particular cell enters into edit mode. It edits the data manually or programmatically. To edit a cell programmatically, follow the code example:

{% highlight c# %}
this.dataGrid.Loaded += dataGrid_Loaded;
void dataGrid_Loaded(object sender, RoutedEventArgs e)
{
    //Edit the cell at 2nd row,2nd column programmatically
    this.dataGrid.BeginEdit(2, 2);
}
{% endhighlight %}

### End editing

The [SfDataGrid.EndEdit](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~EndEdit.html) method can be called to programmatically end editing. A cell that is currently in edit mode commits the edited value to the underlying collection and exits the edit mode when this method is called. To end the editing programmatically, follow the code example:

{% highlight c# %}
this.dataGrid.EndEdit();
{% endhighlight %}

### Cancel editing

The [SfDatagrid.CancelEdit](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~CancelEdit.html) method can be called to programmatically cancel editing. A cell that is currently in edit mode exits the edit mode without committing the edited value in the underlying collection when this method is called. To cancel the editing programmatically, follow the code example:

{% highlight c# %}
this.dataGrid.CancelEdit();
{% endhighlight %}

## How to 

### Cancel editing

The [SfDataGrid.CurrentCellBeginEdit](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~CurrentCellBeginEdit_EV.html) event can be used to cancel the editing operation for the corresponding cell. To cancel the editing operation using the `SfDataGrid.CurrentCellBeginEdit` event, follow the code example:

{% highlight c# %}
this.dataGrid.CurrentCellBeginEdit += DataGrid_CurrentCellBeginEdit;
private void DataGrid_CurrentCellBeginEdit(object sender, GridCurrentCellBeginEditEventArgs args)
{
    if (args.Column.MappingName == "OrderID" || args.RowColumnIndex.RowIndex == 2)
        args.Cancel = true;
}
{% endhighlight %}

### Cancel edited value from getting committed

To prevent the edited value from getting committed, use the [CurrentCellEndEdit](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~CurrentCellEndEdit_EV.html) event. To prevent the edited values from getting committed in the underlying collection, follow the code example:

{% highlight c# %}
this.dataGrid.CurrentCellEndEdit += DataGrid_CurrentCellEndEdit;

private void DataGrid_CurrentCellEndEdit(object sender, GridCurrentCellEndEditEventArgs args)
{
    if (args.RowColumnIndex.RowIndex == 2)
        args.Cancel == true;
}
{% endhighlight %}