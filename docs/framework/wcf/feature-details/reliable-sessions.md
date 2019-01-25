---
title: 可靠会话
ms.date: 03/30/2017
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
ms.openlocfilehash: 1d87f6f4d94763dc8f6ac7e929c22b17940097ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735417"
---
# <a name="reliable-sessions"></a>可靠会话

本部分介绍哪些 Windows Communication Foundation (WCF) 是可靠会话、 它的用途是什么，如何和何时使用它，哪些绑定配置支持它，以及有关最佳实践。 下表汇总了有关本节中要点和相关主题的详细信息。

可靠会话 WCF 提供了是确保终结点之间发送的消息通过 SOAP 或传输媒介传输，并在其中发送的顺序传递一次和 （可选）。

若要 WCF 应用程序中使用可靠会话，请使用 WCF 中默认情况下或作为一个选项，支持可靠会话的系统提供绑定之一，或创建您自己的自定义绑定的支持会话。

## <a name="in-this-section"></a>本节内容

[可靠会话概述](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)   
描述可靠会话、何时使用它们、支持可靠会话的不同绑定以及它们的工作方式。

[如何：可靠会话内交换消息](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)   
描述如何使用在配置中指定的自定义绑定创建通过 HTTP 的可靠会话。

[如何：可靠会话内保护消息](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md)   
描述如何保护可靠会话。

[如何：使用 HTTPS 创建自定义可靠会话绑定](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)   
描述如何创建通过 HTTPS 的可靠会话。

[可靠会话的最佳做法](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md)   
描述与使用可靠会话关联的一些最佳实践。

## <a name="reference"></a>参考

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a>请参阅

- [队列和可靠会话](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
- [会话、实例化和并发](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)
