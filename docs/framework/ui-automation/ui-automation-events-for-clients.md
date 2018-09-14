---
title: 客户端的 UI 自动化事件
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, events for clients
- events, UI Automation clients
ms.assetid: b909e388-3f24-4997-b6d4-bd9c35c2dc27
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: f295bbf44d6272879e8ea8e74c435d206b7af913
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615206"
---
# <a name="ui-automation-events-for-clients"></a>客户端的 UI 自动化事件
> [!NOTE]
>  本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。 有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API: UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。  
  
 本主题介绍如何[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]事件由 UI 自动化客户端。  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 允许客户端订阅感兴趣的事件。 此功能无需频繁地轮询所有，从而提高了性能[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]以查看任何信息、 结构或状态已更改的系统中的元素。  
  
 由于能够只侦听定义范围内的事件，因此效率也得到了提高。 例如，客户端可以侦听焦点更改事件对所有[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]在树中，或上一个元素及其子代元素。  
  
> [!NOTE]
>  不要假定所有可能的事件引发的[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]提供程序。 例如，并非所有属性更改会都导致事件的标准代理提供程序会引发[!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)]和[!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)]控件。  
  
 有关更广泛的视图[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]事件，请参阅[UI 自动化事件概述](../../../docs/framework/ui-automation/ui-automation-events-overview.md)。  
  
<a name="Subscribing_to_Events"></a>   
## <a name="subscribing-to-events"></a>订阅事件  
 客户端应用程序通过使用以下方法之一注册事件处理程序，从而订阅特定种类的事件。  
  
|方法|事件类型|事件参数类型|委托类型|  
|------------|----------------|--------------------------|-------------------|  
|<xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>|焦点更改|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|<xref:System.Windows.Automation.AutomationFocusChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>|属性更改|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddStructureChangedEventHandler%2A>|结构更改|<xref:System.Windows.Automation.StructureChangedEventArgs>|<xref:System.Windows.Automation.StructureChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>|所有其他事件，由标识 <xref:System.Windows.Automation.AutomationEvent>|<xref:System.Windows.Automation.AutomationEventArgs> 或 <xref:System.Windows.Automation.WindowClosedEventArgs>|<xref:System.Windows.Automation.AutomationEventHandler>|  
  
 在调用方法之前，必须创建一个委托方法来处理事件。 如果愿意，你可以在单一方法中处理不同种类的事件，并在多个调用中将此方法传递到表中的某个方法。 例如，将单个<xref:System.Windows.Automation.AutomationEventHandler>可以设置来处理各种事件以不同的方式根据<xref:System.Windows.Automation.AutomationEventArgs.EventId%2A>。  
  
> [!NOTE]
>  若要处理窗口关闭事件，强制转换参数类型传递给事件处理程序作为<xref:System.Windows.Automation.WindowClosedEventArgs>。 因为[!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]窗口的元素将不再有效，则不能使用`sender`参数来检索信息; 使用<xref:System.Windows.Automation.WindowClosedEventArgs.GetRuntimeId%2A>相反。  
  
> [!CAUTION]
>  如果你的应用程序可能会收到事件从其自身[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]，不要使用应用程序的[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]线程来订阅事件，或取消订阅。 这样做可能会导致不可预知的行为。 有关更多信息，请参见 [UI Automation Threading Issues](../../../docs/framework/ui-automation/ui-automation-threading-issues.md)。  
  
 在关闭，或当[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]事件不再感兴趣的应用程序，UI 自动化客户端应调用以下方法之一。  
  
|方法|描述|  
|------------|-----------------|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>|使用注册的事件处理程序中注销<xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>。|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationFocusChangedEventHandler%2A>|使用注册的事件处理程序中注销<xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>。|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>|使用注册的事件处理程序中注销<xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>。|  
|<xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>|取消注册所有已注册的事件处理程序。|  
  
 有关示例代码，请参阅[订阅 UI 自动化事件](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md)。  
  
## <a name="see-also"></a>请参阅  
 [订阅 UI 自动化事件](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md)  
 [UI 自动化事件概述](../../../docs/framework/ui-automation/ui-automation-events-overview.md)  
 [UI 自动化属性概述](../../../docs/framework/ui-automation/ui-automation-properties-overview.md)  
 [TrackFocus 示例](https://msdn.microsoft.com/library/4a91c0af-6bb5-4d38-a743-cf136f268fc9)
