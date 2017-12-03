---
title: System.ServiceModel.Channels.FailedPipeConnect
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a827e0f-fb91-46bb-bd54-926d4b74d8a6
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d1386d9ac7f58e4dd692bbca3ca3915bc3fe453f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="systemservicemodelchannelsfailedpipeconnect"></a>System.ServiceModel.Channels.FailedPipeConnect
尝试连接到指定的管道终结点失败。 将在指定的超时期限内再次进行尝试。  
  
## <a name="description"></a>描述  
 此信息跟踪指示未能连接到指定的管道终结点。 如果未找到指定的管道终结点或指定的管道终结点正忙，则可能会发生此情况。 将进行更多的尝试（两次尝试之间的时间较短），直到尝试成功或 OpenTimeout 过期。  
  
## <a name="see-also"></a>另请参阅  
 [跟踪](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [使用跟踪来排查你的应用程序](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [管理和诊断](../../../../../docs/framework/wcf/diagnostics/index.md)
