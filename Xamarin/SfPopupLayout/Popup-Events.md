---
layout: post
title: Popup Events| SfPopupLayout |Xamarin| Syncfusion
description: Use the built-in events available in Xamarin.Forms PopupLayout to control the opening and closing of popup based on conditions or requirements.
platform: Xamarin
control: SfPopupLayout
documentation: ug
--- 

# Popup Events And Commands

There are four built-in events in the SfPopupLayout control namely:

* Opening
* Opened
* Closing
* Closed

## Opening event

The [SfPopupLayout.Opening](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~Opening_EV.html) event will be fired whenever opening the PopupView in the application. It can cancel popup opening with `CancelEventArgs` that contains the following property:

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true): Popup opening is based on this value.

{% tabs %}
{%highlight Xaml%}
<sfPopup:SfPopupLayout x:Name="popupLayout" Opening="PopupLayout_Opening"/>
{%endhighlight%}

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.Opening += PopupLayout_Opening;
    ....
}

private void PopupLayout_Opening(object sender, System.ComponentModel.CancelEventArgs e)
{
    e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

## Opened event

The [SfPopupLayout.Opened](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~Opened_EV.html) event will be fired whenever displaying the PopupView in the application.

You can execute your own set of codes once the popup is opened, and visible in the application in its respective event handler.

{% tabs %}
{%highlight Xaml%}
<sfPopup:SfPopupLayout x:Name="popupLayout" Opened="PopupLayout_Opened"/>
{%endhighlight%}

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.Opened += PopupLayout_Opened;
    ....
}

private void PopupLayout_Opened(object sender, EventArgs e)
{
   // Codes that needs to be executed once popup is visible in the screen.
}
{% endhighlight %}
{% endtabs %}

## How to close popup view

The [SfPopupLayout.IsOpen](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~IsOpen.html) or [SfPopupLayout.IsVisible](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~IsVisible.html) property is used to close the [SfPopupLayout](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout.html)

{% tabs %}
{% highlight c# %}

private void ClickToClosePopup_Clicked(object sender, EventArgs e)
{
    //set false to IsOpen or IsVisible property like the folowing code to close the popup view.

    popupLayout.IsOpen = false;
    popupLayout.IsVisible = false;
}

{% endhighlight %}
{% endtabs %}

## Closing event

The [SfPopupLayout.Closing](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~Opening_EV.html) event will be fired whenever closing the PopupView in the application. It can cancel popup closing with `CancelEventArgs` that contains the following property:

* [Cancel](https://msdn.microsoft.com/query/dev14.query?appId=Dev14IDEF1&l=EN-US&k=k(System.ComponentModel.CancelEventArgs.Cancel)&rd=true): Popup opening is based on this value.

{% tabs %}
{%highlight Xaml%}
<sfPopup:SfPopupLayout x:Name="popupLayout"  Closing="PopupLayout_Closing"/>
{%endhighlight%}

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.Closing += PopupLayout_Closing;
    ....
}

private void PopupLayout_Closing(object sender, System.ComponentModel.CancelEventArgs e)
{
    e.Cancel = true;
}
{% endhighlight %}
{% endtabs %}

## Closed event

The [SfPopupLayout.Closed](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.SfPopupLayout~Closed_EV.html) event will be fired whenever dismissing the PopupView from the view.

You can execute your own set of codes once the popup is completely closed in its respective event handler.

{% tabs %}
{%highlight Xaml%}
<sfPopup:SfPopupLayout x:Name="popupLayout" Closed="PopupLayout_Closed"/>
{%endhighlight%}

{% highlight c# %}
public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.Closed += PopupLayout_Closed;
    ....
}

private void PopupLayout_Closed(object sender, EventArgs e)
{
    // Codes that needs to be executed once popup is completely closed.
}
{% endhighlight %}
{% endtabs %}

## Accept command

The [SfPopupLayout.PopupView.AcceptCommand](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~AcceptCommand.html) will be fired when clicking the Accept button in the popup footer.

To handle the Accept button, follow the procedure:

* Derive a class from `ICommand`, and implement the necessary interface.
* Return true in the `CanExecute()` override method to close the popup, and fire the `Execute()` method.
* Return false to prevent popup from closing, and `Execute()` method is not fired.

{% tabs %}

{% highlight xaml %}

<sfPopup:SfPopupLayout x:Name="popupLayout">
    <sfPopup:SfPopupLayout.PopupView>
        <sfPopup:PopupView AppearanceMode="TwoButton" />
    </sfPopup:SfPopupLayout.PopupView>
</sfPopup:SfPopupLayout>

{% endhighlight %}

{% highlight c# %}

public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.PopupView.AppearanceMode = AppearanceMode.TwoButton;
    popupLayout.PopupView.AcceptCommand = new AcceptButtonCustomCommand();
    ....
}

//Accept Button Event handler

public class AcceptButtonCustomCommand : ICommand
{
    public event EventHandler CanExecuteChanged;

    public bool CanExecute(object parameter)
    {
        return false;
    }

    public void Execute(object parameter)
    {
      // You can write your set of codes that needs to be executed
    }
}


{% endhighlight %}

{% endtabs %}

## Decline command

The [SfPopupLayout.PopupView.DeclineCommand](https://help.syncfusion.com/cr/cref_files/xamarin/Syncfusion.SfPopupLayout.XForms~Syncfusion.XForms.PopupLayout.PopupView~DeclineCommand.html) will be fired when clicking the Decline button in the popup footer. 

To handle the Decline button, follow the procedure:

* Derive a class from `ICommand`, and implement the necessary interface. 
* Return true in the `CanExecute()` override method to close the popup, and fire the `Execute()` method. 
* Return false to prevent popup from closing, and `Execute()` method is not fired.

{% tabs %}

{% highlight xaml %}

<sfPopup:SfPopupLayout x:Name="popupLayout">
    <sfPopup:SfPopupLayout.PopupView>
        <sfPopup:PopupView AppearanceMode="TwoButton" />
    </sfPopup:SfPopupLayout.PopupView>
</sfPopup:SfPopupLayout>

{% endhighlight %}

{% highlight c# %}

public MainPage()
{
    ....
    InitializeComponent();
    popupLayout.PopupView.AppearanceMode = AppearanceMode.TwoButton;
    popupLayout.PopupView.DeclineCommand = new DeclineButtonCustomCommand();
    ....
}

//Decline Button Event handler

public class DeclineButtonCustomCommand : ICommand
{
    public event EventHandler CanExecuteChanged;

    public bool CanExecute(object parameter)
    {
        return false;
    }

    public void Execute(object parameter)
    {
       // You can write your set of codes that needs to be executed
    }
}

{% endhighlight %}

{% endtabs %}
