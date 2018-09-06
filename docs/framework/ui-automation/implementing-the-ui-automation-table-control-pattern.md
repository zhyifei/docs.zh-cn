---
title: 实现 UI 自动化 Table 控件模式
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Table control pattern
- control patterns, Table
- TableControl pattern
ms.assetid: 880cd85c-aa8c-4fb5-9369-45491d34bb78
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 7466a7cc25ac742483e21fc1ee4a631bd43bc5a3
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43798539"
---
# <a name="implementing-the-ui-automation-table-control-pattern"></a>实现 UI 自动化 Table 控件模式
> [!NOTE]
>  本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API: UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 本主题介绍实现 <xref:System.Windows.Automation.Provider.ITableProvider> 的准则和约定，包括有关属性、方法和事件的信息。 本概述的结尾列出了指向其他参考资料的链接。  
  
 <xref:System.Windows.Automation.TablePattern>控件模式用于支持充当子元素的集合的容器的控件。 此元素的子级必须实现<xref:System.Windows.Automation.Provider.ITableItemProvider>和组织可以按行和列进行遍历的二维逻辑坐标系统中。 此控件模式是类似于<xref:System.Windows.Automation.Provider.IGridProvider>，与任何控件实现的区别<xref:System.Windows.Automation.Provider.ITableProvider>还必须公开每个子元素的列和/或行标题关系。 有关实现此控件模式的控件示例，请参阅 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)。  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>实现准则和约定  
 在实现 Table 控件模式时，请注意以下准则和约定：  
  
-   对各个单元格的内容的访问是通过二维逻辑坐标系统或数组的所需的并发实现提供<xref:System.Windows.Automation.Provider.IGridProvider>。  
  
-   列或行标头可包含在表对象中或可以为与表对象相关联的单独标头对象。  
  
-   列和行标头可能包含主标头以及任何支持的标头。  
  
> [!NOTE]
>  这一概念将变得显而易见中[!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)]电子表格用户定义的"名字"列。 此列现在有两个标头 — 用户定义的“名字”标头和应用程序分配的该列的字母数字名称。  
  
-   请参阅[实现 UI 自动化 Grid 控件模式](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)相关的网格功能。  
  
 ![具有复杂标题项的表。](../../../docs/framework/ui-automation/media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")  
具有复杂列标头的表示例  
  
 ![具有不明确的 RowOrColumnMajor 属性的表。](../../../docs/framework/ui-automation/media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")  
具有不明确的 RowOrColumnMajor 属性的表示例。  
  
<a name="Required_Members_for_ITableProvider"></a>   
## <a name="required-members-for-itableprovider"></a>ITableProvider 必需的成员  
 ITableProvider 接口需要以下属性和方法。  
  
|必需的成员|成员类型|说明|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableProvider.RowOrColumnMajor%2A>|属性|无|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetColumnHeaders%2A>|方法|无|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetRowHeaders%2A>|方法|无|  
  
 没有与此控件模式关联的事件。  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>异常  
 没有与此控件模式关联的异常。  
  
## <a name="see-also"></a>请参阅  
 [UI 自动化控件模式概述](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [在 UI 自动化提供程序中支持控件模式](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [客户端的 UI 自动化控件模式](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [实现 UI 自动化 TableItem 控件模式](../../../docs/framework/ui-automation/implementing-the-ui-automation-tableitem-control-pattern.md)  
 [实现 UI 自动化 Grid 控件模式](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)  
 [UI 自动化树概述](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [在 UI 自动化中使用缓存](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
