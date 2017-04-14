---
title: "在完全信任环境中运行 Intranet 应用程序 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "完全信任, 运行 Intranet 应用程序"
  - "Intranet 应用程序, 在完全信任环境中运行"
  - "在完全信任环境中运行 Intranet 应用程序"
ms.assetid: ee13c0a8-ab02-49f7-b8fb-9eab16c6c4f0
caps.latest.revision: 20
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# 在完全信任环境中运行 Intranet 应用程序
从 .NET Framework 3.5 Service Pack 1 \(SP1\) 开始，应用程序及其库程序集可以从网络共享作为完全信任程序集运行。  <xref:System.Security.SecurityZone> 区域证据会自动添加到从 Intranet 上的共享中加载的程序集。  此证据给予这些程序集的授予集（通常是完全信任）与位于计算机上的程序集所获得的授予集相同。  此功能不适用于 ClickOnce 应用程序或设计为在主机上运行的应用程序。  
  
## 库程序集的规则  
 下面的规则适用于由网络共享中的可执行文件加载的程序集：  
  
-   库程序集必须与可执行文件程序集位于同一文件夹中。  位于子文件夹中的程序集和在其他路径中引用的程序集将不会获得完全信任授予集。  
  
-   如果可执行文件延迟加载程序集，则必须使用在启动该可执行文件时所使用的相同路径。  例如，如果共享\\\\*network\-computer*\\*share*映射到某个驱动器号，并且可执行文件是从该路径运行的，那么由该可执行文件使用网络路径加载的程序集将不会被授予完全信任。  若要在 <xref:System.Security.SecurityZone> 区域中延迟加载程序集，可执行文件必须使用驱动器号路径。  
  
## 还原以前的 Internet 策略  
 在早期版本的 .NET Framework 中，会将 <xref:System.Security.SecurityZone> 区域证据授予共享程序集。  您必须指定代码访问安全策略以将完全信任授予共享中的程序集。  
  
 此新行为是 Intranet 程序集的默认行为。  通过设置应用于计算机中所有应用程序的注册表项，可以恢复到提供 <xref:System.Security.SecurityZone> 证据的早期版本行为。  此过程在 32 位和 64 位计算机上各不相同。  
  
-   在 32 位计算机上，在系统注册表中的 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework 项下创建一个子项。  使用 DWORD 值为 1 项名称 LegacyMyComputerZone。  
  
-   在 64 位计算机上，在系统注册表中的 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework 项下创建一个子项。  使用 DWORD 值为 1 项名称 LegacyMyComputerZone。  在 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\.NETFramework 项下创建相同的子项。  
  
## 请参阅  
 [使用程序集编程](../../../docs/framework/app-domains/programming-with-assemblies.md)