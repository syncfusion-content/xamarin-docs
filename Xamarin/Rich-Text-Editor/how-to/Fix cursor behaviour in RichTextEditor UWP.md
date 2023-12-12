---
layout: post
title: Fix in Xamarin Rich Text Editor control | Syncfusion
description: Learn here all about cursor behaviour in Syncfusion Xamarin Rich Text Editor (SfRichTextEditor) control and more.
platform: xamarin
control: Rich Text Editor
documentation: ug
---

# Fix cursor behaviour in SfRichTextEditor UWP Platform

In some cases the cursor behaviour does not working properly on the RichTextEditor UWP platform. We have implemented the RichTextEditor control using the WebView for rendering the HTML content. Upon the further analysis we have found that the issue from the WebView control. 

To overcome the issue by using the WebView2 Control on the RichTextEditor UWP platform. We provided the support for change WebView control to WebView2 control at the sample level. At default the control load with WebView.

Follow the steps below to create the sample to pass the WebView2 instance from the sample:

1. Install **MicroSoft.UI.Xaml** NuGet Package on UWP platform.

2. Need to create WebView2Container Class and it’s inherited from the common interface **IWebViewContainer**.

3. To create the two private field of the class. **Webview2** is an instance of the WebView2 control, and **renderer** is an instance of the SfRichTextEditorRenderer Class.

4. Create the Constructor and get the SfRichTextEditor instance as a parameter and it’s used to pass the WebView2 values to the source. Raised the necessary WebView2 events.And the events are
	
	* webView2.CoreWebView2Initialized : Under the event to rasied the **webView2.CoreWebView2.WebMessageReceived** event and set the **webView2.CoreWebView2.Settings.IsScriptEnabled** property as true. After the WebView2 control intialized the script value was received and enabled.
	* webView2.NavigationCompleted 

5. Need to create common interface Properties and method to use to load the WebView2 control.

	* object WebView { get; } : To get the WebView2 instance to replace WebView with WebView2 control.
	* Uri Source { get; set; } : get and Set the WebView2 Script file.
	* void ExcecuteScript(string script); : The method used to pass the input values to script file.

6. Call the below methods on corresponding events.
 
	* WebView2Ext_NavigationCompleted event : To call renderer class NotifyNavigationCompleted method.Within the method to pass the input values to the script.
	* CoreWebView2_WebMessageReceived event : To call renderer class NotifyWebMessageReceived(scriptContent) method.This event is raised to perform any actions on the RichTextEditor, passing values to the script file.

7. Need to get the SfRichTextEditorRenderer instance from the UWP sample MainPage.Xaml.cs. And since a direct reference to it is not available, this is achieved by using FindSfRichTextEditorRenderer() method.

8. After getting the SfRichTextEditorRenderer instance to switch the WebView with WebView2 using sfRichTextEditorRenderer.ReplaceWebView(webview2); method.

### WebView2 Limitation :

The WebView2 Unfocused event does not trigger properly, it’s an issue from the WebView2. So, we have overcome the issue of sending the MessagingCenter once the control on the WebView2Container class is unfocused. And subscribes to MessagingCenter on Forms MainPage.Xaml.cs class

To do any unfocused related activities on the subscribes MessagingCenter. Need to UnSubscribe the MessaginCenter on OnDisappearing override method.

N>The WebView2 control does not support the **Any CPU** architecture, but our source project as implemented by Any CPU architecture.So we could not able to implement the WebView2 directly on source. It applies to UWP only. Since iOS and Android working properly.
