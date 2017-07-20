---
title: "可靠性 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "代码, 可靠性"
  - "托管代码, 可靠性"
  - "可靠性 [.NET Framework]"
  - "SQL Server [.NET Framework]"
  - "编写可靠代码"
ms.assetid: 294aa306-0afe-4cbe-b397-86ba9f1860f8
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# 可靠性
在服务器环境（如 SQL Server）中执行的代码应防止出现异步异常，这一点很重要。  此处所讨论的可靠性并非专指 SQL Server，而是指为在 .NET Framework 2.0 版环境中执行的任何主机编写可靠代码。  但是，SQL Server 是第一个充分使用 2.0 版的新可靠性功能的服务，所以将其用作示例。  
  
 在 SQL Server 中运行的代码与其他服务器环境相比，必须遵循更加严格的可靠性准则。  这是由于 SQL Server 的平滑操作需要在资源几乎完全消耗的边缘进行。<xref:System.OutOfMemoryException> 和 <xref:System.Threading.ThreadAbortException> 异常在 SQL Server 环境中很常见。  这些准则通常较少地强调可靠性，而较多地强调允许完全受信任的托管代码在 <xref:System.AppDomain> 级回收中正常失败，这是服务器维持一致性和可用性的主要方法。  
  
## 本节内容  
 [SQL Server 编程和宿主保护特性](../../../docs/framework/performance/sql-server-programming-and-host-protection-attributes.md)  
 介绍 SQL Server 如何使用 <xref:System.Security.Permissions.HostProtectionAttribute> 特性来限制托管代码的执行。  
  
 [可靠性最佳做法](../../../docs/framework/performance/reliability-best-practices.md)  
 为编写满足可靠性要求的代码提供准则。  
  
 [受约束的执行区域](../../../docs/framework/performance/constrained-execution-regions.md)  
 介绍受约束的执行区域 \(CER\) 的功能和行为。  
  
## 参考  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
  
 <xref:System.Security.Permissions.HostProtectionResource>