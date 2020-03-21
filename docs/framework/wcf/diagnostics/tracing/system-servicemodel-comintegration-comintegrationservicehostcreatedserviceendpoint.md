---
title: System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
ms.date: 03/30/2017
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
ms.openlocfilehash: f89dd1373d67714046f8cb958582c3a5dea04456
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674779"
---
# <a name="systemservicemodelchannelsmsmqmoveordeleteattemptfailed"></a>System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
无法移动或删除消息。  
  
## <a name="description"></a>说明  
 跟踪指示当尝试移动、删除或拒绝 MSMQ 消息时出错。  
  
 MSMQ 消息受雇于 Windows 通信基金会 （WCF）（当与 NetMmq 绑定或 Msmq 集成绑定一起使用时）。此跟踪与 NetMmqBinding`ReceiveErrorHandling`或 Msmq集成绑定上属性的选定值相关。  
  
 此跟踪不会指示出全部的系统失败。 但是，它会指示某条消息的选定病毒消息处理失败。 有关消息何时成为病毒以及如何配置服务以正确处理它们的详细信息，请参阅[毒消息处理](../../feature-details/poison-message-handling.md)。  
  
## <a name="see-also"></a>另请参阅

- [跟踪](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [使用跟踪来排除应用程序故障](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [管理和诊断](../../../../../docs/framework/wcf/diagnostics/index.md)
