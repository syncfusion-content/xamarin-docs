---
layout: post
title: Popup using MVVM | SfPopupLayout |Xamarin | Syncfusion
description: Show the Xamarin.Forms Popup view in the Model-View-ViewModel
platform: Xamarin
control: SfPopupLayout
documentation: ug
--- 
#MVVM

##How to show Xamarin.Forms popup from ViewModel?

SfPopup can be used in MVVM architecture applications easily. In the below example [SfPopupLayout.IsOpen](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~IsOpen.html) property is binded to a property in the ViewModel based on which the popup is opened or closed. Refer the below code example to display popup in MVVM.

In the below code snippet, note that the Binding context is set for the page and the property (DisplayPopup) of the ViewModel is binded to the [SfPopupLayout.IsOpen](https://help.syncfusion.com/cr/cref_files/xamarin/sfpopuplayout/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~IsOpen.html).

{% tabs %}

{% highlight xaml %}

<ContentPage.BindingContext>
    <local:ViewModel />
</ContentPage.BindingContext>

<sfpopup:SfPopupLayout x:Name="popup" IsOpen="{Binding DisplayPopup}">
    <sfpopup:SfPopupLayout.Content>
        <StackLayout x:Name="rootView">
            <Button x:Name="isOpenButton" Text="Click to open popup" Command="{Binding OpenPopupCommand}"/>
        </StackLayout>
    </sfpopup:SfPopupLayout.Content>
</sfpopup:SfPopupLayout>

{% endhighlight %}

{% highlight c# %}

// ViewModel.cs

public class ViewModel : INotifyPropertyChanged
{
    private bool displayPopup;

    public ICommand OpenPopupCommand { get; set; }

    public bool DisplayPopup
    {
        get
        {
            return displayPopup;
        }
        set
        {
            displayPopup = value;
            RaisePropertyChanged("DisplayPopup");
        }
    }

    public ViewModel()
    {
        OpenPopupCommand = new Command(OpenPopup);
    }

    private void OpenPopup()
    {
        DisplayPopup = true;
    }

    #region INotifyPropertyChanged

    public event PropertyChangedEventHandler PropertyChanged;

    private void RaisePropertyChanged(string propertyName)
    {
        if(this.PropertyChanged != null)
        {
            this.PropertyChanged(this, new PropertyChangedEventArgs(propertyName));
        }
    }

    #endregion

}

{% endhighlight %}

{% endtabs %}

##How to use commands for popup buttons?

The commanding interface provides an alternative approach to implementing commands that is much better suited to the MVVM architecture. The ViewModel itself can contain commands, which are methods that are executed in reaction to a specific activity in the View such as a Button click will be fired the command.

In SfPopupLayout.PopupView we have two types of command:

*[SfPopupLayout.PopupView.AcceptCommand](https://help.syncfusion.com/xamarin/popup/popup-events?cs-save-lang=1&cs-lang=csharp#accept-command)
*[SfPopupLayout.PopupView.DeclineCommand](https://help.syncfusion.com/xamarin/popup/popup-events?cs-save-lang=1&cs-lang=csharp#decline-command)
