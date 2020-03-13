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

You can bind any int value to the [SfDataGrid.SelectedIndex](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~SelectedIndex.html) property to apply selection to a row programmatically.

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

View sample in [Github](https://github.com/SyncfusionExamples/Xamarin-DataGrid-SelectedIndex-Binding-MVVM/tree/master).

## Xamarin.Forms DataGrid SelectedItem binding

You can bind an object from the underlying source collection to the [SfDataGrid.SelectedItem](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~SelectedItem.html) property to apply selection to a row programmatically.

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

View sample in [Github](https://github.com/SyncfusionExamples/Xamarin-DataGrid-SelectedItem-Binding-MVVM).

## Xamarin.Forms DataGrid SelectedItems binding

You can bind any object type collection to the [SfDataGrid.SelectedItems](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~SelectedItems.html) property to apply selection to multiple rows programmatically.

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

View sample in [Github](https://github.com/SyncfusionExamples/Xamarin-DataGrid-SelectedItems-Binding-MVVM).

## Xamarin.Forms DataGrid column properties binding

SfDataGrid allows you to assign values via binding to the properties of the [GridColumn](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html) such as [HeaderCellTextSize](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~HeaderCellTextSize.html), [CellTextSize](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~CellTextSize.html), [FontAttribute](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~FontAttribute.html), [RecordFont](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~RecordFont.html), [HeaderFont](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~HeaderFont.html) etc. 

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

View sample in [Github](https://github.com/SyncfusionExamples/Xamarin-DataGrid-Column-Properties-Binding-MVVM).

## Binding Picker Column ItemsSource from ViewModel in Xamarin.Forms DataGrid

You can bind any collection to the [GridPickerColumn.ItemsSource](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridPickerColumn~ItemsSource.html) property to display a list of items in the `GridPickerColumn` when entering edit mode.

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

View sample in [Github](https://github.com/SyncfusionExamples/Binding-Picker-Column--ItemsSource-from-ViewModel-in-Xamarin.Forms-DataGrid).

## Binding the ItemsSource from ViewModel for the Picker loaded inside template column in Xamarin.Forms DataGrid

The `ItemsSource` of a picker which is loaded inside the [GridTemplateColumn](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridTemplateColumn.html) can be assigned any value via binding by passing the binding context as the `Source` to the `ItemsSource` property.

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

View sample in [Github](https://github.com/SyncfusionExamples/Binding-the-ItemsSource-from-ViewModel-for-the-Picker-loaded-inside-template-column-in-Xamarin.Forms).

## Binding commands for the button loaded inside template column in Xamarin.Forms DataGrid

You can provide custom actions to the `Command` property of a button loaded inside the GridTemplateColumn via binding.

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

View sample in [Github](https://github.com/SyncfusionExamples/Binding-commands-for-the-button-loaded-inside-template-column-in-Xamarin.Forms-DataGrid).

## Binding columns collection from ViewModel in Xamarin.Forms DataGrid

You can bind any `Columns` type collection in the view model to the [SfDataGrid.Columns](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.Columns.html) property to load the necessary columns in the datagrid.

{% tab %}

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

{% endtab %}

View sample in [Github](https://github.com/SyncfusionExamples/Binding-Columns-in-Xamarin-DataGrid).

## Binding ComboBox Column ItemsSource from ViewModel in Xamarin.Forms DataGrid

You can bind any collection to the [GridComboBoxColumn.ItemsSource](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridComboBoxColumn~ItemsSource.html) property  to display a list of items in the `GridComboBoxColumn` when entering edit mode.

{% tab %}

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

{% endtab %}

View sample in [Github](https://github.com/SyncfusionExamples/Binding-ComboBox-Column-ItemsSource-from-ViewModel-in-Xamarin.Forms-DataGrid).

## Binding the ItemsSource from ViewModel for the SfComboBox loaded inside the template column in Xamarin.Forms DataGrid

You can bind any collection to the `SfComboBox.DataSource` property, which is loaded inside the [GridTemplateColumn] (https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridTemplateColumn.html) using the below code snippet.

{% tab %}

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

{% endtab %}

View sample in [Github](https://github.com/SyncfusionExamples/Binding-ItemsSource-for-the-SfComboBox-inside-template-column-in-Xamarin-DataGrid).

## Hide column in button click using MVVM in Xamarin.Forms DataGrid

Bind any bool property in the view model to the [GridColumn.IsHidden](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~IsHidden.html) property.
Refer the below code snippet where we have bound a command to a button click where we change the value of the bound bool property to hide/unhide a column.

{% tab %}

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

{% endtab %}

View sample in [Github](https://github.com/SyncfusionExamples/Hide-column-in-button-click-using-MVVM-in-Xamarin.Forms-DataGrid).

## Filtering in DataGrid using MVVM

Refer here[https://help.syncfusion.com/xamarin/datagrid/filtering#view-filtering], to know how to apply filtering in SfDataGrid. Upon referring, you might have noticed that we need the SfDataGrid instance to call the methods required for filtering. To achieve this in MVVM use `Xamarin.Forms.Behaviors` by assigning a behavior class to the page that contains SfDataGrid.
Refer the below code snippet to create a behavior class, and use that behavior class to filter the records in SfDataGrid from viewModel.

<% tab %>

<% highlight xaml %>

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:Filter"
             xmlns:sfgrid="clr-namespace:Syncfusion.SfDataGrid.XForms;assembly=Syncfusion.SfDataGrid.XForms"
             x:Class="Filter.MainPage">
    <ContentPage.Behaviors>
        <local:FilterBehavior/>
    </ContentPage.Behaviors>
    <ContentPage.Content>
        <StackLayout>
            <Grid ColumnSpacing="10" Padding="20">
                <Grid.RowDefinitions>
                    <RowDefinition Height="Auto" />
                    <RowDefinition Height="Auto" />
                </Grid.RowDefinitions>
                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="*" />
                    <ColumnDefinition Width="*" />
                </Grid.ColumnDefinitions>
                <Label x:Name="filterlabel"
                   Grid.Row="0"
                   Grid.Column="0"
                   Grid.ColumnSpan="2"
                  HorizontalOptions="Start"
                   Text="Filter Options"
                   VerticalOptions="Center" />
                <Picker x:Name="ColumnsList"
                             Grid.Row="1"
                             Grid.Column="0"
                             HorizontalOptions="Start"
                             WidthRequest="200">
                </Picker>
                <Picker x:Name="OptionsList"
                             Grid.Row="1"
                             Grid.Column="1"
                             HorizontalOptions="Start"
                             IsVisible="False"
                             WidthRequest="200">
                </Picker>
            </Grid>
            <Grid RowSpacing="0">
                <Grid.RowDefinitions>
                    <RowDefinition Height="Auto" />
                    <RowDefinition Height="Auto" />
                </Grid.RowDefinitions>
                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="*" />
                </Grid.ColumnDefinitions>
                <SearchBar x:Name="filterText"
                                Grid.Row="0"
                                Grid.Column="0"
                                IsVisible="true"
                                    HeightRequest="50"
                                    Margin="0,5,0,3"
                                Placeholder="Search here to filter" 
                                WidthRequest="300">
                </SearchBar>
                <sfgrid:SfDataGrid x:Name="dataGrid"
                               Grid.Row="2"
                               Grid.Column="0"
                               ItemsSource="{Binding BookInfo}"
                               AutoGenerateColumns="false"
                               ColumnSizer="Star"
                                SelectionMode="Single">
                    <sfgrid:SfDataGrid.Columns>
                        <sfgrid:GridTextColumn HeaderText="Book ID"
                                               MappingName="BookID"/>
                        <sfgrid:GridTextColumn HeaderText="Book Name"
                                               MappingName="BookName"/>
                        <sfgrid:GridTextColumn HeaderText="Customer ID"
                                               MappingName="CustomerID"/>
                        <sfgrid:GridTextColumn HeaderText="First Name"
                                               MappingName="FirstName"/>
                        <sfgrid:GridTextColumn HeaderText="Last Name"
                                               MappingName="LastName"/>
                    </sfgrid:SfDataGrid.Columns>
                </sfgrid:SfDataGrid>
            </Grid>
        </StackLayout>
    </ContentPage.Content>
</ContentPage>


<% endhighlight %>

<% endtab %>

The filter events and the methods consuming SfDataGrid can be handled from the behavior as shown below.

<% tab %>

 // Behavior.cs
 public class FilterBehavior : Behavior<ContentPage>
    {
 public void OnColumnsSelectionChanged(object sender, EventArgs e)
        {
            Picker newPicker = (Picker)sender;
            this.viewModel.SelectedColumn = newPicker.Items[newPicker.SelectedIndex];
            if (this.viewModel.SelectedColumn == "All Columns")
            {
                this.viewModel.SelectedCondition = "Contains";
                this.optionsList.IsVisible = false;
                this.OnFilterChanged();
            }
            else
            {
                this.optionsList.IsVisible = true;
                foreach (var prop in typeof(BookInfo).GetProperties())
                {
                    if (prop.Name == this.viewModel.SelectedColumn)
                    {
                        if (prop.PropertyType == typeof(string))
                        {
                            this.optionsList.Items.Clear();
                            this.optionsList.Items.Add("Contains");
                            this.optionsList.Items.Add("Equals");
                            this.optionsList.Items.Add("NotEquals");
                            if (this.viewModel.SelectedCondition == "Equals")
                            {
                                this.optionsList.SelectedIndex = 1;
                            }
                            else if (this.viewModel.SelectedCondition == "NotEquals")
                            {
                                this.optionsList.SelectedIndex = 2;
                            }
                            else
                            {
                                this.optionsList.SelectedIndex = 0;
                            }
                        }
                        else
                        {
                            this.optionsList.Items.Clear();
                            this.optionsList.Items.Add("Equals");
                            this.optionsList.Items.Add("NotEquals");
                            if (this.viewModel.SelectedCondition == "Equals")
                            {
                                this.optionsList.SelectedIndex = 0;
                            }
                            else
                            {
                                this.optionsList.SelectedIndex = 1;
                            }
                        }
                    }
                }
            }
        }
        public void OnFilterOptionsChanged(object sender, EventArgs e)
        {
            Picker newPicker = (Picker)sender;
            if (newPicker.SelectedIndex >= 0)
            {
                this.viewModel.SelectedCondition = newPicker.Items[newPicker.SelectedIndex];
                if (this.filterText.Text != null)
                {
                    this.OnFilterChanged();
                }
            }
        }
        #endregion
        #region FilterText Changed method
        public void OnFilterTextChanged(object sender, TextChangedEventArgs e)
        {
            if (e.NewTextValue == null)
            {
                this.viewModel.FilterText = string.Empty;
            }
            else
            {
                this.viewModel.FilterText = e.NewTextValue;
            }
        }

        public void OnFilterChanged()
        {
            if (this.dataGrid.View != null)
            {
                this.dataGrid.View.Filter = this.viewModel.FilterRecords;
                this.dataGrid.View.RefreshFilter();
            }
        }
		 protected override void OnAttachedTo(ContentPage bindAble)
        {
            this.viewModel = new FilteringViewModel();
            this.dataGrid = bindAble.FindByName<SfDataGrid>("dataGrid");
            bindAble.BindingContext = this.viewModel;
            this.optionsList = bindAble.FindByName<Picker>("OptionsList");
            this.columnsList = bindAble.FindByName<Picker>("ColumnsList");
            this.filterText = bindAble.FindByName<SearchBar>("filterText");
            this.optionsList.Items.Add("Equals");
            this.optionsList.Items.Add("NotEquals");
            this.optionsList.Items.Add("Contains");
            this.columnsList.Items.Add("All Columns");
            this.columnsList.Items.Add("CustomerID");
            this.columnsList.Items.Add("BookID");
            this.columnsList.Items.Add("FirstName");
            this.columnsList.Items.Add("LastName");
            this.columnsList.Items.Add("BookName");
            this.columnsList.SelectedIndex = 0;
            this.viewModel.Filtertextchanged = this.OnFilterChanged;
            this.filterText.TextChanged += this.OnFilterTextChanged;
            this.columnsList.SelectedIndexChanged += this.OnColumnsSelectionChanged;
            this.optionsList.SelectedIndexChanged += this.OnFilterOptionsChanged;
            base.OnAttachedTo(bindAble);
        }
	}

<% endtab %>

Refer the view model codes below, where the actual filtering takes place.

<% tab %>

   // ViewModel.cs
   public bool FilterRecords(object o)
        {
            double res;
            bool checkNumeric = double.TryParse(this.FilterText, out res);
            var item = o as BookInfo;
            if (item != null && this.FilterText.Equals(string.Empty) && !string.IsNullOrEmpty(this.FilterText))
            {
                return true;
            }
            else
            {
                if (item != null)
                {
                    if (checkNumeric && !this.SelectedColumn.Equals("All Columns") && !this.SelectedCondition.Equals("Contains"))
                    {
                        bool result = this.MakeNumericFilter(item, this.SelectedColumn, this.SelectedCondition);
                        return result;
                    }
                    else if (this.SelectedColumn.Equals("All Columns"))
                    {
                        if (item.BookName.ToLower().Contains(this.FilterText.ToLower()) ||
                            item.FirstName.ToString().ToLower().Contains(this.FilterText.ToLower()) ||
                            item.LastName.ToString().ToLower().Contains(this.FilterText.ToLower()) ||
                            item.CustomerID.ToString().ToLower().Contains(this.FilterText.ToLower()) ||
                            item.BookID.ToString().ToLower().Contains(this.FilterText.ToLower()))
                        {
                            return true;
                        }

                        return false;
                    }
                    else
                    {
                        bool result = this.MakeStringFilter(item, this.SelectedColumn, this.SelectedCondition);
                        return result;
                    }
                }
            }

            return false;
        }
 private void OnFilterTextChanged()
        {
            if (this.Filtertextchanged != null)
            {
                this.Filtertextchanged();
            }
        }

      private bool MakeStringFilter(BookInfo o, string option, string condition)
        {
            var value = o.GetType().GetProperty(option);
            var exactValue = value.GetValue(o, null);
            exactValue = exactValue.ToString().ToLower();
            string text = this.FilterText.ToLower();
            var methods = typeof(string).GetMethods();

            if (methods.Count() != 0)
            {
                if (condition == "Contains")
                {
                    var methodInfo = methods.FirstOrDefault(method => method.Name == condition);
                    bool result1 = (bool)methodInfo.Invoke(exactValue, new object[] { text });
                    return result1;
                }
                else if (exactValue.ToString() == text.ToString())
                {
                    bool result1 = string.Equals(exactValue.ToString(), text.ToString());
                    if (condition == "Equals")
                    {
                        return result1;
                    }
                    else if (condition == "NotEquals")
                    {
                        return false;
                    }
                }
                else if (condition == "NotEquals")
                {
                    return true;
                }

                return false;
            }
            else
            {
                return false;
            }
        }

         private bool MakeNumericFilter(BookInfo o, string option, string condition)
        {
            var value = o.GetType().GetProperty(option);
            var exactValue = value.GetValue(o, null);
            double res;
            bool checkNumeric = double.TryParse(exactValue.ToString(), out res);
            if (checkNumeric)
            {
                switch (condition)
                {
                    case "Equals":
                        try
                        {
                            if (exactValue.ToString() == this.FilterText)
                            {
                                if (Convert.ToDouble(exactValue) == Convert.ToDouble(this.FilterText))
                                {
                                    return true;
                                }
                            }
                        }
                        catch (Exception e)
                        {
                            Debug.WriteLine(e.Message);
                        }

                        break;
                    case "NotEquals":
                        try
                        {
                            if (Convert.ToDouble(this.FilterText) != Convert.ToDouble(exactValue))
                            {
                                return true;
                            }
                        }
                        catch (Exception e)
                        {
                            Debug.WriteLine(e.Message);
                            return true;
                        }

                        break;
                }
            }

            return false;
        }
    }
<% endtab %>

View sample in [Github]().

## Interaction commands in Xamarin.Forms DataGrid

The SfDataGrid provides command support for all the interactions such as tap, double tap and long press to support MVVM. Refer [here](https://help.syncfusion.com/xamarin/datagrid/grid-events#commands) to know about the available interaction commands.