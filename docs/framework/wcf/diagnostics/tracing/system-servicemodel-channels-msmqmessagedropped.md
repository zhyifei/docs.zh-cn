---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: e80fecf508158dcb53f08b75c8f9486c13e403a4
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674798"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a>System.ServiceModel.Channels.MsmqMessageDropped
MSMQ 已删除该消息。  
  
## <a name="description"></a>说明  
 该跟踪指示已丢弃 MSMQ 消息。 当 Windows 通信基础 （WCF） （与 NetMmqBinding 或 Msmq 集成绑定一起使用） 无法处理它们时，MSMQ 消息可以被删除。 这些消息称为病毒消息。  
  
 当 NetMsmqBinding 或 MsmqIntegrationBinding 上的 `ReceiveErrorHandling` 属性设置为 `Drop` 时，将丢弃病毒消息。 丢弃的消息会从队列中移除而不再可恢复。  
  
 有关消息何时成为病毒以及如何配置服务以正确处理它们的详细信息，请参阅[毒消息处理](../../feature-details/poison-message-handling.md)。  
  
## <a name="see-also"></a>另请参阅

- [跟踪](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [使用跟踪来排除应用程序故障](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [管理和诊断](../../../../../docs/framework/wcf/diagnostics/index.md)
- [病毒消息处理](../../feature-details/poison-message-handling.md)
