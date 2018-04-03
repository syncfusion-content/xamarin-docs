---
layout : post
title : Localization of ImageEditor
description : How to Localize the contents of SfImageEditor control.
platform : xamarin.forms
control : ImageEditor
documentation : ug
---

# Localization

The image editor control provides support for localization.You can localize ImageEditor contents by adding equivalent localized string.

## Change default control language

Based on the resource strings in the project the contents are localized accordingly.

By default,ImageEditor control is available in English.

### Change default texts in the control

You can localize the custom strings used in the ImageEditor control. For that you need to configure it for each platform separately.

Localizing the text in Android renderer.

Localizing the text in iOS renderer.

Localizing the text in UWP renderer.

### Localizing the text in Android renderer

You can localize the text available in the control by adding equivalent localized string in the resource file.

Create String.xml in resource file in Android

Location- ProjectName.Android/Resources/values/Strings.Xml

![SfImageEditor](ImageEditor_images/androidstrings.png)

In below screenshot we have localized the text  to French language.

![SfImageEditor](ImageEditor_images/androidresources.png)

### Localizing the text in iOS renderer

You can localize custom text available in the control by adding equivalent localized string in the resource file.

Create Localizable.strings in resource file in iOS.

Location- ProjectName.iOS/Resources/Localizable.strings

![SfImageEditor](ImageEditor_images/iosresources.png)

In below screenshot we have localized the text to French language.

![SfImageEditor](ImageEditor_images/ioslocalizable.png)

### Localizing the text in UWP renderer

You can localize custom text available in the control by adding equivalent localized string in the resource file.

Create Syncfusion.SfImageEditor.UWP.Resources file in UWP.

Location- ProjectName.UWP/Resources/Syncfusion.SfImageEditor.UWP.Resources 

![SfImageEditor](ImageEditor_images/uwpresw.png)

In below screenshot we have localized the text to French language.

![SfImageEditor](ImageEditor_images/uwpresources.png)

Please find the screenshot in which we have localized the text in ImageEditor to French language.

![SfImageEditor](ImageEditor_images/imageframe.png)


 




