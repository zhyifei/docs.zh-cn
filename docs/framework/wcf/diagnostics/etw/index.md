---
title: 使用 ETW 进行分析跟踪
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: dd745730ca186b9489c547f790c546e95bf96372
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798086"
---
# <a name="analytic-tracing-with-etw"></a>使用 ETW 进行分析跟踪
Windows Communication Foundation （WCF）分析跟踪提供一种在执行 WCF 服务的过程中捕获诊断信息的方法。 在 WCF 堆栈中的关键点处发出 WCF 分析跟踪事件，以允许在生产环境中对 WCF 服务进行故障排除。 Wcf 服务的分析跟踪对承载[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] wcf 服务的产品服务器的性能的影响最小，因为这些事件非常有效地发送到 Windows 事件跟踪（ETW）会话。  
  
## <a name="in-this-section"></a>本节内容  
 [分析跟踪概述](analytic-tracing-overview.md)  
 讨论 WCF 分析跟踪在中的[!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]工作方式。  
  
 [动态启用分析跟踪](dynamically-enabling-analytic-tracing.md)  
 讨论如何使用 ETW 动态启用或禁用跟踪。  
  
 [配置消息流跟踪](configuring-message-flow-tracing.md)  
 描述如何配置消息流跟踪。  
  
 [分析跟踪事件参考](analytic-trace-event-reference.md)  
 显示一张表，其中包括事件 ID 及其事件级别、事件消息和关键字。  
  
## <a name="see-also"></a>请参阅

- [WCF Services and Event Tracing for Windows](../../samples/wcf-services-and-event-tracing-for-windows.md)
- [在 Windows 中将事件跟踪到事件跟踪](../../../windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
