---
title: "Windows 窗体安全"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- designer access security [Windows Forms]
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms]
- access control [Windows Forms], Windows Forms
- security policy [Windows Forms], Windows Forms
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8bd9b87fdfa54a6f9bf53e4fa897106257b4c625
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="windows-forms-security"></a>Windows 窗体安全
Windows 窗体功能是基于代码的 （安全级别设置为代码，无论运行代码的用户） 的安全模型。 这是除了可能已在您的计算机系统中的任何安全架构。 其中可能包括浏览器 （如基于区域的安全在 Internet Explorer 中可用） 或操作系统 （例如 Windows NT 的凭据基于安全性） 中。  
  
## <a name="in-this-section"></a>本节内容  
 [Windows 窗体中的安全性概述](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 简要介绍了.NET Framework 安全模型和需确保你的应用程序中的 Windows 窗体的基本步骤都是安全的。  
  
 [在 Windows 窗体中提高文件和数据访问的安全性](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 描述如何访问文件和不完全受信任环境中的数据。  
  
 [Windows 窗体中更加安全的打印](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 介绍如何访问部分信任的环境中的打印功能。  
  
 [Windows 窗体中额外的安全注意事项](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 描述执行窗口操作、 使用剪贴板，以及调用到非托管代码在不完全受信任的环境中。  
  
## <a name="related-sections"></a>相关章节  
 [NIB： 默认安全策略](http://msdn.microsoft.com/library/2c086873-0894-4f4d-8f7e-47427c1a3b55)  
 列出授予完全信任、 本地 Intranet 和 Internet 权限集的默认权限。  
  
 [NIB： 常规安全策略管理](http://msdn.microsoft.com/library/5121fe35-f0e3-402c-94ab-4f35b0a87b4b)  
 提供有关管理.NET Framework 安全策略和提升权限的信息。  
  
 [危险权限和策略管理](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md)  
 讨论一些可能允许绕过安全系统的.net Framework 权限。  
  
 [安全编码准则](../../../docs/standard/security/secure-coding-guidelines.md)  
 这些主题介绍安全地编写针对.NET Framework 的代码的最佳做法的链接。  
  
 [NIB： 请求权限](http://msdn.microsoft.com/library/0447c49d-8cba-45e4-862c-ff0b59bebdc2)  
 讨论特性，以便知道你的代码需要运行哪些权限的运行时的使用。  
  
 [安全性的基础概念](../../../docs/standard/security/key-security-concepts.md)  
 链接到涵盖的基本代码安全性方面的主题。  
  
 [代码访问安全性基础知识](../../../docs/framework/misc/code-access-security-basics.md)  
 讨论使用运行时的安全策略的.NET Framework 的基础知识。  
  
 [NIB： 确定何时修改安全策略](http://msdn.microsoft.com/library/af749b17-e461-409d-84b9-a3d44789db16)  
 说明如何确定你的应用程序需要以偏离默认安全策略时。  
  
 [NIB： 部署安全策略](http://msdn.microsoft.com/library/f936c1e5-033b-4bd9-a3bd-a39ba733a681)  
 讨论将安全策略更改部署的最佳方式。
