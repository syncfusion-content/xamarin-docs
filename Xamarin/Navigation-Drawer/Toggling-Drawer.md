---
layout: post
title: Toggle methods in Xamarin Navigation Drawer control | Syncfusion
description: Learn here all about Toggle methods support in Syncfusion Xamarin Navigation Drawer (SfNavigationDrawer) control and more.
platform: Xamarin
control: NavigationDrawer
documentation: ug
---
# Toggle methods in Xamarin Navigation Drawer (SfNavigationDrawer)

Drawer can be toggled using

*	[`IsOpen property`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html#Syncfusion_SfNavigationDrawer_XForms_SfNavigationDrawer_IsOpen)

*	[`ToggleDrawer method`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html#Syncfusion_SfNavigationDrawer_XForms_SfNavigationDrawer_ToggleDrawer)

*	[`Swipe gesture`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html#Syncfusion_SfNavigationDrawer_XForms_SfNavigationDrawer_EnableSwipeGesture)

## Opening Drawer Programmatically
[`IsOpen`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html#Syncfusion_SfNavigationDrawer_XForms_SfNavigationDrawer_IsOpen) property and [`ToggleDrawer`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html#Syncfusion_SfNavigationDrawer_XForms_SfNavigationDrawer_ToggleDrawer) method can be used to open or close the drawer programmatically.

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:NaviSample" 
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="NaviSample.MainPage">
    <navigationdrawer:SfNavigationDrawer x:Name="navigationDrawer" 
                                         IsOpen="True">
        <navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
            <Grid BackgroundColor="#1aa1d6" 
                  VerticalOptions="Center" 
                  HorizontalOptions="Center">
                <Label Text="Header view" 
                       FontSize="16" 
                       VerticalOptions="Center" 
                       HorizontalOptions="Center"/>
            </Grid>
        </navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
    </navigationdrawer:SfNavigationDrawer>
</ContentPage>

{% endhighlight %}	
	
{% highlight c# %} 

navigationDrawer.IsOpen = true;

{% endhighlight %}

{% endtabs %}

Using [`ToggleDrawer`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html#Syncfusion_SfNavigationDrawer_XForms_SfNavigationDrawer_ToggleDrawer) method,

{% highlight c# %} 

navigationDrawer.ToggleDrawer();

{% endhighlight %}

Toggling drawer by swipe gesture is explained in `Swipe Gesture and Sensitivity` section.

## Opening Drawer via Binding

[`SfNavigationDrawer`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html) can be used in any MVVM architecture application easily. In the below example, [`SfNavigationDrawer.IsOpen`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html#Syncfusion_SfNavigationDrawer_XForms_SfNavigationDrawer_IsOpen) property is bound to a property in the ViewModel, based on which the drawer is opened or closed. Refer the below code example to display drawer in MVVM.

In the following code sample, note that the Binding context is set for the page and the property (OpenDrawer) of the ViewModel is bound to the [`SfNavigationDrawer.IsOpen`](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfNavigationDrawer.XForms.SfNavigationDrawer.html#Syncfusion_SfNavigationDrawer_XForms_SfNavigationDrawer_IsOpen).

{% tabs %}

{% highlight xaml %}

<?xml version="1.0" encoding="utf-8"?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:NaviSample" 
             xmlns:navigationdrawer="clr-namespace:Syncfusion.SfNavigationDrawer.XForms;assembly=Syncfusion.SfNavigationDrawer.XForms"
             x:Class="NaviSample.MainPage">
     <ContentPage.BindingContext>
        <local:ViewModel />
    </ContentPage.BindingContext>
    <navigationdrawer:SfNavigationDrawer x:Name="navigationDrawer" 
                                         IsOpen="{Binding OpenDrawer,Mode=TwoWay}">
        <navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
            <Grid BackgroundColor="#1aa1d6" 
                  VerticalOptions="Center" 
                  HorizontalOptions="Center">
                <Button x:Name="isOpenButton" Text="Click to open Drawer" Command="{Binding OpenDrawerCommand}"/>
            </Grid>
        </navigationdrawer:SfNavigationDrawer.DrawerHeaderView>
    </navigationdrawer:SfNavigationDrawer>
</ContentPage>

{% endhighlight %}	
	
{% highlight c# %} 

using System.Windows.Input;
using Xamarin.Forms;
using System.ComponentModel;

// ViewModel.cs.
 public class ViewModel : INotifyPropertyChanged
    {
        private bool displayDrawer;

        public ICommand OpenDrawerCommand { get; set; }

        public bool OpenDrawer
        {
            get
            {
                return displayDrawer;
            }
            set
            {
                displayDrawer = value;
                RaisePropertyChanged("OpenDrawer");
            }
        }

        public ViewModel()
        {
            OpenDrawerCommand = new Command(OpenDrawerMethod);
        }

        private void OpenDrawerMethod()
        {
            OpenDrawer = true;
        }

        #region INotifyPropertyChanged

        public event PropertyChangedEventHandler PropertyChanged;

        private void RaisePropertyChanged(string propertyName)
        {
            if (this.PropertyChanged != null)
            {
                this.PropertyChanged(this, new PropertyChangedEventArgs(propertyName));
            }
        }

        #endregion

    }

{% endhighlight %}

{% endtabs %}
