---
title: ".NET Framework 4.6.1 中的运行时更改 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime changes, .NET Framework
- runtime changes, .NET Framework 4.6.1
- application compatibility
ms.assetid: 9d97421c-5fee-4523-98c9-a158e7e6a1ee
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b8c6ec4d0bad4a769fb4d19a98c9e8a4eda0db78
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-461"></a>.NET Framework 4.6.1 中的运行时更改
在极少数情况下，运行时更改可能影响面向以前版本的 .NET Framework 但更高版本的 .NET Framework 运行时上运行的现有应用。 他们还包括运行于不同 .NET Framework 运行时环境上的应用程序间的行为差异。 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 包括以下方面的更改：  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|使用 `TransportWithMessageCredential` 安全模式的 WCF 绑定|默认情况下，对于非对称安全密钥，使用 `TransportWithMessageCredential` 安全模式的 WCF 绑定不允许带未签名“to”标头的消息。 从在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 下运行的应用开始，可能放宽此要求，并可接收没有签署“to”标头的消息。|这是一项选择加入的行为。 若要允许带未签名“to”标头的消息，请将以下配置设置添加到应用的配置文件的 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分：<br /><br /> `<runtime>     <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />  </runtime>`<br /><br /> 由于这是一项可以选择使用的功能，因此它不应影响现有应用的行为。|边缘|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|<xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName>|当 <xref:System.Windows.Controls.ItemsControl> 使用虚拟化 (<xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> = `true`) 和项滚动 (<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>) 显示集合以及控件滚动显示像素高度不同于其相邻项的项时，<xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> 会循环访问集合中的所有项。   UI 在该循环访问过程中处于不响应状态；如果集合非常大，这可能会被视为挂起。<br /><br /> 在其他情况下会发生此循环访问，甚至在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 之前的版本中也会发生。 例如，在以下情况下会出现上述情形：遇到像素高度不同的项时进行像素滚动 (<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>)，以及遇到子项数量不同于其相邻项的项时进行项滚动分层数据（例如，在 <xref:System.Windows.Controls.TreeView> 控件中，或已启用分组的 <xref:System.Windows.Controls.ItemsControl> 中）。<br /><br /> 对于项滚动和像素高度不同的情况，会在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 中引入循环访问以修复分层数据布局中存在的 bug。  如果数据采用平面结构（没有任何层次结构），则并不需要进行循环访问，[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 在这种情况下也不会执行该操作。|如果循环访问发生在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 中，但在以前版本中并未发生（也就是说，如果 <xref:System.Windows.Controls.ItemsControl> 项滚动含有像素高度不同的项的平面列表），可采用以下两种补救措施：<br /><br /> 安装 [.NET Framework 4.6.2](../../../docs/framework/install/guide-for-developers.md)。<br /><br /> 安装适用于 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 的 [修补程序 HR 1605](https://support.microsoft.com/en-us/kb/3154529)。|次要|  
## <a name="see-also"></a>另请参阅  
 [4.6.1 中的应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)
