---
layout: post
title: Auto-Size Xamarin.Forms Popup | SfPopupLayout |Xamarin | Syncfusion
description: Auto-Size / AutoFit popup's content in Xamarin.Forms PopupLayout.
platform: Xamarin
control: SfPopupLayout
documentation: ug
--- 

# Auto-Size Popup

The `SfPopupLayout` can auto size the popup view based on the contents loaded inside its `SfPopupLayout.PopupView.ContentTemplate` property using the `SfPopupLayout.PopupView.AutoSizeMode` property. The default value is `AutoSizeMode.None`. You can choose to auto size the popup in height, width or in both height and width of its contents. By default the `HeightRequest` and `WidthRequest` set to the `SfPopupLayout.PopupView` or to the views loaded inside the template is given higher priority than the `AutoSizeMode`.

Refer the below code snippet to auto size the popup in height based on the content loaded inside the `SfPopupLayout.PopupView.ContentTemplate` property.

{% tabs %}

{% highlight xaml %}

    <sfPopup:SfPopupLayout x:Name="popUpLayout">
        <sfPopup:SfPopupLayout.PopupView>
            <sfPopup:PopupView AutoSizeMode="Height">
                <sfPopup:PopupView.ContentTemplate>
                    <DataTemplate>
                        <StackLayout Padding="5,5,5,0">
                            <Label Text="Window loads under the parent window surrounded by an overlay which prevents clicking anywhere else on the screen apart from the control of the modal. Modal opens in the same window. It also does not require any user action to open, and give callbacks when closing or opening the modal."
                            BackgroundColor="White"
                            LineBreakMode="WordWrap"
                           />
                        </StackLayout>
                    </DataTemplate>
                </sfPopup:PopupView.ContentTemplate>
            </sfPopup:PopupView>
        </sfPopup:SfPopupLayout.PopupView>
    </sfPopup:SfPopupLayout>

{% endhighlight %}

{% highlight c# %}

popUpLayout.PopupView.AutoSizeMode = AutoSizeMode.Height;

{% endhighlight %}

{% endtabs %}

Executing the above codes renders the following output in an Android device.

![Auto height in Xamarin.Forms Popup](PopupLayout_images/PopupView_AutoSize_Height.jpg)

Sample Link: You can download the above sample code by clicking [here](http://www.syncfusion.com/downloads/support/directtrac/general/ze/AutoSize_SfPopuplayout1703576210).