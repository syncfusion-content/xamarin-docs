---
layout: post
title: Build error occurs during Syncfusion core project compilation
description: Error processing method occurs during core projects compilation
platform: xamarin
control: Troubleshooting
documentation: ug
---

# Error processing method: System.Void Syncfusion.XForms.Android.TextInputLayout.InputLayoutBorder::OnDraw(Android.Graphics.Canvas) occurs during build the project.

When setting [`TargetFrameworkVersion`](https://docs.microsoft.com/en-us/xamarin/android/app-fundamentals/android-api-levels?tabs=windows#framework) of the application to any lower version(below 8.1), the below error will occurs,

<table>
<tr>
<td>

<b>Error : The "LinkAssemblies" task failed unexpectedly.</b>
<br/>

<b>Error processing method: 'System.Void Syncfusion.XForms.Android.TextInputLayout.InputLayoutBorder::OnDraw(Android.Graphics.Canvas)' in assembly: 'Syncfusion.Core.XForms.Android.dll' ---&gt; Mono.Cecil.ResolutionException: Failed to resolve System.Boolean Android.Graphics.Canvas::ClipOutRect(Android.Graphics.RectF)
   at Mono.Linker.Steps.MarkStep.HandleUnresolvedMethod(MethodReference reference)
   at Mono.Linker.Steps.MarkStep.MarkMethod(MethodReference reference)
   at Mono.Linker.Steps.MarkStep.MarkInstruction(Instruction instruction)
   at Mono.Linker.Steps.MarkStep.MarkMethodBody(MethodBody body)
   at Mono.Linker.Steps.MarkStep.ProcessMethod(MethodDefinition method)
   at Mono.Linker.Steps.MarkStep.ProcessQueue()
   --- End of inner exception stack trace ---
   at Mono.Linker.Steps.MarkStep.ProcessQueue()
   at Mono.Linker.Steps.MarkStep.ProcessPrimaryQueue()
   at Mono.Linker.Steps.MarkStep.Process()
   at MonoDroid.Tuner.MonoDroidMarkStep.Process(LinkContext context)
   at Mono.Linker.Pipeline.Process(LinkContext context)
   at MonoDroid.Tuner.Linker.Process(LinkerOptions options, ILogger logger, LinkContext& context)
   at Xamarin.Android.Tasks.LinkAssemblies.Execute(DirectoryAssemblyResolver res)
   at Xamarin.Android.Tasks.LinkAssemblies.Execute()
   at Microsoft.Build.BackEnd.TaskExecutionHost.Microsoft.Build.BackEnd.ITaskExecutionHost.Execute()
   at Microsoft.Build.BackEnd.TaskBuilder.&lt;ExecuteInstantiatedTask&gt;d__26.MoveNext()	Entersoft.Universal.Android			
</b>
</td>
</tr>
</table>

You can resolve this issue by 

* Setting [`TargetFrameworkVersion`](https://docs.microsoft.com/en-us/xamarin/android/app-fundamentals/android-api-levels?tabs=windows#framework) of the application to latest version (Android 8.1 or greater), but you can set the [`TargetAndroidVersion`](https://docs.microsoft.com/en-us/xamarin/android/app-fundamentals/android-api-levels?tabs=windows#target) to any required version. To know more these settings, refer this [link.](https://docs.microsoft.com/en-us/xamarin/android/app-fundamentals/android-api-levels?tabs=windows) 
  


