---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 87eac8f0e3949ac47c7bb2915a87043bdc205b8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a>System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
无法移动或删除消息。  
  
## <a name="description"></a>描述  
 跟踪指示当尝试移动、删除或拒绝 MSMQ 消息时出错。  
  
 MSMQ 消息由 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 使用（当与 NetMsmqBinding 或 MsmqIntegrationBinding 一起使用时）。此跟踪与 NetMsmqBinding 或 MsmqIntegrationBinding 上的 `ReceiveErrorHandling` 属性的选定值相关。  
  
 此跟踪不会指示出全部的系统失败。 但是，它会指示某条消息的选定病毒消息处理失败。 请参阅[病毒消息处理](http://go.microsoft.com/fwlink/?LinkID=99546)有关消息何时成为病毒消息以及如何配置你的服务以适当地处理的详细信息。  
  
## <a name="see-also"></a>请参阅  
 [跟踪](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [使用跟踪来排除应用程序故障](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [管理和诊断](../../../../../docs/framework/wcf/diagnostics/index.md)
