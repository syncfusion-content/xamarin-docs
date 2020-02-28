---
layout: post
title: Working with MVVM | SfDataGrid | Xamarin | Syncfusion
description: Describes about how to use the SfDataGrid in MVVM and binding the ViewModel property to the SfDataGrid Controls. 
platform: xamarin
control: SfDataGrid
documentation: UG
---
# Working With MVVM in SfDataGrid

## Binding SfDataGrid.SelectedIndex property
You can bind any int value to the bindable property [SfDataGrid.SelectedIndex](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~SelectedIndex.html) which gets or sets the lastly selected row's index in the SfDataGrid.

Refer the below code to bind the `SfDataGrid.SelectedIndex` from the ViewModel.

{% highlight xaml %}

 <sfgrid:SfDataGrid x:Name="dataGrid"
                    AutoGenerateColumns="true" 
                    ItemsSource="{Binding State}"
                    SelectionMode="Multiple"
                    SelectedIndex="{Binding SelectedIndex}">
 </sfgrid:SfDataGrid>

{% endhighlight %}

{% highlight c# %}

        //ViewModel.cs code

        private int _selectedIndex;

        public int SelectedIndex
        {
            get { return _selectedIndex; }
            set { this._selectedIndex = value;
			RaisePropertyChanged("SelectedIndex"); }
        }

         public ViewModel()
        {
           this.SelectedIndex = 5;
        }

{% endhighlight %}


## Binding SfDataGrid.SelectedItem property

You can bind any object value to the bindable property [SfDataGrid.SelectedItem](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~SelectedItem.html) which gets or sets the selected item in the SfDataGrid.

Refer the below code to bind the `SfDataGrid.SelectedItem` from the ViewModel.

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
            this.SelectedItem = State[8];
        }
		
{% endhighlight %}



## Binding SfDataGrid.SelectedItems property
You can bind any object type collection to the bindable property SfDataGrid[SfDataGrid.SelectedItems](http://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.SfDataGrid~SelectedItems.html) which gets or sets the collection of `SelectedItems` collection in the SfDataGrid.

Refer the below code to bind the `SfDataGrid.SelectedItems` from the ViewModel.

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
          this.SelectedItems.Add(State[1]);
          this.SelectedItems.Add(State[5]);
          this.SelectedItems.Add(State[8]);
        }

{% endhighlight %}



## Binding GridColumn properties

You can also assign value via binding to the properties of the [GridColumn](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn.html) such as [HeaderCellTextSize](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~HeaderCellTextSize.html),[CellTextSize](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~CellTextSize.html),[FontAttribute](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~FontAttribute.html),[RecordFont](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~RecordFont.html),[HeaderFont](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~HeaderFont.html) etc. 

Refer the below code to bind the GridColumn properties from the ViewModel.

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
            set { this.TextSize = value; RaisePropertyChanged("CellTextSize"); }
        }

         public ViewModel()
        {
          this.CellTextSize = 20;
        }

{% endhighlight %}



## Binding GridPickerColumn ItemsSource from ViewModel

You can assign any object typed collection to the [GridPickerColumn.ItemsSource](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridPickerColumn~ItemsSource.html) to display a list of items in the `GridPickerColumn` when entering edit mode. 

Refer the below code to bind the ItemsSource of GridPickerColumn from the ViewModel.

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
            StatesProvince.Add("Central");
            StatesProvince.Add("Eastern");
            StatesProvince.Add("NorthEastern");
            StatesProvince.Add("Northern");
            StatesProvince.Add("Southern");
            StatesProvince.Add("Western");
        }
		 public void AddStateDetails()
        {
            State.Add(new StateDetails("Andhra Pradesh", "Amaravati ", "Visakhapatnam", "Telugu", "Southern", 49506799));
            State.Add(new StateDetails("Tamil Nadu", "Chennai", "Chennai", "Tamil", "Southern", 72147030));
            State.Add(new StateDetails("Karnataka", "Bangalore", "Bangalore", "Kannada","Southern", 61095297));
            State.Add(new StateDetails("Himachal Pradesh", "Shimla ", "Shimla ", "Hindi", "Northern", 6864602));
		}
	}

{% endhighlight %}



## Binding the ItemsSource in ViewModel to the Picker loaded inside template

The `ItemsSource` of a picker which is loaded inside the [GridTemplateColumn](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridTemplateColumn.html) can also be assigned any value via binding by passing the binding context as the `Source` to the `ItemsSource` property.

Refer the below code to bind the ItemsSource of Picker loaded inside the GridTemplateColumn from the ViewModel.

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
            StatesProvince.Add("Central");
            StatesProvince.Add("Eastern");
            StatesProvince.Add("NorthEastern");
            StatesProvince.Add("Northern");
            StatesProvince.Add("Southern");
            StatesProvince.Add("Western");
        }
		 public void AddStateDetails()
        {
            State.Add(new StateDetails("Andhra Pradesh", "Amaravati ", "Visakhapatnam", "Telugu", "Southern", 49506799));
            State.Add(new StateDetails("Tamil Nadu", "Chennai", "Chennai", "Tamil", "Southern", 72147030));
            State.Add(new StateDetails("Karnataka", "Bangalore", "Bangalore", "Kannada","Southern", 61095297));
            State.Add(new StateDetails("Himachal Pradesh", "Shimla ", "Shimla ", "Hindi", "Northern", 6864602));
		}
	}
	


{% endhighlight %}

## Binding the button command in template column to ViewModel

You can also assign any value to the Command property of the Button loaded inside the GridTemplateColumn via binding.

Refer the below code to bind the command property of Button loaded inside the GridTemplateColumn from the ViewModel.

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

You can download the source code of binding the SfDataGrid properties sample [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/SfGrid_Sample788022149)

## Binding SfDataGrid column from ViewModel

you can bind any `Columns` type collection property to the [SfDataGrid.Columns](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.Columns.html) property. Which gets or sets the `Columns` of the SfDataGrid.

Refer the below code snippet to bind `SfDataGrid.Columns` property from the viewmodel.

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
            State.Add(new StateDetails("Andhra Pradesh", "Amaravati ", "Visakhapatnam", "Telugu", Province.Southern, 49506799));
            State.Add(new StateDetails("Tamil Nadu", "Chennai", "Chennai", "Tamil", Province.Southern, 72147030));
            State.Add(new StateDetails("Karnataka", "Bangalore", "Bangalore", "Kannada", Province.Southern, 61095297));
            State.Add(new StateDetails("Himachal Pradesh", "Shimla ", "Shimla ", "Hindi", Province.Northern, 6864602));
		}
	}
		
{% endhighlight %}

{% endtab %}



## Binding the GridComboBoxColumn ItemSource from viewModel

You can bind any object type collection property to the [GridComboBoxColumn.ItemsSource](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridComboBoxColumn~ItemsSource.html) property to display a list of items in the `GridComboBoxColumn` when entering edit mode.

Refer the below code snippet to bind `GridComboBoxColumn.ItemsSource` property from the viewmodel.

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
            StatesProvince.Add("Central");
            StatesProvince.Add("Eastern");
            StatesProvince.Add("NorthEastern");
            StatesProvince.Add("Northern");
            StatesProvince.Add("Southern");
            StatesProvince.Add("Western");
        }
		 public void AddStateDetails()
        {
            State.Add(new StateDetails("Andhra Pradesh", "Amaravati ", "Visakhapatnam", "Telugu", "Southern", 49506799));
            State.Add(new StateDetails("Tamil Nadu", "Chennai", "Chennai", "Tamil", "Southern", 72147030));
            State.Add(new StateDetails("Karnataka", "Bangalore", "Bangalore", "Kannada","Southern", 61095297));
            State.Add(new StateDetails("Himachal Pradesh", "Shimla ", "Shimla ", "Hindi", "Northern", 6864602));
		}
	}
		
{% endhighlight %}

{% endtab %}



## Binding the ItemsSource in ViewModel to the SfComboBox loaded inside the template

You can bind the any object type collection property to the `SfComboBox.DataSource` property which is loaded inside the [GridTemplateColumn] (https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridTemplateColumn.html) can also be assigned any value via binding by passing the binding context as the `Source` to the `DataSource` property.

Refer the below code snippet to bind `SfComboBox.DataSource` property from the viewmodel. SfComboBox was loaded inside the the template.

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
            StatesProvince.Add("Central");
            StatesProvince.Add("Eastern");
            StatesProvince.Add("NorthEastern");
            StatesProvince.Add("Northern");
            StatesProvince.Add("Southern");
            StatesProvince.Add("Western");
        }
		 public void AddStateDetails()
        {
            State.Add(new StateDetails("Andhra Pradesh", "Amaravati ", "Visakhapatnam", "Telugu", "Southern", 49506799));
            State.Add(new StateDetails("Tamil Nadu", "Chennai", "Chennai", "Tamil", "Southern", 72147030));
            State.Add(new StateDetails("Karnataka", "Bangalore", "Bangalore", "Kannada","Southern", 61095297));
            State.Add(new StateDetails("Himachal Pradesh", "Shimla ", "Shimla ", "Hindi", "Northern", 6864602));
		}
	}
		
{% endhighlight %}

{% endtab %}


## Hide column from DataGrid using Button Click in MVVM

You can bind the bool property to the [GridColumn.IsHidden] (https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfDataGrid.XForms~Syncfusion.SfDataGrid.XForms.GridColumn~IsHidden.html) property from the viewmodel. `IsHidden` was handled by button click command.

Refer the below code snippet to Hide column from DataGrid using button click in MVVM

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
            <Button Text="HidePopulationColumn" Command="{Binding HideColumnCommand}"/>
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


## Filtering in DataGrid using MVVM

In Model-View-ViewModel, SfDataGrid support to filtering the records by setting behavior for the `ContentPage`. In order to filter the records, assign the filtered strings to the viewmodel.FilterText property which will be later applied in FilterPredicate that is assigned to SfDataGrid.View.Filter in OnFilterChanged() method. Call the SfDataGrid.View.RefreshFilter() method after setting the filtered records to the SfDataGrid.View.Filter property.

* To filter records in all the columns or in a particular column, use codes in `OnColumnsSelectionChanged` method.
* In order to column based filtering, the records can be filtered based on `Equals`,`Not Equals`,`Contains` conditions.
* To filter records in all the columns or particular column, use codes in `OnFilterOptionsChanged` method.

Refer the below code snippet to filter the records in SfDataGrid from viewModel. ViewModel illustrates the method used to filter the records.

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

The Event and Binding properties of the SfDataGrid can be handled by the behavior.

<% tab %>

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

In ViewModel, filtering methods and properties was implemented and method will be called when `OnFilterChanged` triggered.

<% tab %>

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

<% endtab %>
