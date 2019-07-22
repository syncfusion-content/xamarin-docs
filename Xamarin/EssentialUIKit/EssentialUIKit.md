---
layout: post
title: Syncfusion Essential UI Kit
platform: xamarin
control: Xamarin UI Kit
documentation: ug
---

# Syncfusion XAML Templates for Xamarin.Forms

The Syncfusion Essential UI Kit is a collection of easy-to-use, extendable, and adaptable XAML templates that allows you to quickly create a Xamarin.Forms application by providing generic pre-defined screens. Now, the UI Kit has screens for the following categories:

* Login
* ECommerce
* Chat
* Feedback
* Contact us
* About Us
* Article
* Navigation
* Error and Empty  

The screens are developed with MVVM pattern that separates the UI and business logic results in a clean, professional, and scalable representation of a user interface in your Xamarin.Forms application.

## Adding predefined screens to your application

The screens can be added in your application by the following two ways:

1. Using **XAML UI Kit for Xamarin.Forms** Visual Studio extension.

2. Copying the files from our open source [GitHub repository](https://github.com/syncfusion/essential-ui-kit-for-xamarin.forms).

## Essential UI Kit for Xamarin.Forms extension

This is the easiest way to add the pre-defined screens to your application. The following steps explain how to add screens to an application with our extension: 

1. Open Visual Studio.

2. Go to Extension, and then click Manage Extensions as shown in the following screenshot.

![Visual Studio Extensions](Essential-UI-Kit-images/VS_Extensions.png)

3. Search for **XAML UI Kit for Xamarin.Forms**, and then install it.

![Visual Studio Extensions & Updates](Essential-UI-Kit-images/Extension_Update.png)

4. Restart the Visual Studio and allow it to complete the installation. 

5. Now, open an existing Xamarin.Forms application or create a new application as per your requirements.
 
6. Right-click the Xamarin.Forms [NETStandard] project, and you can see the **XAML UI Kit for Xamarin.Forms** option.

7. Select the category and pages you need to add in your application. In the following screenshot, the **Login Page with Gradient** screen has been selected from the **Login** category. 

![Visual Studio UIkit Category](Essential-UI-Kit-images/Essential_UIKit_Category.png)

8. Clicking the 'Add' button will include the selected template to your project. The necessary class files, resources, and NuGet package references will automatically be added to your project as shown in the following screenshot.

![Visual Studio Ui Kit nuget and files](Essential-UI-Kit-images/Kit_Nuget_Files.jpg)

## How to render the added page

In a Xamarin.Forms demo application, you must make the added template as the start-up page in the App.xaml.cs file. 
Example: If you added the Login Page, then you must invoke the page as demonstrated in the following code.

{% highlight c# %}
MainPage=new SampleFormsApplication.Views.Login.LoginPage();
{% endhighlight %} 

In real-world applications, you can set the navigations or wire up the newly added pages as your requirement. 

N> Now, **XAML UI Kit for Xamarin.Forms** Visual Studio extension is supported in the Windows operating system only.