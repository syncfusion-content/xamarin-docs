---
layout: post
title: Create Project | xamarin | Syncfusion®
description: Syncfusion® Project Templates Extension creates the Syncfusion® Xamarin Application by adding the required Syncfusion® NuGet packages.
platform: xamarin
control: Syncfusion<sup>®</sup> Extensions
documentation: ug
---

# Creating Syncfusion<sup>®</sup> Xamarin Application

Syncfusion<sup>®</sup> provides Visual Studio Project Templates for the Syncfusion<sup>®</sup> Xamarin platform, allowing you to quickly develop a Syncfusion<sup>®</sup> Xamarin application by just adding the needed Syncfusion<sup>®</sup> NuGet packages for the control you want to use. 

I> The Syncfusion<sup>®</sup> Xamarin Project Templates are available from v16.2.0.41.

To create the **Syncfusion<sup>®</sup> Xamarin Application** in Visual Studio, follow these steps

> Check whether the **Xamarin Extensions - Syncfusion<sup>®</sup>** are installed or not in Visual Studio Extension Manager by going to **Extensions -> Manage Extensions -> Installed** for Visual Studio 2019 or later, and for Visual Studio 2017 or lower by going to **Tools -> Extensions and Updates -> Installed**. If this extension not installed, please install the extension by follow the steps from the [download and installation](download-and-installation) help topic.

1.	Follow one of the instructions below to create a Syncfusion<sup>®</sup> Xamarin project

	**Option 1:**  
	Click **Extensions->Syncfusion<sup>®</sup>** Menu and choose **Essential Studio<sup>®</sup> for Xamarin > Create New Syncfusion<sup>®</sup> Project…** in **Visual Studio**.

	![Choose Syncfusion<sup>®</sup> Xamarin application from Visual Studio new project dialog via Syncfusion<sup>®</sup> menu](Syncfusion_Project_Templates_images/xamarin-visual-studio-intergration-new-project.png)

	N> In Visual Studio 2017 or lower, you can see the Syncfusion<sup>®</sup> menu directly in the Visual Studio menu.

	![Choose Syncfusion<sup>®</sup> Xamarin application from Visual Studio new project dialog via Syncfusion<sup>®</sup> menu](Syncfusion_Project_Templates_images/xamarin-project-creation-syncfusion-menu.png)

	**Option 2:**  
	Choose **File -> New -> Project**. Opens a new dialog to create a new project. By filtering the project type with Syncfusion<sup>®</sup> or using the Syncfusion<sup>®</sup> keyword in the search option, you can get the templates offered by Syncfusion<sup>®</sup> for Xamarin.

	![Choose Syncfusion<sup>®</sup> Xamarin application from Visual Studio new project dialog](Syncfusion_Project_Templates_images/xamarin-project-creation-dialog.png)

	In Visual Studio 2017 or lower, choose **File > New > Project** and navigate to **Syncfusion > Cross-Platform > Syncfusion<sup>®</sup> Xamarin Project Template** in **Visual Studio**.

	![Choose Syncfusion<sup>®</sup> Xamarin application from Visual Studio new project dialog](Syncfusion_Project_Templates_images/Syncfusion-Project-Templates-img1.jpeg)

2.	Click **OK** once you've given the **project  name**, selected a destination location, and set the project's Framework. The Project Configuration Wizard is now displayed.
   
3.	Choose the Project, Android, iOS, and UWP by on/off in the following Project Configuration window to configure the Syncfusion<sup>®</sup> Xamarin Application.

    ![Syncfusion<sup>®</sup> Xamarin project configuaration wizard](Syncfusion_Project_Templates_images/xamarin-project-creation-configuration-wizard.jpeg)

	**Project Configuration:**

	**Assemblies From:** Choose NuGet or Installed Location to load the Syncfusion<sup>®</sup> Xamarin reference into Xamarin Application.

	N> Installed location option will be shown only when the Syncfusion<sup>®</sup> Xamarin setup has been installed.

	**Android**

	1. **Minimum Android Version:** Choose the earliest Android version for which you want to provide support for your app. 
	2. **Target Android Version:** Choose the Android version on which your app will run. 

	**iOS**

	1. **Target Device:**  Choose the Xamarin.iOS device of Xamarin.iOS project either Unified, iPhone/iPod, or iPad.
	2. **Target Version:** Select the Xamarin.iOS Project version.

	**Choose controls:** To create the Syncfusion<sup>®</sup> Xamarin application, choose at least one Syncfusion<sup>®</sup> control. 

	N> If you want to add other Syncfusion<sup>®</sup> Xamarin controls in the created Syncfusion<sup>®</sup> Xamarin application, you can use our [Syncfusion Xamarin toolbox](https://help.syncfusion.com/xamarin/visual-studio-integration/toolbox-control)

	![Choose Syncfusion Xamarin control](Syncfusion_Project_Templates_images/xamarin-project-creation-control-selection.png)

4.	The Syncfusion<sup>®</sup> Xamarin Application has been created when you click **Create**.

	N> Choose any one of the project type and controls from Project Configuration Wizard.

	![Selected Syncfusion<sup>®</sup> Xamarin control assemblies added to the UWP project](Syncfusion_Project_Templates_images/xamarin-project-creation-added-assemblies.PNG)

5.	Based on the control selected, required Syncfusion<sup>®</sup> NuGet/Assemblies and configuration have been added to the project.

	**Net Standard /PCL**

	![Selected Syncfusion<sup>®</sup> Xamarin control NuGet package installed in project](Syncfusion_Project_Templates_images/xamarin-project-creation-installed-nuget-packages.jpeg)

	![Selected Syncfusion<sup>®</sup> Xamarin control assemblies added to the project](Syncfusion_Project_Templates_images/xamarin-project-creation-added-controls.jpeg)

	**Android**

	![Selected Syncfusion<sup>®</sup> Xamarin control Android NuGet package](Syncfusion_Project_Templates_images/xamarin-project-creation-android-packages.jpeg)

	![Selected Syncfusion<sup>®</sup> Xamarin control assemblies added to the Android project](Syncfusion_Project_Templates_images/xamarin-project-creation-android.jpeg)

	**iOS**

	![Selected Syncfusion<sup>®</sup> Xamarin control iOS NuGet package](Syncfusion_Project_Templates_images/xamarin-project-creation-ios-packages.jpeg)

	![Selected Syncfusion<sup>®</sup> Xamarin control assemblies added to the iOS project](Syncfusion_Project_Templates_images/xamarin-project-creation-ios.jpeg)

	**UWP**

	![Selected Syncfusion<sup>®</sup> Xamarin control UWP NuGet package](Syncfusion_Project_Templates_images/xamarin-project-creation-ios-packages.jpeg)

	![Selected Syncfusion<sup>®</sup> Xamarin control assemblies added to the UWP project](Syncfusion_Project_Templates_images/xamarin-project-creation-controls-uwp.jpeg)

6.	Then, Syncfusion<sup>®</sup> licensing registration required message box will be shown if you installed the trial setup or NuGet packages since Syncfusion<sup>®</sup> introduced the licensing system from 2018 Volume 2 (v16.2.0.41) Essential Studio<sup>®</sup> release. Navigate to the [help topic](https://help.syncfusion.com/common/essential-studio/licensing/overview#how-to-generate-syncfusion-license-key), which is shown in the licensing message box to generate and register the Syncfusion<sup>®</sup> license key to your project. Refer to this [blog](https://www.syncfusion.com/blogs/post/whats-new-in-2018-volume-2.aspx) post for understanding the licensing changes introduced in Essential Studio<sup>®</sup>.

	![Syncfusion<sup>®</sup> license registration required information dialog in Syncfusion<sup>®</sup> Xamarin Project](Syncfusion_Project_Templates_images/xamarin-project-creation-license-registration.jpeg)


