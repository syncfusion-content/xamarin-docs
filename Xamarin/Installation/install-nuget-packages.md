---
layout: post
title: Install Syncfusion Xamarin NuGet packages - Syncfusion
description: Learn here about the how to install Syncfusion Xamarin NuGet packages from Package manager and NuGet manager.
platform: Xamarin
control: Extension
documentation: ug

---

# Install Syncfusion Xamarin NuGet packages

## Overview

**NuGet** is a Package management system for Visual Studio. It makes it easy to add, update and remove external libraries in our application. Syncfusion publishing all Xamarin  NuGet packages in [nuget.org](https://www.nuget.org/packages?q=Tags%3A%22xamarin%22+syncfusion). The Syncfusion Xamarin NuGet packages can be used without installing the Syncfusion Essential Studio setup. To create with the Syncfusion Xamarin components, just use the Syncfusion Xamarin NuGet packages in a Xamarin application.

> From v16.2.0.46 (2018 Volume 2 Service Pack 1) onwards, all the Syncfusion Xamarin components are available as NuGet packages at [nuget.org](https://www.nuget.org/packages?q=Tags%3A%22xamarin%22+syncfusion).

## Installation using Package Manager UI

The NuGet Package Manager UI allows you to search, install, uninstall, and update Syncfusion Xamarin NuGet packages in your applications and solutions. You can find and install the Syncfusion Xamarin NuGet packages in your Visual Studio Xamarin app and this process is easy with the steps below:

1.  Right-click on the Xamarin app or solution in the Solution Explorer, and choose Manage NuGet Packages...

    ![Manage NuGet Packages add-in for Xamarin Installation](platform_images/xamarin-nuget-packages-installation-add-in.png)

    As an alternative, after opening the Xamarin application in Visual Studio, go to the **Tools** menu and after hovering **NuGet Package Manager**, select **Manage NuGet Packages for Solution...**

2. The Manage NuGet Packages window will open. Navigate to the Browse tab, then search for the Syncfusion Xamarin NuGet packages using a term like "**Syncfusion.Xamarin**" and select the appropriate Syncfusion Xamarin NuGet package for your development.

    ![Xamarin NuGet Packages Search](platform_images/xamarin-nuget-packages-installation-search.png)

    > The [nuget.org](https://api.nuget.org/v3/index.json) package source is selected by default in the Package source drop-down. If your Visual Studio does not have nuget.org configured, follow the instructions in the [Microsoft documents](https://learn.microsoft.com/en-us/nuget/consume-packages/install-use-packages-visual-studio#package-sources) to set up the nuget.org feed URL.
 
3. When you select a package, the right-side panel will provide more information about it..

4.  By default, the package selected with latest version. You can choose the required version and click the Install button and accept the license terms. The package will be added to your Xamarin app.

    ![Xamarin NuGet Packages Install](platform_images/xamarin-nuget-packages-installation-app.png)

5.  At this point, your application has all the required Syncfusion assemblies, and you will be ready to start building high-performance, responsive app with  [Syncfusion Xamarin components](https://www.syncfusion.com/xamarin-ui-controls). Also, you can refer to the [Syncfusion Xamarin help document](https://help.syncfusion.com/xamarin/introduction/overview) for development.

## Installation using Dotnet (.NET) CLI

The [dotnet Command Line Interface (CLI)](https://learn.microsoft.com/en-us/nuget/consume-packages/install-use-packages-dotnet-cli), allows you to add, restore, pack, publish, and manage packages without making any changes to your application files. [Dotnet add package](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-add-package?tabs=netcore2x) adds a package reference to the application file, then runs [dotnet restore](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-restore?tabs=netcore2x) to install the package.

Follow the below instructions to use the dotnet CLI command to install the Syncfusion Xamarin NuGet packages.

1. Open a command prompt and navigate to the directory where your Syncfusion Xamarin project file is located.
2. To install a NuGet package, run the following command.

    ```dotnet add package <Package name>```

    **For Example:**
    dotnet add package Syncfusion.Xamarin.SfDataGrid

    > If you don’t provide a version flag, this command will be upgrading to the latest version by default. To specify a version, add the -v parameter: dotnet add package Syncfusion.Xamarin.SfDataGrid -v 19.3.0.44.

3.  Examine the Syncfusion Xamarin project file after the command has completed to ensure that the Syncfusion Xamarin package was installed. To see the added reference, open the .csproj file.

    ![Xamarin NuGet Package Installation Entry ](platform_images/xamarin-nuget-packages-installation-entry.png)

4. Then run  [dotnet restore](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-restore?tabs=netcore2x) command to restores all the packages listed in the application file.

    > Restoring is done automatically with **dotnet build** and **dotnet run** in .NET Core 2.0 and later.

5. At this point, your application has all the required Syncfusion assemblies, and you will be ready to start building high-performance, responsive app with  [Syncfusion Xamarin components](https://www.syncfusion.com/xamarin-ui-controls). Also, you can refer to the [Syncfusion Xamarin help document](https://help.syncfusion.com/xamarin/introduction/overview) for development.

## Installation using Package Manager Console

The **Package Manager Console** saves NuGet packages installation time since you don't have to search for the Syncfusion Xamarin NuGet package which you want to install, and you can just type the installation command to install the appropriate Syncfusion Xamarin NuGet package. Follow the instructions below to use the Package Manager Console to reference the Syncfusion Xamarin component as NuGet packages in your Xamarin application

1. To launch the Package Manager Console, open your Xamarin application in Visual Studio and navigate to **Tools -> NuGet Package Manager -> Package Manager Console**.

    ![Package Manager Console in Xamarin NuGet Packages ](platform_images/xamarin-nuget-packages-installation-console.png)

2. The **Package Manager Console** will be shown at the bottom of the screen. You can install the Syncfusion Xamarin NuGet packages by enter the following NuGet installation commands.

    ***Install specified Syncfusion Xamarin NuGet package***

    The below command will install the Syncfusion Xamarin NuGet package in the Xamarin application.

    ```Install-Package <Package Name>```

    **For example:** Install-Package Syncfusion.Xamarin.SfDataGrid

    > You can find the list of Syncfusion Xamarin NuGet packages which are published in nuget.org from [here](https://www.nuget.org/packages?q=Tags%3A%22xamarin%22+syncfusion)

    ***Install specified Syncfusion Xamarin NuGet package in specified Xamarin application***

    The below command will install the Syncfusion Xamarin NuGet package in the given Xamarin application.

    ```Install-Package <Package Name> -ProjectName <Project Name>```

    **For example:** Install-Package Syncfusion.Xamarin.SfDataGrid -ProjectName SyncfusionXamarinApp

3. By default, the package will be installed with latest version. You can give the required version with the -Version term like below to install the Syncfusion Xamarin NuGet packages in the appropriate version.

    ```Install-Package Syncfusion.Xamarin.SfDataGrid -Version 19.3.0.44```

    ![Package Manager Console Output in Xamarin NuGet Packages installation](platform_images/xamarin-nuget-packages-console-installation-output.png)

4. The NuGet package manager console will install the Syncfusion Xamarin NuGet package as well as the dependencies it has. When the installation is complete, the console will show that your Syncfusion Xamarin package has been successfully added to the application.

5. At this point, your application has all the required Syncfusion assemblies, and you will be ready to start building high-performance, responsive app with  [Syncfusion Xamarin components](https://www.syncfusion.com/xamarin-ui-controls). Also, you can refer to the [Syncfusion Xamarin help document](https://help.syncfusion.com/xamarin/introduction/overview) for development.