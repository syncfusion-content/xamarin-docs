---
layout: post
title: Xamarin.Forms DataGrid MVVM | SfDataGrid | Xamarin | Syncfusion
description: Describes about how to use the Syncfusion Xamarin.Forms DataGrid in MVVM, use binding and commands to SfDataGrid properties. 
platform: xamarin
control: SfDataGrid
documentation: UG
---
# MVVM in Xamarin.Forms DataGrid (SfDataGrid)

## Xamarin.Forms DataGrid SelectedIndex binding

You can bind any int value to the [SfDataGrid.SelectedIndex](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_SelectedIndex) property to apply selection to a row programmatically.

{% tabs %}

{% highlight xaml %}

 <sfgrid:SfDataGrid x:Name="dataGrid"
                    AutoGenerateColumns="true" 
                    ItemsSource="{Binding State}"
                    SelectionMode="Multiple"
                    SelectedIndex="{Binding SelectedIndex}">
 </sfgrid:SfDataGrid>

{% endhighlight %}

{% highlight c# %}

        //ViewModel.cs

        private int _selectedIndex;

        public int SelectedIndex
        {
            get { return _selectedIndex; }
            set { this._selectedIndex = value;
			RaisePropertyChanged("SelectedIndex"); }
        }

        public ViewModel()
        {
           this.State = AddStateDetails();
           this.SelectedIndex = 5;
        }
        
        public void AddStateDetails()
        {
            State.Add(new StateDetails("California", "Sacramento ", "Sacramento", "English", "Western", 49506799));
            State.Add(new StateDetails("Florida", "Tallahassee", "Tallahassee", "English", "South Eastern", 72147030));
            State.Add(new StateDetails("Texas", "Austin", "Austin", "English","South Central", 61095297));
            State.Add(new StateDetails("New Jersey", "Trenton", "Trenton", "English", "North Eastern", 6864602));
		}

{% endhighlight %}

{% endtabs %}

View sample in [Github](https://github.com/SyncfusionExamples/Xamarin-DataGrid-SelectedIndex-Binding-MVVM/tree/master).

## Xamarin.Forms DataGrid SelectedItem binding

You can bind an object from the underlying source collection to the [SfDataGrid.SelectedItem](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_SelectedItem) property to apply selection to a row programmatically.

{% tabs %}

{% highlight xaml %}

 <sfgrid:SfDataGrid x:Name="dataGrid"
                    AutoGenerateColumns="False" 
                    ItemsSource="{Binding State}"
                    SelectionMode="Multiple"
                    SelectedItem="{Binding SelectedItem}">
 </sfgrid:SfDataGrid>

{% endhighlight %}

{% highlight c# %}

        //ViewModel.cs code

        private object _selectedItem;

        public object SelectedItem
        {
            get { return _selectedItem; }
            set { this._selectedItem = value; RaisePropertyChanged("SelectedItem"); }
        }

        public ViewModel()
        {
            this.State = this.AddStateDetails();
            this.SelectedItem = State[3];
        }
        
        public void AddStateDetails()
        {
            State.Add(new StateDetails("California", "Sacramento ", "Sacramento", "English", "Western", 49506799));
            State.Add(new StateDetails("Florida", "Tallahassee", "Tallahassee", "English", "South Eastern", 72147030));
            State.Add(new StateDetails("Texas", "Austin", "Austin", "English","South Central", 61095297));
            State.Add(new StateDetails("New Jersey", "Trenton", "Trenton", "English", "North Eastern", 6864602));
		}
		
{% endhighlight %}

{% endtabs %}

View sample in [Github](https://github.com/SyncfusionExamples/Xamarin-DataGrid-SelectedItem-Binding-MVVM).

## Xamarin.Forms DataGrid SelectedItems binding

You can bind any object type collection to the [SfDataGrid.SelectedItems](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.SfDataGrid.html#Syncfusion_SfDataGrid_XForms_SfDataGrid_SelectedItems) property to apply selection to multiple rows programmatically.

{% tabs %}

{% highlight xaml %}

 <sfgrid:SfDataGrid x:Name="dataGrid"
                    AutoGenerateColumns="False" 
                    ItemsSource="{Binding State}"
                    SelectionMode="Multiple"
                    SelectedItems="{Binding SelectedItems}">
 </sfgrid:SfDataGrid>

{% endhighlight %}

{% highlight c# %}

        //ViewModel.cs code

        private ObservableCollection<object> _selectedItems;

        public ObservableCollection<object> SelectedItems
        {
            get { return _selectedItems; }
            set { this._selectedItems = value; RaisePropertyChanged("SelectedItems"); }
        }

        public ViewModel()
        {
          this.State = this.AddStateDetails();
          this.SelectedItems.Add(State[1]);
          this.SelectedItems.Add(State[2]);
          this.SelectedItems.Add(State[3]);
        }
        
        public void AddStateDetails()
        {
            State.Add(new StateDetails("California", "Sacramento ", "Sacramento", "English", "Western", 49506799));
            State.Add(new StateDetails("Florida", "Tallahassee", "Tallahassee", "English", "South Eastern", 72147030));
            State.Add(new StateDetails("Texas", "Austin", "Austin", "English","South Central", 61095297));
            State.Add(new StateDetails("New Jersey", "Trenton", "Trenton", "English", "North Eastern", 6864602));
		}

{% endhighlight %}

{% endtabs %}

View sample in [Github](https://github.com/SyncfusionExamples/Xamarin-DataGrid-SelectedItems-Binding-MVVM).

## Xamarin.Forms DataGrid column properties binding

SfDataGrid allows you to assign values via binding to the properties of the [GridColumn](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridColumn.html) such as [HeaderCellTextSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridColumn.html#Syncfusion_SfDataGrid_XForms_GridColumn_HeaderCellTextSize), [CellTextSize](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridColumn.html#Syncfusion_SfDataGrid_XForms_GridColumn_CellTextSize), [FontAttribute](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridColumn.html#Syncfusion_SfDataGrid_XForms_GridColumn_FontAttribute), [RecordFont](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridColumn.html#Syncfusion_SfDataGrid_XForms_GridColumn_RecordFont), [HeaderFont](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridColumn.html#Syncfusion_SfDataGrid_XForms_GridColumn_HeaderFont) etc. 

{% tabs %}

{% highlight xaml %}

 <sfgrid:SfDataGrid x:Name="dataGrid"
                    AutoGenerateColumns="True" 
                    ItemsSource="{Binding State}">
    <sfgrid:SfDataGrid.Columns>
        <sfgrid:GridTextColumn MappingName="Name" CellTextSize="{Binding CellTextSize,Source={x:Reference viewModel}}"/>
    </sfgrid:SfDataGrid.Columns>
 </sfgrid:SfDataGrid>

{% endhighlight %}

{% highlight c# %}

        //ViewModel.cs code

        private double cellTextSize;

        public double CellTextSize
        {
            get { return cellTextSize; }
            set 
            { 
                this.TextSize = value;
                RaisePropertyChanged("CellTextSize");
            }
        }

        public ViewModel()
        {
           this.CellTextSize = 20;
        }

{% endhighlight %}

{% endtabs %}

View sample in [Github](https://github.com/SyncfusionExamples/Xamarin-DataGrid-Column-Properties-Binding-MVVM).

## Binding Picker Column ItemsSource from ViewModel in Xamarin.Forms DataGrid

You can bind any collection to the [GridPickerColumn.ItemsSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridPickerColumn.html#Syncfusion_SfDataGrid_XForms_GridPickerColumn_ItemsSource) property to display a list of items in the `GridPickerColumn` when entering edit mode.

{% tabs %}

{% highlight xaml %}

 <sfgrid:SfDataGrid x:Name="dataGrid"
                    AutoGenerateColumns="False" 
                    ItemsSource="{Binding State}">
    <sfgrid:SfDataGrid.Columns>
         <sfgrid:GridPickerColumn BindingContext="{x:Reference viewModel}"
                                  MappingName="Province" 
                                  ItemsSource="{Binding StatesProvince}" />
    </sfgrid:SfDataGrid.Columns>
 </sfgrid:SfDataGrid>

{% endhighlight %}

{% highlight c# %}

    //ViewModel.cs
    class ViewModel : INotifyPropertyChanged
    {  
	    private ObservableCollection<StateDetails> states = new ObservableCollection<StateDetails>();
	    private ObservableCollection<string> stateProvince = new ObservableCollection<string>();
	    
	    public ObservableCollection<string> StatesProvince
        {
            get { return stateProvince; }
            set 
            {  
                stateProvince = value;
                OnPropertyChanged(nameof(StatesProvince));
            }
		}
		
		public ObservableCollection<StateDetails> State
        {
            get { return states; }
            set {states = value;}
        }
        
		public ViewModel()
		{
		     AddProvince();
             AddStateDetails();
		}
		
		private void AddProvince()
        {
            StatesProvince.Add("South Central");
            StatesProvince.Add("Eastern");
            StatesProvince.Add("North Eastern");
            StatesProvince.Add("Northern");
            StatesProvince.Add("South Eastern");
            StatesProvince.Add("Western");
        }
        
		public void AddStateDetails()
        {
            State.Add(new StateDetails("California", "Sacramento ", "Sacramento", "English", "Western", 49506799));
            State.Add(new StateDetails("Florida", "Tallahassee", "Tallahassee", "English", "South Eastern", 72147030));
            State.Add(new StateDetails("Texas", "Austin", "Austin", "English","South Central", 61095297));
            State.Add(new StateDetails("New Jersey", "Trenton", "Trenton", "English", "North Eastern", 6864602));
		}
	}

{% endhighlight %}

{% endtabs %}

View sample in [Github](https://github.com/SyncfusionExamples/Binding-Picker-Column--ItemsSource-from-ViewModel-in-Xamarin.Forms-DataGrid).

## Binding the ItemsSource from ViewModel for the Picker loaded inside template column in Xamarin.Forms DataGrid

The `ItemsSource` of a picker which is loaded inside the [GridTemplateColumn](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridTemplateColumn.html) can be assigned any value via binding by passing the binding context as the `Source` to the `ItemsSource` property.

{% tabs %}

{% highlight xaml %}

 <sfgrid:SfDataGrid x:Name="dataGrid"
                    AutoGenerateColumns="False" 
                    ItemsSource="{Binding State}">
    <sfgrid:SfDataGrid.Columns>
         <sfgrid:GridTemplateColumn   MappingName="Province">
        <sfgrid:GridTemplateColumn.CellTemplate>
          <DataTemplate>
              <Picker ItemsSource="{Binding StatesProvince,Source={x:Reference viewModel}}" SelectedIndex="0"/>
          </DataTemplate>
        </sfgrid:GridTemplateColumn.CellTemplate>
    </sfgrid:GridTemplateColumn>
    </sfgrid:SfDataGrid.Columns>
 </sfgrid:SfDataGrid>

{% endhighlight %}

{% highlight c# %}

        //ViewModel.cs code

    class ViewModel : INotifyPropertyChanged
    {  
	   private ObservableCollection<StateDetails> states = new ObservableCollection<StateDetails>();
	   private ObservableCollection<string> stateProvince = new ObservableCollection<string>();
	   public ObservableCollection<string> StatesProvince
        {
            get { return stateProvince; }
            set {   stateProvince = value;
                OnPropertyChanged(nameof(StatesProvince));}
		}
		public ObservableCollection<StateDetails> State
        {
            get { return states; }
            set{states = value;}
        }
		public ViewModel()
		{
		     AddProvince();
             AddStateDetails();
		}
        
        private void AddProvince()
        {
            StatesProvince.Add("South Central");
            StatesProvince.Add("Eastern");
            StatesProvince.Add("North Eastern");
            StatesProvince.Add("Northern");
            StatesProvince.Add("South Eastern");
            StatesProvince.Add("Western");
        }
        
		public void AddStateDetails()
        {
            State.Add(new StateDetails("California", "Sacramento ", "Sacramento", "English", "Western", 49506799));
            State.Add(new StateDetails("Florida", "Tallahassee", "Tallahassee", "English", "South Eastern", 72147030));
            State.Add(new StateDetails("Texas", "Austin", "Austin", "English","South Central", 61095297));
            State.Add(new StateDetails("New Jersey", "Trenton", "Trenton", "English", "North Eastern", 6864602));
		}
	}

{% endhighlight %}

{% endtabs %}

View sample in [Github](https://github.com/SyncfusionExamples/Binding-the-ItemsSource-from-ViewModel-for-the-Picker-loaded-inside-template-column-in-Xamarin.Forms).

## Binding commands for the button loaded inside template column in Xamarin.Forms DataGrid

You can provide custom actions to the `Command` property of a button loaded inside the GridTemplateColumn via binding.

{% tabs %}

{% highlight xaml %}

 <sfgrid:SfDataGrid x:Name="dataGrid"
                    AutoGenerateColumns="False" 
                    ItemsSource="{Binding OrderInfoCollection}">
    <sfgrid:SfDataGrid.Columns>    
        <sfgrid:GridTemplateColumn MappingName="Customer">
             <sfgrid:GridTemplateColumn.CellTemplate>

                 <DataTemplate>
                     <Button Text="Template" Command="{Binding ButtonCommand,Source={x:Reference viewModel}}"/>
                 </DataTemplate>
            </sfgrid:GridTemplateColumn.CellTemplate>
        </sfgrid:GridTemplateColumn>
    </sfgrid:SfDataGrid.Columns>
 </sfgrid:SfDataGrid>

{% endhighlight %}

{% highlight c# %}

        //ViewModel.cs code

        private Command _buttonCommand;

        public Command ButtonCommand
        {
            get { return _buttonCommand; }
            set { this._buttonCommand = value;RaisePropertyChanged("ButtonCommand"); }
        }

         public ViewModel()
        {
          this.ButtonCommand = new Command(CustomMethod);
        }

        public void CustomMethod()
        {
            // Customize your code here
        }

{% endhighlight %}

{% endtabs %}

View sample in [Github](https://github.com/SyncfusionExamples/Binding-commands-for-the-button-loaded-inside-template-column-in-Xamarin.Forms-DataGrid).

## Binding columns collection from ViewModel in Xamarin.Forms DataGrid

You can bind any `Columns` type collection in the view model to the [SfDataGrid.Columns](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.Columns.html) property to load the necessary columns in the datagrid.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:UGMVVM"
             xmlns:sfgrid="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms"
             x:Class="MVVM.MainPage">
    <ContentPage.BindingContext>
        <local:ViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>
    <ContentPage.Content >
        <sfgrid:SfDataGrid ItemsSource="{Binding State}" 
                           NavigationMode="Cell"
                           ColumnSizer="Auto"
                           SelectionMode="Multiple"
                           AutoGenerateColumns="False"
                           Columns="{Binding SfGridColumns}">
        </sfgrid:SfDataGrid>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

// ViewModel.cs

 class ViewModel : INotifyPropertyChanged
    {
	    private Columns column = new Columns();
		private ObservableCollection<StateDetails> states = new ObservableCollection<StateDetails>();
	    public Columns SfGridColumns
        {
            get{return column;}
            set{column = value;}
        }
		public ObservableCollection<StateDetails> State
        {
            get { return states; }
            set{states = value;}
        }
		public ViewModel()
		{
		     AddStateDetails();
             GenerateColumn();
		}
		private void GenerateColumn()
        {
            SfGridColumns.Add(new GridTextColumn() {MappingName="Name" });
            SfGridColumns.Add(new GridTextColumn() {MappingName="LargestCity" });
            SfGridColumns.Add(new GridNumericColumn() {MappingName="Population" });
        }
		
		public void AddStateDetails()
        {
            State.Add(new StateDetails("California", "Sacramento ", "Sacramento", "English", "Western", 49506799));
            State.Add(new StateDetails("Florida", "Tallahassee", "Tallahassee", "English", "South Eastern", 72147030));
            State.Add(new StateDetails("Texas", "Austin", "Austin", "English","South Central", 61095297));
            State.Add(new StateDetails("New Jersey", "Trenton", "Trenton", "English", "North Eastern", 6864602));
		}
	}
		
{% endhighlight %}

{% endtabs %}

View sample in [Github](https://github.com/SyncfusionExamples/Binding-Columns-in-Xamarin-DataGrid).

## Binding ComboBox Column ItemsSource from ViewModel in Xamarin.Forms DataGrid

You can bind any collection to the [GridComboBoxColumn.ItemsSource](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridComboBoxColumn.html#Syncfusion_SfDataGrid_XForms_GridComboBoxColumn_ItemsSource) property  to display a list of items in the `GridComboBoxColumn` when entering edit mode.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:UGMVVM"
             xmlns:sfgrid="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms"
             x:Class="MVVM.MainPage">
    <ContentPage.BindingContext>
        <local:ViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>
    <ContentPage.Content >
        <sfgrid:SfDataGrid ItemsSource="{Binding State}" 
                           NavigationMode="Cell"
                           ColumnSizer="Auto"
                           SelectionMode="Multiple"
                           AutoGenerateColumns="True">
            <sfgrid:SfDataGrid.Columns>
                <sfgrid:GridComboBoxColumn AllowEditing="True"
                                           MappingName="Province"
                                           ItemsSource="{Binding StatesProvince}">
                </sfgrid:GridComboBoxColumn>
            </sfgrid:SfDataGrid.Columns>
        </sfgrid:SfDataGrid>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

// ViewModel.cs

    class ViewModel : INotifyPropertyChanged
    {  
	   private ObservableCollection<StateDetails> states = new ObservableCollection<StateDetails>();
	   private ObservableCollection<string> stateProvince = new ObservableCollection<string>();
	   public ObservableCollection<string> StatesProvince
       {
            get { return stateProvince; }
            set {   
                   stateProvince = value;
                   OnPropertyChanged(nameof(StatesProvince));
                }
	   }
	   public ObservableCollection<StateDetails> State
       {
           get { return states; }
           set{states = value;}
       }
       
	   public ViewModel()
	   {
		     AddProvince();
             AddStateDetails();
	   }
        private void AddProvince()
        {
            StatesProvince.Add("South Central");
            StatesProvince.Add("Eastern");
            StatesProvince.Add("North Eastern");
            StatesProvince.Add("Northern");
            StatesProvince.Add("South Eastern");
            StatesProvince.Add("Western");
        }
        
		public void AddStateDetails()
        {
            State.Add(new StateDetails("California", "Sacramento ", "Sacramento", "English", "Western", 49506799));
            State.Add(new StateDetails("Florida", "Tallahassee", "Tallahassee", "English", "South Eastern", 72147030));
            State.Add(new StateDetails("Texas", "Austin", "Austin", "English","South Central", 61095297));
            State.Add(new StateDetails("New Jersey", "Trenton", "Trenton", "English", "North Eastern", 6864602));
		}
	}
		
{% endhighlight %}

{% endtabs %}

View sample in [Github](https://github.com/SyncfusionExamples/Binding-ComboBox-Column-ItemsSource-from-ViewModel-in-Xamarin.Forms-DataGrid).

## Binding the ItemsSource from ViewModel for the SfComboBox loaded inside the template column in Xamarin.Forms DataGrid

You can bind any collection to the `SfComboBox.DataSource` property, which is loaded inside the [GridTemplateColumn](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridTemplateColumn.html) using the below code snippet.

{% tabs %}

{% highlight xaml %}
<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:UGMVVM"
             xmlns:sfgrid="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms"
             xmlns:combobox="clr-namespace:Syncfusion.XForms.ComboBox;assembly=Syncfusion.SfComboBox.XForms"
             x:Class="MVVM.MainPage">
    <ContentPage.BindingContext>
        <local:ViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>
    <ContentPage.Content >
        <sfgrid:SfDataGrid ItemsSource="{Binding State}" 
                             NavigationMode="Cell"
                               ColumnSizer="Auto"
                               SelectionMode="Multiple"
                            AutoGenerateColumns="True">
            <sfgrid:SfDataGrid.Columns>
                 <sfgrid:GridTemplateColumn MappingName="Province">
                    <sfgrid:GridTemplateColumn.CellTemplate>
                        <DataTemplate>
                            <combobox:SfComboBox BindingContext="{x:Reference viewModel}" 
                                                 DataSource="{Binding StatesProvince}"
                                                 WidthRequest="150"
                                                 IsEditableMode="True"
                                   />
                        </DataTemplate>
                    </sfgrid:GridTemplateColumn.CellTemplate>
                </sfgrid:GridTemplateColumn>
            </sfgrid:SfDataGrid.Columns>
           </sfgrid:SfDataGrid>
    </ContentPage.Content>
</ContentPage>

{% endhighlight %}

{% highlight c# %}

// ViewModel.cs

 class ViewModel : INotifyPropertyChanged
    {  
	   private ObservableCollection<StateDetails> states = new ObservableCollection<StateDetails>();
	   private ObservableCollection<string> stateProvince = new ObservableCollection<string>();
	   public ObservableCollection<string> StatesProvince
        {
            get { return stateProvince; }
            set {   stateProvince = value;
                OnPropertyChanged(nameof(StatesProvince));}
		}
		public ObservableCollection<StateDetails> State
        {
            get { return states; }
            set{states = value;}
        }
		public ViewModel()
		{
		     AddProvince();
             AddStateDetails();
		}
		 private void AddProvince()
        {
            StatesProvince.Add("South Central");
            StatesProvince.Add("Eastern");
            StatesProvince.Add("North Eastern");
            StatesProvince.Add("Northern");
            StatesProvince.Add("South Eastern");
            StatesProvince.Add("Western");
        }
        
		public void AddStateDetails()
        {
            State.Add(new StateDetails("California", "Sacramento ", "Sacramento", "English", "Western", 49506799));
            State.Add(new StateDetails("Florida", "Tallahassee", "Tallahassee", "English", "South Eastern", 72147030));
            State.Add(new StateDetails("Texas", "Austin", "Austin", "English","South Central", 61095297));
            State.Add(new StateDetails("New Jersey", "Trenton", "Trenton", "English", "North Eastern", 6864602));
		}
	}
		
{% endhighlight %}

{% endtabs %}

View sample in [Github](https://github.com/SyncfusionExamples/Binding-ItemsSource-for-the-SfComboBox-inside-template-column-in-Xamarin-DataGrid).

## Hide column in button click using MVVM in Xamarin.Forms DataGrid

Bind any bool property in the view model to the [GridColumn.IsHidden](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfDataGrid.XForms.GridColumn.html#Syncfusion_SfDataGrid_XForms_GridColumn_IsHidden) property.
Refer the below code snippet where we have bound a command to a button click where we change the value of the bound bool property to hide/unhide a column.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:UGMVVM"
             xmlns:sfgrid="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms"
             xmlns:combobox="clr-namespace:Syncfusion.XForms.ComboBox;assembly=Syncfusion.SfComboBox.XForms"
             x:Class="MVVM.MainPage">
    <ContentPage.BindingContext>
        <local:ViewModel x:Name="viewModel"/>
    </ContentPage.BindingContext>
    <ContentPage.Content >
        <StackLayout>
            <Button Text="Hide Population Column" Command="{Binding HideColumnCommand}"/>
            <sfgrid:SfDataGrid ItemsSource="{Binding State}" 
                               NavigationMode="Cell"
                               ColumnSizer="Auto"
                            AutoGenerateColumns="True">
                <sfgrid:SfDataGrid.Columns>
                  <sfgrid:GridNumericColumn
                        MappingName="Population"
                        IsHidden="{Binding IsHidden}"/>
                </sfgrid:SfDataGrid.Columns>
            </sfgrid:SfDataGrid>
        </StackLayout>
    </ContentPage.Content>
</ContentPage>


{% endhighlight %}

{% highlight c# %}

// ViewModel.cs

 class ViewModel : INotifyPropertyChanged
    {  
	   
	    public ICommand HideColumnCommand { get; set; }
		private bool isHidden;
		public bool IsHidden
        {
            get { return isHidden; }
            set { isHidden = value;
                OnPropertyChanged("IsHidden");
            }
        }
        
		public ViewModel()
		{
		    IsHidden = false;
            HideColumnCommand = new Command(HideOrUnHideColumn);
		}
		
		private void HideOrUnHideColumnColumn()
        {
            IsHidden = !IsHidden;
			OnPropertyChanged(nameof(IsHidden));
        }
	}
		
{% endhighlight %}

{% endtabs %}

View sample in [Github](https://github.com/SyncfusionExamples/Hide-column-in-button-click-using-MVVM-in-Xamarin.Forms-DataGrid).

## Filtering in DataGrid using MVVM

You can refer [here](https://help.syncfusion.com/xamarin/datagrid/filtering#view-filtering), to know how to apply filtering in SfDataGrid using MVVM.

## Interaction commands in Xamarin.Forms DataGrid

The SfDataGrid provides command support for all the interactions such as tap, double tap and long press to support MVVM. Refer [here](https://help.syncfusion.com/xamarin/datagrid/grid-events#commands) to know about the available interaction commands.