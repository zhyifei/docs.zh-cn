---
title: System.ServiceModel.ManualFlowThrottleLimitReached
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 556afe035697ee35d7ba86185b5b768a645c32c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelmanualflowthrottlelimitreached"></a>System.ServiceModel.ManualFlowThrottleLimitReached
System.ServiceModel.ManualFlowThrottleLimitReached  
  
## <a name="description"></a>描述  
 系统已达到为 ManualFlowControlLimit throttle 阈值设置的限制。 通过对 ServiceHost 或 InstanceContext 上的 ManualFlowControlLimit 属性进行适当修改，可以更改该阈值。  
  
 在手动流控制限制最初减少为 0 时发出此跟踪。 不跟踪后续更改为 0 的情况。 对于每个上下文只跟踪一次实例上下文上的流控制限制。  
  
## <a name="see-also"></a>另请参阅  
 [跟踪](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [使用跟踪来排查你的应用程序](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [管理和诊断](../../../../../docs/framework/wcf/diagnostics/index.md)
