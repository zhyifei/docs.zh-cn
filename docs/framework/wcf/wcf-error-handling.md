---
title: "WCF 错误处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e4b1e0f-9598-449d-9d73-90bda62305b8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 860f96ee92db6a11238942202d4e202ba912d748
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-error-handling"></a><span data-ttu-id="f0436-102">WCF 错误处理</span><span class="sxs-lookup"><span data-stu-id="f0436-102">WCF Error Handling</span></span>
<span data-ttu-id="f0436-103">WCF 应用程序遇到的错误属于下列三组中的一组：</span><span class="sxs-lookup"><span data-stu-id="f0436-103">The errors encountered by a WCF application belong to one of three groups:</span></span>  
  
1.  <span data-ttu-id="f0436-104">通信错误</span><span class="sxs-lookup"><span data-stu-id="f0436-104">Communication Errors</span></span>  
  
2.  <span data-ttu-id="f0436-105">代理/通道错误</span><span class="sxs-lookup"><span data-stu-id="f0436-105">Proxy/Channel Errors</span></span>  
  
3.  <span data-ttu-id="f0436-106">应用程序错误</span><span class="sxs-lookup"><span data-stu-id="f0436-106">Application Errors</span></span>  
  
 <span data-ttu-id="f0436-107">网络不可用、客户端使用错误地址或服务主机未侦听传入消息时，会发生通信错误。</span><span class="sxs-lookup"><span data-stu-id="f0436-107">Communication errors occur when a network is unavailable, a client uses an incorrect address, or the service host is not listening for incoming messages.</span></span> <span data-ttu-id="f0436-108">这种类型的错误将作为 <xref:System.ServiceModel.CommunicationException> 或 <xref:System.ServiceModel.CommunicationException> 派生的类返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="f0436-108">Errors of this type are returned to the client as <xref:System.ServiceModel.CommunicationException> or <xref:System.ServiceModel.CommunicationException>-derived classes.</span></span>  
  
 <span data-ttu-id="f0436-109">代理/通道错误是通道或代理自身内部发生的错误。</span><span class="sxs-lookup"><span data-stu-id="f0436-109">Proxy/Channel errors are errors that occur within the channel or proxy itself.</span></span> <span data-ttu-id="f0436-110">这种类型的错误包括：尝试使用已关闭的代理或通道，客户端和服务之间存在协定不匹配，或者客户端凭据被服务拒绝。</span><span class="sxs-lookup"><span data-stu-id="f0436-110">Errors of this type include: attempting to use a proxy or channel that has been closed, a contract mismatch exists between the client and service, or the client’s credentials are rejected by the service.</span></span> <span data-ttu-id="f0436-111">此类别中存在许多不同类型的错误，错误太多，恕不在此列出。</span><span class="sxs-lookup"><span data-stu-id="f0436-111">There are many different types of errors in this category, too many to list here.</span></span> <span data-ttu-id="f0436-112">这种类型的错误将按原样返回到客户端（不对异常对象执行任何转换）。</span><span class="sxs-lookup"><span data-stu-id="f0436-112">Errors of this type are returned to the client as-is (no transformation is performed on the exception objects).</span></span>  
  
 <span data-ttu-id="f0436-113">执行服务操作过程中发生应用程序错误。</span><span class="sxs-lookup"><span data-stu-id="f0436-113">Application errors occur during the execution of a service operation.</span></span> <span data-ttu-id="f0436-114">这种类型的错误将作为 <xref:System.ServiceModel.FaultException> 或 <xref:System.ServiceModel.FaultException%601> 发送到客户端。</span><span class="sxs-lookup"><span data-stu-id="f0436-114">Errors of this kind are sent to the client as <xref:System.ServiceModel.FaultException> or <xref:System.ServiceModel.FaultException%601>.</span></span>  
  
 <span data-ttu-id="f0436-115">通过以下一种或多种方法执行 WCF 中的错误处理：</span><span class="sxs-lookup"><span data-stu-id="f0436-115">Error handling in WCF is performed by one or more of the following:</span></span>  
  
-   <span data-ttu-id="f0436-116">直接处理引发的异常。</span><span class="sxs-lookup"><span data-stu-id="f0436-116">Directly handling the exception thrown.</span></span> <span data-ttu-id="f0436-117">只能针对通信错误以及代理/通道错误执行此操作。</span><span class="sxs-lookup"><span data-stu-id="f0436-117">This is only done for communication and proxy/channel errors.</span></span>  
  
-   <span data-ttu-id="f0436-118">使用错误协定</span><span class="sxs-lookup"><span data-stu-id="f0436-118">Using fault contracts</span></span>  
  
-   <span data-ttu-id="f0436-119">实现 <xref:System.ServiceModel.Dispatcher.IErrorHandler> 接口</span><span class="sxs-lookup"><span data-stu-id="f0436-119">Implementing the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface</span></span>  
  
-   <span data-ttu-id="f0436-120">处理 <xref:System.ServiceModel.ServiceHost> 事件</span><span class="sxs-lookup"><span data-stu-id="f0436-120">Handling <xref:System.ServiceModel.ServiceHost> events</span></span>  
  
## <a name="fault-contracts"></a><span data-ttu-id="f0436-121">错误协定</span><span class="sxs-lookup"><span data-stu-id="f0436-121">Fault Contracts</span></span>  
 <span data-ttu-id="f0436-122">利用错误协定，您可以独立于平台的方式定义服务操作期间会发生的错误。</span><span class="sxs-lookup"><span data-stu-id="f0436-122">Fault contracts allow you to define the errors that can occur during service operation in a platform independent way.</span></span> <span data-ttu-id="f0436-123">默认情况下，所有从服务操作内引发的异常都将作为 <xref:System.ServiceModel.FaultException> 对象返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="f0436-123">By default all exceptions thrown from within a service operation will be returned to the client as a <xref:System.ServiceModel.FaultException> object.</span></span> <span data-ttu-id="f0436-124"><xref:System.ServiceModel.FaultException> 对象将包含很少的信息。</span><span class="sxs-lookup"><span data-stu-id="f0436-124">The <xref:System.ServiceModel.FaultException> object will contain very little information.</span></span> <span data-ttu-id="f0436-125">通过定义错误协定并作为 <xref:System.ServiceModel.FaultException%601> 返回错误，可以控制发送到客户端的信息。</span><span class="sxs-lookup"><span data-stu-id="f0436-125">You can control the information sent to the client by defining a fault contract and returning the error as a <xref:System.ServiceModel.FaultException%601>.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="f0436-126">[指定和处理在协定和服务中的错误](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)。</span><span class="sxs-lookup"><span data-stu-id="f0436-126"> [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
## <a name="ierrorhandler"></a><span data-ttu-id="f0436-127">IErrorHandler</span><span class="sxs-lookup"><span data-stu-id="f0436-127">IErrorHandler</span></span>  
 <span data-ttu-id="f0436-128">利用 <xref:System.ServiceModel.Dispatcher.IErrorHandler> 接口，您可以对 WCF 应用程序响应错误的方式进行更多的控制。</span><span class="sxs-lookup"><span data-stu-id="f0436-128">The <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface allows you more control over how your WCF application responds to errors.</span></span>  <span data-ttu-id="f0436-129">您可以完全控制返回到客户端的故障消息，还可以执行自定义错误处理，例如日志记录。</span><span class="sxs-lookup"><span data-stu-id="f0436-129">It gives you full control over the fault message that is returned to the client and allows you to perform custom error processing such as logging.</span></span>  [!INCLUDE[crdefault](../../../includes/crabout-md.md)]<span data-ttu-id="f0436-130"><xref:System.ServiceModel.Dispatcher.IErrorHandler>和[扩展对错误处理和报告的控制](../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md)</span><span class="sxs-lookup"><span data-stu-id="f0436-130"> <xref:System.ServiceModel.Dispatcher.IErrorHandler> and [Extending Control Over Error Handling and Reporting](../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md)</span></span>  
  
## <a name="servicehost-events"></a><span data-ttu-id="f0436-131">ServiceHost 事件</span><span class="sxs-lookup"><span data-stu-id="f0436-131">ServiceHost Events</span></span>  
 <span data-ttu-id="f0436-132"><xref:System.ServiceModel.ServiceHost> 类承载服务，并定义处理错误可能需要的几个事件。</span><span class="sxs-lookup"><span data-stu-id="f0436-132">The <xref:System.ServiceModel.ServiceHost> class hosts services and defines several events that may be needed for handling errors.</span></span> <span data-ttu-id="f0436-133">例如:</span><span class="sxs-lookup"><span data-stu-id="f0436-133">For example:</span></span>  
  
1.  <!--zz <xref:System.ServiceModel.ServiceHost.Faulted>-->  `System.ServiceModel.ServiceHost.Faulted`
  
2. <!--zz  <xref:System.ServiceModel.ServiceHost.UnknownMessageReceived>  --> `System.ServiceModel.ServiceHost.UnknownMessageReceived`
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="f0436-134"> <xref:System.ServiceModel.ServiceHost></span><span class="sxs-lookup"><span data-stu-id="f0436-134"> <xref:System.ServiceModel.ServiceHost></span></span>
