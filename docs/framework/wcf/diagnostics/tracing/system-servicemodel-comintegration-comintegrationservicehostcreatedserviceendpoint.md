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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4cecacdcc9ec1155fbb374bb763f6858da6ccc57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a>System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
无法移动或删除消息。  
  
## <a name="description"></a>描述  
 跟踪指示当尝试移动、删除或拒绝 MSMQ 消息时出错。  
  
 MSMQ 消息由 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 使用（当与 NetMsmqBinding 或 MsmqIntegrationBinding 一起使用时）。此跟踪与 NetMsmqBinding 或 MsmqIntegrationBinding 上的 `ReceiveErrorHandling` 属性的选定值相关。  
  
 此跟踪不会指示出全部的系统失败。 但是，它会指示某条消息的选定病毒消息处理失败。 请参阅[病毒消息处理](http://go.microsoft.com/fwlink/?LinkID=99546)有关消息何时成为病毒消息以及如何配置你的服务以适当地处理的详细信息。  
  
## <a name="see-also"></a>另请参阅  
 [跟踪](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [使用跟踪来排查你的应用程序](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [管理和诊断](../../../../../docs/framework/wcf/diagnostics/index.md)
