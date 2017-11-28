---
title: "在 UI 自动化提供程序中支持控件模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, supporting in UI Automation provider
- UI Automation, supporting control patterns in provider
ms.assetid: 0d635c35-ffa8-4dc8-bbc9-12fcd5445776
caps.latest.revision: "13"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: d427c4e3957dd620659f6f5097f4c16caf290d72
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="support-control-patterns-in-a-ui-automation-provider"></a>在 UI 自动化提供程序中支持控件模式
> [!NOTE]
>  本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](http://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 本主题演示如何在 UI 自动化提供程序上实现一个或多个控件模式，以便客户端应用程序可以操作控件并从中获取数据。  
  
### <a name="support-control-patterns"></a>支持控件模式  
  
1.  为元素应支持的控件模式实现相应的接口，例如为 为 <xref:System.Windows.Automation.Provider.IInvokeProvider> 实现 <xref:System.Windows.Automation.InvokePattern>。  
  
2.  返回包含的每个控件接口的实现中实现的对象<xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A?displayProperty=nameWithType>  
  
## <a name="example"></a>示例  
 下面的示例演示了对单项选择自定义列表框实现 <xref:System.Windows.Automation.Provider.ISelectionProvider> 。 它返回三个属性并获取当前所选的项。  
  
 [!code-csharp[UIAFragmentProvider_snip#119](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListPattern.cs#119)]
 [!code-vb[UIAFragmentProvider_snip#119](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListPattern.vb#119)]  
  
## <a name="example"></a>示例  
 下面的示例演示了返回实现 <xref:System.Windows.Automation.Provider.IRawElementProviderSimple.GetPatternProvider%2A> 的类的 <xref:System.Windows.Automation.Provider.ISelectionProvider>的实现。 大多数列表框控件还支持其他模式，但在本示例中对所有其他模式标识符返回了 null 引用（`Nothing` 中的 [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]）。  
  
 [!code-csharp[UIAFragmentProvider_snip#120](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#120)]
 [!code-vb[UIAFragmentProvider_snip#120](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#120)]  
  
## <a name="see-also"></a>另请参阅  
 [UI 自动化提供程序概述](../../../docs/framework/ui-automation/ui-automation-providers-overview.md)  
 [服务器端 UI 自动化提供程序实现](../../../docs/framework/ui-automation/server-side-ui-automation-provider-implementation.md)
