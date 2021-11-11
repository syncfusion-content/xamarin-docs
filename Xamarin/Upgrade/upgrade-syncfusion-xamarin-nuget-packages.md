---
layout: post
title: Upgrade Syncfusion Xamarin NuGet packages| Xamarin | Syncfusion
description: This section provides the information about upgrade the Syncfusion Xamarin NuGet packages by using Package Manager UI, .NET CLI, and Package Manager Console.
platform: Xamarin
control: Essential Studio
documentation: ug
---

# Upgrading Syncfusion Xamarin NuGet packages to a latest version

Every three months, Syncfusion releases new volumes with interesting new features. For this volume, there will be weekly NuGet releases and a service pack. Syncfusion Xamarin NuGet packages are released on a weekly basis to address critical issue fixes. From any Syncfusion Xamarin NuGet version you have installed; you can update to our most recent version.


## Upgrade NuGet packages through Package Manager UI

The NuGet Package Manager UI in Visual Studio allows you to easily install, uninstall, and update NuGet packages in applications and solutions. You can find and upgrade the Syncfusion Xamarin NuGet packages to the most recent version or to specific version in the Xamarin solution or application and this process is easy with the steps below:

1. Right-click on the Xamarin application or solution in the Solution Explorer tab, and choose **Manage NuGet Packages...**

    ![Manage NuGet Packages add-in](Upgrade-images/manage-nuget.png)

    As an alternative, after opening the Xamarin application in Visual Studio, go to the **Tools** menu and after hovering **NuGet Package Manager**, select **Manage NuGet Packages for Solution...**

2. The Manage NuGet Packages window will open. Navigate to the **Updates** tab, then search for the Syncfusion Xamarin NuGet packages using a term like **"Syncfusion"** and select the appropriate Syncfusion Xamarin NuGet package for your application.

    > The [nuget.org](https://api.nuget.org/v3/index.json) package source is selected by default in the Package source drop-down. If your Visual Studio does not have nuget.org configured, follow the instructions in the [Microsoft documents](https://docs.microsoft.com/en-us/nuget/tools/package-manager-ui#package-sources) to set up the nuget.org feed URL.

3. By default, the package selected with latest version. You can select the required version and click the Update button and accept the license terms. The package will be upgraded to selected version in your Xamarin application.

    ![Xamarin Upgrade](Upgrade-images/NuGetUpgrade.png)

    You can choose the multiple NuGet packages by **selecting the checkbox** like below and click the **Update** button to update the multiple Syncfusion NuGet packages in your application.

    ![Xamarin NuGet Upgrade](Upgrade-images/MultipleNuGetUpgrade.png)

## Upgrade NuGet packages through .NET CLI

There is no distinct command for the update procedure in the .NET CLI. Unless you specify the package version, .NET CLI installs the latest version of the Syncfusion Xamarin NuGet packages when you use the dotnet add package command.

To specify a version, add the -v parameter:

```dotnet add package Syncfusion.Xamarin.SfDataGrid -v 19.3.0.43```

## Upgrade NuGet packages through Package Manager Console

The **Package Manager Console** saves NuGet packages upgrade time since you don't have to search for the package you want to update, and you can just type the command to update the appropriate Syncfusion Xamarin NuGet package. Follow the steps below to upgrade the installed Syncfusion Xamarin packages using the Package Manager Console in your Xamarin application.

1. To show the Package Manager Console, open your Xamarin application in Visual Studio and navigate to **Tools** in the Visual Studio menu and after hovering **NuGet Package Manager**, select **Package Manager Console**.

    ![Package Manager Console](Upgrade-images/console.png)

2.  The Package Manager Console will be shown at the bottom of the screen. You can update the Syncfusion Xamarin NuGet packages by enter the following NuGet update commands.

    ***Update specified Syncfusion Xamarin NuGet package***

    The below command will update the Syncfusion Xamarin NuGet package in the default Xamarin application.

    ```Update-Package <Package Name>```

    **For example:** Update-Package Syncfusion.Xamarin.SfDataGrid

    ***Update specified Syncfusion Xamarin NuGet package in specified Xamarin application***

    The below command will update the Syncfusion Xamarin NuGet package in the given Xamarin application alone.

    ```Update-Package <Package Name> -ProjectName <Project Name>```

    **For example:** Update-Package Syncfusion.Xamarin.SfDataGrid -ProjectName SyncfusionXamarinApp

3. By default, the package will be installed with latest version. You can give the required version with the -Version term like below to install the Syncfusion Xamarin NuGet packages in the appropriate version.

    ```Update-Package Syncfusion.Xamarin.SfDataGrid -Version 19.3.0.44```

    ![Package Manager Console Output](Upgrade-images/UpdateConsole.png)

4. The NuGet package manager will update the Syncfusion Xamarin NuGet package as well as the dependencies it has.