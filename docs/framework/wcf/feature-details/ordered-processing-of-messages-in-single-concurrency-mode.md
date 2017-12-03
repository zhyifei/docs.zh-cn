---
title: "单并发模式中的有序消息处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c677ed869c0e5dd0df1288de48668ba403df5aa
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a><span data-ttu-id="b89d1-102">单并发模式中的有序消息处理</span><span class="sxs-lookup"><span data-stu-id="b89d1-102">Ordered Processing of Messages in Single Concurrency Mode</span></span>
<span data-ttu-id="b89d1-103">WCF 可使消息的处理顺序无法保证，除非基础通道是会话。</span><span class="sxs-lookup"><span data-stu-id="b89d1-103">WCF makes no guarantees about the order in which messages are processed, unless the underlying channel is sessionful.</span></span>  <span data-ttu-id="b89d1-104">例如，使用 MsmqInputChannel，不是会话通道，WCF 服务将无法按顺序处理信息。</span><span class="sxs-lookup"><span data-stu-id="b89d1-104">For instance, a WCF service that uses MsmqInputChannel, which is not a sessionful channel, will fail to process messages in order.</span></span> <span data-ttu-id="b89d1-105">有某些情况下，其中开发人员可能想在订单处理行为，但不是想使用会话。</span><span class="sxs-lookup"><span data-stu-id="b89d1-105">There are some circumstances where a developer may want the in order processing behavior but not want to use sessions.</span></span> <span data-ttu-id="b89d1-106">本主题介绍在单一并发模式中运行服务时，如何配置这种行为。</span><span class="sxs-lookup"><span data-stu-id="b89d1-106">This topic describes how to configure this behavior when a service is running in Single Concurrency Mode.</span></span>  
  
## <a name="in-order-message-processing"></a><span data-ttu-id="b89d1-107">有序消息处理</span><span class="sxs-lookup"><span data-stu-id="b89d1-107">In-order Message Processing</span></span>  
 <span data-ttu-id="b89d1-108">名为 <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> 的新特性已添加到 <xref:System.ServiceModel.ServiceBehaviorAttribute>。</span><span class="sxs-lookup"><span data-stu-id="b89d1-108">A new attribute called <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> has been added to the <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span></span> <span data-ttu-id="b89d1-109">当 <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> 设置为 true 并且<xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> 设置为 <xref:System.ServiceModel.ConcurrencyMode.Single> 时，将按顺序处理发送到服务的消息。</span><span class="sxs-lookup"><span data-stu-id="b89d1-109">When <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> is set to true and <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to <xref:System.ServiceModel.ConcurrencyMode.Single> messages sent to the service will be processed in order.</span></span> <span data-ttu-id="b89d1-110">下面的代码段演示如何设置这些特性。</span><span class="sxs-lookup"><span data-stu-id="b89d1-110">The following code snippet illustrates how to set these attributes.</span></span>  
  
```  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 <span data-ttu-id="b89d1-111">如果 <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> 设置为任何其他值，则引发 <xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="b89d1-111">If <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> is set to any other value, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b89d1-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b89d1-112">See Also</span></span>  
 [<span data-ttu-id="b89d1-113">会话，实例化和并发</span><span class="sxs-lookup"><span data-stu-id="b89d1-113">Sessions, Instancing, and Concurrency</span></span>](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [<span data-ttu-id="b89d1-114">并发</span><span class="sxs-lookup"><span data-stu-id="b89d1-114">Concurrency</span></span>](../../../../docs/framework/wcf/samples/concurrency.md)
