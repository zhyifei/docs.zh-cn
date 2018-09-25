---
title: 实现 UI 自动化 TableItem 控件模式
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: e5d5e82c5c2cfc48c98559bd6ce14519bdfaa522
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47085913"
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a>实现 UI 自动化 TableItem 控件模式
> [!NOTE]
>  本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API: UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 本主题介绍的实现准则和约定<xref:System.Windows.Automation.Provider.ITableItemProvider>，包括有关事件和属性的信息。 本概述的结尾列出了指向其他参考资料的链接。  
  
 <xref:System.Windows.Automation.TableItemPattern>控件模式用于支持实现的容器的子控件<xref:System.Windows.Automation.Provider.ITableProvider>。 对个别单元格功能的访问必需的并发实现提供<xref:System.Windows.Automation.Provider.IGridItemProvider>。 此控件模式是类似于<xref:System.Windows.Automation.Provider.IGridItemProvider>与任何控件实现的区别<xref:System.Windows.Automation.Provider.ITableItemProvider>必须以编程方式公开各个单元格与其行和列信息之间的关系。 有关实现此控件模式的控件示例，请参阅 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)。  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>实现准则和约定  
  
-   有关相关的网格项功能，请参阅[实现 UI 自动化 GridItem 控件模式](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)。  
  
<a name="Required_Members_for_ITableItemProvider"></a>   
## <a name="required-members-for-itableitemprovider"></a>ITableItemProvider 必需的成员  
  
|必需的成员|成员类型|说明|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|方法|无|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|方法|无|  
  
 没有与此控件模式关联的属性或事件。  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>异常  
 没有与此控件模式关联的异常。  
  
## <a name="see-also"></a>请参阅  
 [UI 自动化控件模式概述](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [在 UI 自动化提供程序中支持控件模式](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [客户端的 UI 自动化控件模式](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [实现 UI 自动化 Table 控件模式](../../../docs/framework/ui-automation/implementing-the-ui-automation-table-control-pattern.md)  
 [实现 UI 自动化 GridItem 控件模式](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)  
 [UI 自动化树概述](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [在 UI 自动化中使用缓存](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
