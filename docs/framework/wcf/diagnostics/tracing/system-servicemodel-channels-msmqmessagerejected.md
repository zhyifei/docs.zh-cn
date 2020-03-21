---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 8f783dcd4b966ed89c24d724918a3923c5a2d0b1
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674777"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a>System.ServiceModel.Channels.MsmqMessageRejected
MSMQ 已拒绝该消息。  
  
## <a name="description"></a>说明  
 此跟踪指示已拒绝 MSMQ 消息。  
  
 当 Windows 通信基础 （WCF） （与 NetMmqBinding 或 Msmq 集成绑定一起使用） 无法处理 MSMQ 消息时，MSMQ 消息可能会被拒绝。 这些消息称为病毒消息。 当 NetMsmqBinding 或 MsmqIntegrationBinding 上的 `ReceiveErrorHandling` 属性设置为 `Reject` 时，将拒绝病毒消息。 被拒绝的邮件将传递回发件人[的死信队列](https://docs.microsoft.com/dotnet/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures)。  
  
 有关消息何时成为病毒以及如何配置服务以正确处理它们的详细信息，请参阅[毒消息处理](../../feature-details/poison-message-handling.md)。  
  
 有关被拒绝的邮件在 MSMQ 中的含义的详细信息，请参阅[MQMarkMessage 拒绝](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))。  
  
## <a name="see-also"></a>另请参阅

- [跟踪](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [使用跟踪来排除应用程序故障](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [管理和诊断](../../../../../docs/framework/wcf/diagnostics/index.md)
- [病毒消息处理](../../feature-details/poison-message-handling.md)
- [MQMark消息被拒绝](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))
