---
title: Windows 窗体安全
ms.date: 03/30/2017
helpviewer_keywords:
- designer access security [Windows Forms]
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms]
- access control [Windows Forms], Windows Forms
- security policy [Windows Forms], Windows Forms
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
ms.openlocfilehash: 75016e9e04cf47782add18c87f7c677931743a4e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556173"
---
# <a name="windows-forms-security"></a>Windows 窗体安全
Windows 窗体的功能是基于代码的 （安全级别设置为代码，而不考虑运行代码的用户） 的安全模型。 其中不包括任何可能已在您的计算机系统中的安全架构。 其中可能包括那些在浏览器 （如基于区域的安全在 Internet Explorer 中可用） 或操作系统 （例如基于凭据的 Windows NT 的安全性）。  
  
## <a name="in-this-section"></a>本节内容  
 [Windows 窗体中的安全性概述](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 简要介绍了.NET Framework 安全模型并要确保你的应用程序中的 Windows 窗体所需的基本步骤的安全。  
  
 [在 Windows 窗体中提高文件和数据访问的安全性](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 介绍如何访问文件和不完全受信任环境中的数据。  
  
 [Windows 窗体中更加安全的打印](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 介绍如何访问部分信任的环境中的打印功能。  
  
 [Windows 窗体中额外的安全注意事项](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 介绍使用剪贴板，并调用非托管代码在部分信任的环境中执行窗口操作。  
  
## <a name="related-sections"></a>相关章节  
 [NIB： 默认安全策略](https://msdn.microsoft.com/library/2c086873-0894-4f4d-8f7e-47427c1a3b55)  
 列出了授予完全信任、 本地 Intranet 和 Internet 权限集的默认权限。  
  
 [NIB： 常规安全策略管理](https://msdn.microsoft.com/library/5121fe35-f0e3-402c-94ab-4f35b0a87b4b)  
 提供有关管理的.NET Framework 安全策略和提升权限的信息。  
  
 [危险权限和策略管理](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md)  
 讨论一些可能允许绕过安全系统的.net Framework 权限。  
  
 [安全编码准则](../../../docs/standard/security/secure-coding-guidelines.md)  
 这些主题介绍用于安全地编写针对.NET Framework 代码的最佳做法的链接。  
  
 [NIB： 请求权限](https://msdn.microsoft.com/library/0447c49d-8cba-45e4-862c-ff0b59bebdc2)  
 介绍如何使用属性告知运行时知道你的代码需要运行哪些权限。  
  
 [安全性的基础概念](../../../docs/standard/security/key-security-concepts.md)  
 链接到介绍代码安全性的基本方面的主题。  
  
 [代码访问安全性基础知识](../../../docs/framework/misc/code-access-security-basics.md)  
 讨论使用运行时安全策略的.NET Framework 的基础知识。  
  
 [NIB： 确定何时修改安全策略](https://msdn.microsoft.com/library/af749b17-e461-409d-84b9-a3d44789db16)  
 介绍如何确定您的应用程序需要从默认的安全策略发生偏离。  
  
 [NIB： 部署安全策略](https://msdn.microsoft.com/library/f936c1e5-033b-4bd9-a3bd-a39ba733a681)  
 讨论用于部署的安全策略更改的最佳方式。
