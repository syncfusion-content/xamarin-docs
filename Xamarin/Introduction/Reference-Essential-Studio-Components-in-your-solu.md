---
layout: post
title: Reference-Essential-Studio-Components-in-your-solu
description: reference essential studio components in your solution
platform: xamarin
control: Control Name undefined
documentation: ug
---

# Reference Essential Studio Components in your solution

## UI Controls

When you acquire Essential Studio components through the Xamarin Component Store interface from your IDE, then after adding the components to your Xamarin.iOS, Xamarin.Android and WindowsPhone projects through the Component Manager, you need to manually reference the PCL (Portable Class Library) assemblies in the Xamarin.Forms PCL Project in your solution. You can do this by manually adding the relevant PCL assembly references to your PCL project contained in the following path inside your solution folder:

Components/syncfusionessentialstudio-version/lib/pcl/

Alternatively, when you download Essential Studio from Syncfusion.com or through the Xamarin Store web interface, all the assembly references need to be added manually. 

After installing Essential Studio for Xamarin, all the required assemblies can be found in the installation folders, typically:

{Syncfusion Installed location}\Essential Studio\{version}\lib

Example: C:\Program Files (x86)\Syncfusion\Essential Studio\12.2.0.40\lib

Otherwise, after downloading through the Xamarin Store web interface, all the required assemblies can be found in the following folder:

{download location}\syncfusionessentialstudio-version\lib

## File Formats

XlsIO and DocIO are packaged as a portable class library, so there is no way to add reference to it from within the Xamarin Component Store IDE interface, at present. You need to obtain the required assemblies, either through the Xamarin Component Store web interface or from Syncfusion.com. Typically, you can add reference to XlsIO and DocIO only in the PCL project of your Xamarin.Forms application. The required assembly references are:

Syncfusion.Compression.Portable.dll

Syncfusion.XlsIO.Portable.dll

Syncfusion.DocIO.Portable.dll



N> If you have already referenced one of the UI components such as Chart, Gauge or TreeMap, from the Xamarin component store IDE interface then the XlsIO and DocIO assemblies have already been downloaded and available in your solution folder, you can then manually add references from that folder.

Components/syncfusionessentialstudio-version/lib/pcl/





