---
title: 通过部分受信任的代码使用库
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], partially trusted code
- partially trusted code
- partial trust
- AllowPartiallyTrustedCallersAttribute attribute
- code access security, partially trusted code
- APTCA
ms.assetid: dd66cd4c-b087-415f-9c3e-94e3a1835f74
ms.openlocfilehash: 61291a07639c3f92a05f78dff49f6b20f1aee77e
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645722"
---
# <a name="using-libraries-from-partially-trusted-code"></a>通过部分受信任的代码使用库
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
> [!NOTE]
> 本主题讨论强命名程序集的行为，并且仅适用于[级别 1](security-transparent-code-level-1.md)程序集。 [安全透明代码、.NET](security-transparent-code-level-2.md)框架 4 或更高版本中的 2 级程序集不受强名称的影响。 有关安全系统更改的详细信息，请参阅[安全更改](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes)。  
  
 不允许未从其主机或沙盒获取完全信任的应用程序调用共享的托管库，除非库编写器明确允许它们使用 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 特性。 因此，应用程序编写器必须注意某些库在部分受信任的上下文中将不可用。 默认情况下，在部分信任[沙盒](how-to-run-partially-trusted-code-in-a-sandbox.md)中执行且不在完全信任程序集列表中的所有代码都是部分受信任的。 如果不希望从部分受信任的上下文中执行或由部分受信任的代码调用自己的代码，则不必关心此部分的信息。 但是，如果所编写的代码必须与部分受信任的代码进行交互或从部分受信任的上下文环境进行操作，则应考虑以下因素：  
  
- 为了方便多个应用程序共享库，则必须使用强名称对库进行签名。 强名称允许你的代码可放入全局程序集缓存中或添加到沙盒处理 <xref:System.AppDomain> 的完全信任列表，并允许使用者验证实际来自你的移动代码的特定部分。  
  
- 默认情况下，强名称的[1 级](security-transparent-code-level-1.md)共享库自动执行隐式[LinkDemand](link-demands.md)以完全信任，而库编写器无需执行任何操作。  
  
- 如果调用方不具有完全信任但仍尝试调用这样的库，则运行时会引发 <xref:System.Security.SecurityException>，且会不允许调用方链接到库。  
  
- 为了禁用自动**LinkDemand**并防止引发异常，可以将**Allow 部分受信任的调用方属性**放在共享库的程序集作用域上。 此属性允许从部分受信任的托管代码调用你的库。  
  
- 被授予访问具有此属性的库的权限的部分受信任代码仍将受到由 <xref:System.AppDomain> 定义的进一步限制。  
  
- 没有编程方式让部分受信任的代码调用没有 **"允许部分受信任的调用方属性"属性**的库。  
  
 专用到特定应用程序的库不需要强名称或**AllowPartiallyTrustedCallers属性**，并且应用程序外部的潜在恶意代码无法引用。 保护此类代码免受部分受信任的移动代码的有意或无意滥用，而无需开发人员进行任何额外操作。  
  
 你应该考虑显式启用以下代码类型的部分受信任代码的用法：  
  
- 已对安全漏洞进行认真测试并符合[安全编码指南中描述的准则](../../standard/security/secure-coding-guidelines.md)的代码。  
  
- 专门为部分受信任的情况进行编写的强名称代码库。  
  
- 使用强名称签名的任何组件（无论是部分或完全受信任）都将由从 Internet 下载的代码调用。  
  
> [!NOTE]
> .NET Framework 类库中的某些类没有 **"允许部分受信任的调用方属性"属性**，并且无法由部分受信任的代码调用。  
  
## <a name="see-also"></a>另请参阅

- [代码访问安全性](code-access-security.md)
