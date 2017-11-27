---
title: "可靠会话"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 659309ff5560480c423fc9b0adab5e93eac05ce5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="reliable-sessions"></a>可靠会话

本节介绍什么[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]可靠会话是，它有何，如何及何时使用它，哪些绑定配置支持它，以及有关最佳实践。 下表汇总了有关本节中要点和相关主题的详细信息。

可靠会话[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]提供 featrues 确保终结点之间发送的消息跨 SOAP 或传输媒介传输，而与发送这些相同的顺序传递一次和 （可选）。

若要将可靠会话与 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 应用程序一起使用，请使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中默认情况下支持可靠会话或作为一个选项的系统提供绑定之一，或者创建自己的支持会话的自定义绑定。

## <a name="in-this-section"></a>本节内容

[可靠会话概述](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)   
描述可靠会话、何时使用它们、支持可靠会话的不同绑定以及它们的工作方式。

[如何： 在可靠会话内交换消息](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)   
描述如何使用在配置中指定的自定义绑定创建通过 HTTP 的可靠会话。

[如何： 在可靠会话内保护消息](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md)   
描述如何保护可靠会话。

[如何： 创建使用 HTTPS 的自定义可靠会话绑定](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)   
描述如何创建通过 HTTPS 的可靠会话。

[可靠会话的最佳实践](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md)   
描述与使用可靠会话关联的一些最佳实践。

## <a name="reference"></a>参考

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a>另请参阅

[队列和可靠会话](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)   
[会话，实例化和并发](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
