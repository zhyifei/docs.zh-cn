---
title: "缓解：WPF 应用程序中的区域性和调度程序操作 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 455c1452-8ce0-45ae-a092-21fb8edf1cac
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1aee32c5c50c4ff4309f93bff270e6c3b3c8f7cc
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-culture-and-dispatcher-operations-in-wpf-apps"></a>缓解：WPF 应用程序中的区域性和调度程序操作
在面向 .NET Framework 4.6 和 .NET Framework 4.6.1 的应用中，在 <xref:System.Windows.Threading.Dispatcher> 中对 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 或 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 属性所做的更改在调度程序操作结束时都会丢失。 同样，在调度程序操作之外对 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 或 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 所做的更改在该操作执行时可能并不会反映出来。  
  
 这是由于 <xref:System.Threading.ExecutionContext> 更改导致 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 和 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 存储在执行上下文中所致。 WPF 调度程序操作存储用于启动操作的执行上下文，并在操作完成时还原以前的上下文。 因为 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 和 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 现在属于上下文，在调度程序操作中对它们所做的更改不会在操作之外保留。  
  
## <a name="impact"></a>影响  
 实际上，也就是说，对 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 和 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 属性所做的更改可能不会在 WPF UI 回叫和 WPF 应用程序中的其他代码之间流动。  
  
## <a name="mitigation"></a>缓解操作  
 受此更改影响的应用程序可以使用下面两种方法之一解决此问题：  
  
-   将所需的 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 或 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 存储在字段中，然后检查所有 <xref:System.Windows.Threading.Dispatcher> 操作正文（包括 UI 事件回叫处理程序）是否均已正确设置 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 或 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>。  
  
-   因为对 <xref:System.Threading.ExecutionContext> 的更改仅影响定位 .NET Framework 4.6 或 .NET Framework 4.6.1 的 WPF 应用程序，所以可通过定位 .NET Framework 4.5.2 或定位 .NET Framework 4.6.2 及更高版本来避免这一更改。  
  
## <a name="see-also"></a>另请参阅  
 [重定目标更改](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
