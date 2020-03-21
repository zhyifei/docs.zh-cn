---
title: System.ServiceModel.Channels.MsmqPoisonMessageRejected
ms.date: 03/30/2017
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
ms.openlocfilehash: 6b0e6e3ebcf5d414e9dbbcecd09ba2e8bb3ddd3a
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674817"
---
# <a name="systemservicemodelchannelsmsmqpoisonmessagerejected"></a>System.ServiceModel.Channels.MsmqPoisonMessageRejected
拒绝的病毒消息。  
  
## <a name="description"></a>说明  

 该跟踪指示遇到病毒消息并随后将其拒绝。 当 NetMsmqBinding 或 MsmqIntegrationBinding 上的 `ReceiveErrorHandling` 属性设置为 `Reject` 时，将会出现此情况。 被拒绝的邮件将传递回发件人[的死信队列](../../feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)。  
  
 有关消息何时成为病毒以及如何配置服务以正确处理它们的详细信息，请参阅[毒消息处理](../../feature-details/poison-message-handling.md)。 有关被拒绝的邮件在 MSMQ 中的含义的详细信息，请参阅[MQMarkMessage 拒绝](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))。  
  
## <a name="see-also"></a>另请参阅

- [跟踪](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [使用跟踪来排除应用程序故障](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [管理和诊断](../../../../../docs/framework/wcf/diagnostics/index.md)
- [病毒消息处理](../../feature-details/poison-message-handling.md)
- [MQMark消息被拒绝](https://docs.microsoft.com/previous-versions/windows/desktop/msmq/ms707071(v%3dvs.85))
