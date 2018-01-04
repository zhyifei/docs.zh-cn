---
title: "重要跟踪"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40a1770e-3b09-4142-b0dd-f9ef73642074
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6641fe633585caf6cbf068a804430f9171e5ece0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="significant-traces"></a>重要跟踪
本主题列出 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 发出的一些主要跟踪。  
  
## <a name="significant-traces"></a>重要跟踪  
  
|跟踪|描述|  
|-----------|-----------------|  
|消息日志跟踪|如果启用了 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 跟踪源，则当消息日志记录功能记录下 `System.ServiceModel.MessageLogging` 消息时发出此跟踪。 单击此跟踪可以显示消息。 一条消息有四个可配置的记录点：`ServiceLevelSendRequest`、`TransportSend`、`TransportReceive`、`ServiceLevelReceiveRequest`，消息日志跟踪的“消息源”属性中也指明了它们。|  
|已接收消息的跟踪|如果在信息级别或详细级别启用了 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 跟踪源，则将在接收到 `System.ServiceModel` 消息时发出此跟踪。 此跟踪对于在活动图形视图中查看消息相关箭头而言是必需的。|  
|已发送消息的跟踪|如果在信息级别或详细级别启用了 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 跟踪源，则当发送 `System.ServiceModel` 消息时发出此跟踪。 此跟踪对于在活动图形视图中查看消息相关箭头而言是必需的。|  
|获取 ChannelEndpointElement|在构建通道工厂时以信息级别发出此跟踪。 此跟踪提供对与客户端通信的终结点的说明（远程地址、绑定、协定名称）。|  
|获取 ServiceElement|在构建服务主机时以信息级别发出此跟踪。 此跟踪提供对服务协定和绑定的说明。|  
|SocketConnection 创建|在客户端执行的第一个处理操作中，以及在服务上的接收字节活动中发出此跟踪。 此跟踪提供本地和远程 IP 地址， 以信息级别发出。|
