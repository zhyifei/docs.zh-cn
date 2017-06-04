---
title: ".NET Framework 4.6.1 中的运行时更改 | Microsoft Docs"
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
  - ".NET Framework 的运行时更改"
  - ".NET Framework 4.6.1 的运行时更改"
  - "应用程序兼容性"
ms.assetid: 9d97421c-5fee-4523-98c9-a158e7e6a1ee
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# .NET Framework 4.6.1 中的运行时更改
在极少数情况下，运行时更改可能影响面向以前版本的 .NET Framework 但更高版本的 .NET Framework 运行时上运行的现有应用。 他们还包括运行于不同 .NET Framework 运行时环境上的应用程序间的行为差异。 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]包括以下几个方面的更改︰  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|使用 WCF 绑定`TransportWithMessageCredential`安全模式|默认情况下，WCF 绑定，它使用`TransportWithMessageCredential`安全模式不允许使用无符号的消息"to"标头为非对称安全密钥。 从下运行的应用程序开始[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]，就可以放宽此要求和接收不对"to"标头进行签名的消息。|这是一项选择加入的行为。 若要允许将消息与"to"标头未签名，请添加以下配置设置来[ <> \> ](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)应用程序的配置文件节︰<br /><br /> `<runtime>     <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />  </runtime>`<br /><br /> 由于这是一项可以选择使用的功能，因此它不应影响现有应用的行为。|边缘|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
  
|功能|更改|影响|范围|  
|-------------|------------|------------|-----------|  
|<xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName>|当<xref:System.Windows.Controls.ItemsControl>显示使用虚拟化的集合 (<xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> = `true`) 和项滚动 (<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>)，和控件滚动以显示其高度 （像素） 不同于其邻近某项时<xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName>循环访问集合中的所有项。   在此小版本; 过程 UI 无响应 如果集合很大，这可以被视作挂起。<br /><br /> 在其他情况下，甚至在之前的版本中进行此迭代[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]。 例如，发生像素滚动时 (<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>) 项滚动时遇到项不同的像素高度，和后分层数据 (如在<xref:System.Windows.Controls.TreeView>控件或<xref:System.Windows.Controls.ItemsControl>与启用的分组) 一旦遇到具有不同数量的子代的项的数目与其相邻元素的项。<br /><br /> 为项滚动和不同像素高度的情况下，最小版本中引入[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]若要修复的分层数据的布局中的 bug。  如果数据不变时则不需要 （有无层次结构），与[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]就不会进行这种情况下。|如果在进行迭代[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]但不是在早期版本中 — 也就是说，如果<xref:System.Windows.Controls.ItemsControl>项滚动的平面列表具有不同的像素高度-项目有两种补救措施︰<br /><br /> 安装[.NET Framework 4.6.2](../../../docs/framework/install/guide-for-developers.md)。<br /><br /> 安装[修补程序 HR 1605](https://support.microsoft.com/en-us/kb/3154529)为[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]。|次要|  
  
## <a name="see-also"></a>另请参阅  
 [4.6.1 在应用程序兼容性](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)