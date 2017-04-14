---
title: "如何：调试 CLR 激活问题 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "CLR 激活, 调试问题"
ms.assetid: 4fe17546-d56e-4344-a930-6d8e4a545914
caps.latest.revision: 5
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 5
---
# 如何：调试 CLR 激活问题
如果在使用正确版本的公共语言运行时 \(CLR\) 的运行应用程序时遇到问题，则可以查看和调试 CLR 激活日志。  这些日志非常有用。确定启动问题的根本原因，那么，当您的应用程序比预期加载不同的 CLR 版本或根本不加载 CLR。  当没有 CLR 发现应用程序时，[.NET Framework 初始化错误：管理用户体验](../../../docs/framework/deployment/initialization-errors-managing-the-user-experience.md) 讨论体验。  
  
 使用 HKEY\_LOCAL\_MACHINE 注册表项或系统环境变量，可启用 CLR 激活日志记录。  将生成日志，直到注册表项或环境变量移除。  或者，您可以使用用户或进程本地环境变量来启动记录的不同范围和持续时间。  
  
 CLR 激活日志不应与[程序集绑定日志](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md)混淆，它们完全不同。  
  
## 启用 CLR 激活日志记录  
  
#### 使用注册表  
  
1.  在“注册表编辑器”中，请导航到 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework 文件夹（位于 32 位计算机上）或 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\.NETFramework 文件夹（位于 64 位计算机上）。  
  
2.  添加名为 `CLRLoadLogDir` 的字符串值，并将其设置为要存储 CLR 激活日志的现有目录的完整路径。  
  
 保持启用激活记录，直至移除字符串值。  
  
#### 使用环境变量  
  
-   设置字符串的 `COMPLUS_CLRLoadLogDir` 环境变量，该字符串表示您要存储 CLR 激活日志所在的现有目录的完整路径。  
  
     如何设置环境变量将决定其作用域：  
  
    -   如果将其设置在系统级别上，则在移除环境变量时，将在该计算机上针对所有 .NET Framework 应用程序启用激活日志记录。  
  
    -   如果将其设置在用户级别，则仅对当前用户帐户启用激活日志记录。  记录继续，直到环境变量已移除。  
  
    -   如果正在加载 CLR 之前从进程内设置它，启用激活日志记录直到进程终止。  
  
    -   如果在命令提示下设置在您运行应用程序之前启用从命令提示中运行任何应用程序的激活日志记录。  
  
     例如，若要将激活日志存储在具有进程级别作用域的 c:\\clrloadlogs 目录下，请打开“命令提示”窗口并在运行应用程序前键入以下内容：  
  
    ```  
    set COMPLUS_CLRLoadLogDir=c:\clrloadlogs  
    ```  
  
## 示例  
 CLR 激活日志提供有关 CLR 激活的大量数据和承载 API 的 CLR 的使用。  如本文所述，大部分数据在 Microsoft 内部使用，但是，某些数据还可用于帮助开发人员。  
  
 记录以反映承载 API 的 CLR 调用的顺序。  它还包括有关在计算机上检测到已安装运行时集的有关数据。  CLR 激活日志格式本身没有记录，但是可用于协作需要解决 CLR 激活问题的开发人员。  
  
> [!NOTE]
>  在使用 CLR 的过程终止之前不能打开激活日志。  
  
> [!NOTE]
>  CLR 激活日志不本地化；它们始终以英语生成。  
  
 在以下的激活日志示例中，最有用的信息在日志后会有说明。  
  
```  
532,205950.367,CLR Loading log for C:\Tests\myapp.exe   
532,205950.367,Log started at 4:26:12 PM on 10/6/2011   
532,205950.367,-----------------------------------   
532,205950.382,FunctionCall: _CorExeMain   
532,205950.382,FunctionCall: ClrCreateInstance, Clsid: {2EBCD49A-1B47-4A61-B13A-4A03701E594B}, Iid: {E2190695-77B2-492E-8E14-C4B3A7FDD593}   
532,205950.382,MethodCall: ICLRMetaHostPolicy::GetRequestedRuntime. Version: (null), Metahost Policy Flags: 0x168, Binary: (null), Iid: {BD39D1D2-BA2F-486A-89B0-B4B0CB466891}   
532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0   
532,205950.382,Input values for ComputeVersionString follow this line   
532,205950.382,-----------------------------------   
532,205950.382,Default Application Name: C:\Tests\myapp.exe   
532,205950.382,IsLegacyBind is: 0   
532,205950.382,IsCapped is 0   
532,205950.382,SkuCheckFlags are 0   
532,205950.382,ShouldEmulateExeLaunch is 0   
532,205950.382,LegacyBindRequired is 0   
532,205950.382,-----------------------------------   
532,205950.382,Parsing config file: C:\Tests\myapp.exe   
532,205950.382,UseLegacyV2RuntimeActivationPolicy is set to 0   
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe   
532,205950.382,LegacyFunctionCall: GetFileVersion. Filename: C:\Tests\myapp.exe   
532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727   
532,205950.382,ERROR: Version v2.0.50727 is not present on the machine.   
532,205950.398,SEM_FAILCRITICALERRORS is set to 0   
532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3   
532,205950.398,FunctionCall: RealDllMain. Reason: 0   
532,205950.398,FunctionCall: OnShimDllMainCalled. Reason: 0  
  
```  
  
-   **CLR 加载日志**提供启动加载托管代码的进程的可执行文件的路径。  请注意，这可能是一个本机宿主。  
  
    ```  
    532,205950.367,CLR Loading log for C:\Tests\myapp.exe  
  
    ```  
  
-   **Installed Runtime** 是 CLR 版本集，其安装在属于激活请求的候选的计算机上。  
  
    ```  
    532,205950.382,Installed Runtime: v4.0.30319. VERSION_ARCHITECTURE: 0  
  
    ```  
  
-   **生成使用的版本** 是用于生成提供给诸如 [ICLRMetaHostPolicy::GetRequestedRuntime](../Topic/ICLRMetaHostPolicy::GetRequestedRuntime%20Method.md) 的方法二进制的 CLR 的版本。  
  
    ```  
    532,205950.382,C:\Tests\myapp.exe was built with version: v2.0.50727  
  
    ```  
  
-   **功能按需安装** 是指在 Windows 8 上启用 .NET Framework 3.5。  有关此方案的更多信息，请参见 [.NET Framework 初始化错误：管理用户体验](../../../docs/framework/deployment/initialization-errors-managing-the-user-experience.md)。  
  
    ```  
    532,205950.398,Launching feature-on-demand installation. CmdLine: C:\Windows\system32\fondue.exe /enable-feature:NetFx3  
  
    ```  
  
## 请参阅  
 [部署](../../../docs/framework/deployment/net-framework-and-applications.md)   
 [如何：配置应用程序以支持 .NET Framework 4 或 4.5](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)