---
title: "自定义消息格式化程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c07435f3-5214-4791-8961-2c2b61306d71
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 01998d0ac732f63f6771c47bfc76a8207a5531f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="custom-message-formatters"></a><span data-ttu-id="b9fb3-102">自定义消息格式化程序</span><span class="sxs-lookup"><span data-stu-id="b9fb3-102">Custom Message Formatters</span></span>
<span data-ttu-id="b9fb3-103">消息内容通常为 XML 格式，该格式通常不便于在应用程序中使用。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-103">The content in a message is often in the form of XML, which is usually not a convenient format for an application.</span></span> <span data-ttu-id="b9fb3-104">应用程序操作对象，并且获取和设置其属性。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-104">Applications manipulate objects, getting and setting their properties.</span></span> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="b9fb3-105">使用*数据协定*要转换<xref:System.ServiceModel.Channels.Message>到应用程序易于处理的对象的对象。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-105"> uses the *Data Contract* to convert a <xref:System.ServiceModel.Channels.Message> object into an object easily handled by an application.</span></span> <span data-ttu-id="b9fb3-106">我们将这些过程称为序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-106">These processes are called serialization and deserialization.</span></span> <span data-ttu-id="b9fb3-107">请注意，这些词同样用于描述传输层对消息连网格式所进行的序列化和反序列化，这是一个不相关的过程。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-107">Note that these same terms are used to describe the serialization and deserialization done by the transport layer to and from the message wire format, which is an unrelated process.</span></span>  
  
 <span data-ttu-id="b9fb3-108">如果需要实现通过数据协定无法完成的消息和对象之间的专用转换，则可以使用自定义消息格式化程序。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-108">You can use a custom message formatter if you need to implement a specialized conversion between messages and objects that you cannot accomplish by means of a Data Contract.</span></span> <span data-ttu-id="b9fb3-109">方法是修改或扩展客户端或服务上的特定协定操作的执行行为。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-109">Do this by modifying or extending the execution behavior of a specific contract operation on a client or a service.</span></span>  
  
## <a name="custom-message-formatters-on-the-client"></a><span data-ttu-id="b9fb3-110">自定义客户端上的消息格式化程序</span><span class="sxs-lookup"><span data-stu-id="b9fb3-110">Custom Message Formatters on the Client</span></span>  
 <span data-ttu-id="b9fb3-111"><xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> 接口定义用于控制客户端应用程序的消息与对象之间的转换方法。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-111">The <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> interface defines methods that are used to control the conversion of messages into objects and objects into messages for client applications.</span></span>  
  
 <span data-ttu-id="b9fb3-112">您必须实现此接口。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-112">You must implement this interface.</span></span> <span data-ttu-id="b9fb3-113">首先重写 <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.DeserializeReply%2A> 方法以反序列化消息。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-113">First override the <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.DeserializeReply%2A> method to deserialize a message.</span></span> <span data-ttu-id="b9fb3-114">在接收传入消息后，将消息调度到客户端操作之前调用此方法。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-114">This method is called after an incoming message is received, but before it is dispatched to the client operation.</span></span>  
  
 <span data-ttu-id="b9fb3-115">然后，重写 <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.SerializeRequest%2A> 方法以序列化对象。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-115">Next, override the <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.SerializeRequest%2A> method to serialize an object.</span></span> <span data-ttu-id="b9fb3-116">在发送传出消息前调用此方法。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-116">This method is called prior to sending an outgoing message.</span></span>  
  
 <span data-ttu-id="b9fb3-117">若要将自定义格式化程序插入服务应用程序，请使用操作行为将 <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> 对象分配给 <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-117">To insert the custom formatter into the service application, assign the <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> object to the <xref:System.ServiceModel.Dispatcher.ClientOperation.Formatter%2A> property using an operation behavior.</span></span> <span data-ttu-id="b9fb3-118">有关各种行为的信息，请参阅[配置和扩展的运行时带有行为](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-118">For information about behaviors, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="custom-message-formatters-on-the-service"></a><span data-ttu-id="b9fb3-119">自定义服务上的消息格式化程序</span><span class="sxs-lookup"><span data-stu-id="b9fb3-119">Custom Message Formatters on the Service</span></span>  
 <span data-ttu-id="b9fb3-120"><xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> 接口定义将服务应用程序中的 <xref:System.ServiceModel.Channels.Message> 对象转换为操作参数并将参数转换为 <xref:System.ServiceModel.Channels.Message> 对象的方法。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-120">The <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> interface defines methods that convert a <xref:System.ServiceModel.Channels.Message> object into parameters for an operation and from parameters into a <xref:System.ServiceModel.Channels.Message> object in a service application.</span></span>  
  
 <span data-ttu-id="b9fb3-121">您必须实现此接口。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-121">You must implement this interface.</span></span> <span data-ttu-id="b9fb3-122">首先重写 <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.DeserializeReply%2A> 方法以反序列化消息。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-122">First override the <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.DeserializeReply%2A> method to deserialize a message.</span></span> <span data-ttu-id="b9fb3-123">在接收传入消息后，将消息调度到客户端操作之前调用此方法。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-123">This method is called after an incoming message is received, but before it is dispatched to the client operation.</span></span>  
  
 <span data-ttu-id="b9fb3-124">然后，重写 <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.SerializeRequest%2A> 方法以序列化对象。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-124">Next, override the <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter.SerializeRequest%2A> method to serialize an object.</span></span> <span data-ttu-id="b9fb3-125">在发送传出消息前调用此方法。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-125">This method is called prior to sending an outgoing message.</span></span>  
  
 <span data-ttu-id="b9fb3-126">若要将自定义格式化程序插入服务应用程序，请使用操作行为将 <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> 对象分配给 <xref:System.ServiceModel.Dispatcher.DispatchOperation.Formatter%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-126">To insert the custom formatter into the service application, assign the <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> object to the <xref:System.ServiceModel.Dispatcher.DispatchOperation.Formatter%2A> property using an operation behavior.</span></span> <span data-ttu-id="b9fb3-127">有关各种行为的信息，请参阅[配置和扩展的运行时带有行为](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)。</span><span class="sxs-lookup"><span data-stu-id="b9fb3-127">For information about behaviors, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9fb3-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9fb3-128">See Also</span></span>  
 <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>  
 <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>  
 [<span data-ttu-id="b9fb3-129">配置和扩展的运行时带有行为</span><span class="sxs-lookup"><span data-stu-id="b9fb3-129">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
