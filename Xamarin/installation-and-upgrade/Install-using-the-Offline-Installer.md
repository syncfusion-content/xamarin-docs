---
layout: post
title: Syncfusion Essential Studio Offline Installer
description: this section provides information regarding the Syncfusion Xamarin Offline installer and steps for installing it
platform: Xamarin
control: Installation and Deployment
documentation: ug

---

# Installation using Offline Installer

## Installing with UI   

The following procedure illustrates how to install Essential Studio Xamarin platform.

1. Close all the running Visual Studio instances.

2. Double-click the Syncfusion Xamarin platform installer file. The Installer Wizard opens and extracts the package automatically.

   ![Installer extraction wizard](Platform_images/Step-by-Step-Installation_img1.png)

   N> The Installer wizard extracts the syncfusionessentialxamarin_(version).exe dialog, displaying the unzip operation of the package.

3. You have two options to unlock the Syncfusion installer:

   
* *Login To Install*
   
* *Use Unlock Key*
   
   
   
   **Login To Install**
   
   You should enter your Syncfusion Direct-Trac login credentials. If you don't have Syncfusion Direct-Trac login credentials, then you can click on Sign Up to a create new account. Else if you forgot your password, click on Reset Password to create new password. Here Email address and Password is validated and the Platform Selection window opens.

   ![Login credentials](Platform_images/Step-by-Step-Installation_img2.png)   


   **Use Unlock Key**
   
   You should use the Syncfusion License/Trial key. Trial key is valid for 30 days and the installer won't accept the expired trial key. Licensed customer can generate key from [here](https://www.syncfusion.com/kb/2326).

   ![Product key](Platform_images/Step-by-Step-Installation_img3.png)   


4. After reading the License Terms and Conditions, check the **I agree to the License Terms and Conditions** check box.


5. Click Next. Select the Installation, Samples Folder and Advanced Options screen opens. To install in the displayed default location, click Install


    ![Advanced options](Platform_images/Step-by-Step-Installation_img4.png)


    N> From the 2018 Volume 2 release, Syncfusion has changed the install and samples location 
	   **Default Install location:** {ProgramFilesFolder}\Syncfusion\{Platform}\{version}
	   **Default Samples location:** C:\Users\Public\Documents\Syncfusion\{platform}\{version}
	   However, you can change the locations by clicking browse button.

   * Select the **Install Syncfusion Samples** check box to install Syncfusion samples, or leave the check box clear, when you do not want to install Syncfusion samples.
   * Select the **Configure Syncfusion controls in Visual Studio Toolbox** check box to configure the Syncfusion controls in the Visual Studio toolbox, or clear this check box when you do not want to configure the Syncfusion controls in the Visual Studio toolbox during installation. Note that you must also select the Register Syncfusion assemblies in GAC check box when you select this check box.
   * Select the **Install Syncfusion Extensions** checkbox to configure the Syncfusion Extensions in Visual Studio or clear this check box when you do not want to configure the Syncfusion Extensions in Visual Studio.


6.  Click Install.


    ![Installing wizard](Platform_images/Step-by-Step-Installation_img5.png)

7. The Completed screen is displayed once the Xamarin platform is installed.

    ![Installation completed](Platform_images/Step-by-Step-Installation_img6.png)


8. Select the **Run Syncfusion Control Panel** check box to launch the Syncfusion Control Panel after installing.


9. Click Finish. Syncfusion Xamarin platform is installed in your system and the Syncfusion Essential Studio [Syncfusion Control Panel](http://help.syncfusion.com/common/essential-studio/utilities#dashboard ) is launched automatically.

## Installing in silent mode

The Syncfusion Essential Studio Platform Installer supports installing/uninstalling through Command Line. The following sections illustrate this ability. 

### Command Line Installation

Follow the steps below to install through Command Line in Silent mode.

1. Double-click the Syncfusion Essential Studio platform installer file. The installer Wizard opens and extracts the package automatically. 
2. The syncfusionessentialxamarin_(version).exe file is extracted into the Temp folder.
3. Run %temp%. The Temp folder will open. The syncfusionessentialxamarin_(version).exe file is available in one of the folders.
4. Copy the extracted syncfusionessentialxamarin_(version).exe file in local drive.
5. Cancel the Wizard.
6. Open the Command Prompt in administrator mode and pass the following arguments.

   
   **Arguments:** “Installer file path\SyncfusionEssentialStudio(platform)_(version).exe” /Install silent /PIDKEY:“(product unlock key)” [/log “{Log file path}”] [/InstallPath:{Location to install}] [/InstallSamples:{true/false}] [/InstallAssemblies:{true/false}] [/UninstallExistAssemblies:{true/false}] [/InstallToolbox:{true/false}]


   N> [..] – Arguments inside the square brackets are optional.

   **Example:** “D:\Temp\syncfusionessentialxamarin_x.x.x.x.exe” /Install silent /PIDKEY:“product unlock key” /log “C:\Temp\EssentialStudio_Platform.log” /InstallPath:C:\Syncfusion\x.x.x.x /InstallSamples:true /InstallAssemblies:true /UninstallExistAssemblies:true /InstallToolbox:true

	
7. Essential Studio Xamarin is installed.

   N> x.x.x.x needs to be replaced with the Essential Studio version and the Product Unlock Key needs to be replaced with the Unlock Key for that version.
   

### Command Line Uninstallation

Syncfusion Essential Studio supports uninstalling through Command Line in Silent mode. The following steps illustrate this. 

1. When you do not have the extracted installer (syncfusionessentialxamarin_(version).exe) then follow the steps from 2 to 7.
2. Double-click the Syncfusion Essential Studio platform installer file. The Installer Wizard opens and extracts the package automatically.
3. The syncfusionessentialxamarin_(version).exe file is extracted into the Temp folder.
4. Run %temp%. The Temp folder will open. The syncfusionessentialxamarin_(version).exe file is available in one of the folders.
5. Copy the syncfusionessentialxamarin_(version).exe file in local drive. 
6. Cancel the Wizard.
7. Open the Command Prompt in administrator mode and pass the following arguments.
   
   **Arguments:** “Copied installer file path\syncfusionessentialxamarin_(version).exe” /uninstall silent 

   **Example:** “D:\Temp\syncfusionessentialxamarin_x.x.x.x.exe" /uninstall silent


8. Essential Studio Xamarin is uninstalled.

   N> x.x.x.x needs to be replaced with the Essential Studio version installed in your machine.
   
   
## Explore the libraries package

You can find the Syncfusion libraries, samples and NuGet from the installed location in Windows.

{Essential Studio installed location}\Syncfusion\Essential Studio\{version}\Xamarin

* **"lib"** folder - e.g., C:\Program Files (x86)\Syncfusion\Essential Studio\16.2.0.41\Xamarin\lib

   It contains all the required libraries for Xamarin.iOS, Xamarin.Android, and Xamarin.Forms projects.
   
* **"nuget"** folder - e.g., C:\Users\Public\Documents\Syncfusion\16.2.0.41\Xamarin\nuget

   It contains the above libraries as NuGet packages. The same NuGet packages also can be configured from online [nuget.org](https://api.nuget.org/v3/index.json).
   
* **"sample"** folder - e.g., C:\Users\Public\Documents\Syncfusion\16.2.0.41\Xamarin\sample

   It contains the sample applications for our controls in Xamarin.iOS, Xamarin.Android, and Xamarin.Forms platforms in iOS, Android, and Forms folders, respectively.

The "Forms" directory includes,

* Individual control sample folders: It contains the samples for individual controls such as SfChart, SfDataGrid, etc. Since they represent the individual controls, these samples are light-weighted. You can check the samples for your required controls alone faster with minimum deployment time.

* “nuget” folder: It contains the compiled assemblies of the above samples as NuGet package. It is referred in the common sample browser as explained in the next step.

* “SampleBrowser” folder: It contains common sample browser, which refers the individual control's samples as NuGet package. Run this to see the demo samples of all the controls in single application.

* It also contains showcase samples such as Patient Monitor, Server Monitor, and Invoice.

### Add reference to the project

You can then add the assembly references to the respective projects such as PCL, XForms.Droid, XForms.iOS and XForms.UWP. You can find the dependencies for each control from this [link](https://help.syncfusion.com/xamarin/introduction/control-dependencies).

I> After adding the reference, currently, an additional step is required for iOS and UWP projects. For example, if we are using SfKanban, we need to call the Init method of SfKanbanRenderer as shown in this [KB article](https://www.syncfusion.com/kb/7171).

I> For UWP alone, one more additional step is required if the project is built in release mode with .NET Native tool chain enabled. For example, if we are using SfKanban, you can refer the [KB article](https://www.syncfusion.com/kb/7170) for more details.
