---
title: "使用字节流编码器编码二进制对象"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 020ee981-c889-4b12-a3ea-91823ef46444
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: acf9d2ace66702c5f0bc522d97ae92869891a38b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="encoding-binary-objects-with-bytestream-encoder"></a><span data-ttu-id="a3a9a-102">使用字节流编码器编码二进制对象</span><span class="sxs-lookup"><span data-stu-id="a3a9a-102">Encoding Binary Objects with ByteStream Encoder</span></span>
<span data-ttu-id="a3a9a-103">使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 配置通过 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement> 发送和接收原始二进制数据。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-103">Sending and receiving raw binary data with [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is configured using <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>.</span></span>  
  
## <a name="byte-stream-message-encoder-architecture"></a><span data-ttu-id="a3a9a-104">字节流消息编码器体系结构</span><span class="sxs-lookup"><span data-stu-id="a3a9a-104">Byte Stream Message Encoder Architecture</span></span>  
 <span data-ttu-id="a3a9a-105">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 使用的二进制消息编码器没有功能可用于处理、验证或标识消息中的基础二进制数据。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-105">The binary message encoder used by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] has no facility for processing, validating, or identifying the underlying binary data in the message.</span></span> <span data-ttu-id="a3a9a-106">数据包会编码为 XML 进行发送、接收和解码。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-106">The data package is encoded into XML, sent, received, and decoded.</span></span> <span data-ttu-id="a3a9a-107">编码器在数据传递到传输之后但在消息发送到消息队列之前处理数据。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-107">The encoder processes the data after being passed to the transport and before the message is sent to the message queue.</span></span> <span data-ttu-id="a3a9a-108">在功能上，二进制编码器将消息数据包装在 `<binary>` 元素中进行发送，并在收到消息之后删除元素。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-108">Functionally, the binary encoder wraps the message data in `<binary>` elements for sending and removes the elements after the message is received.</span></span>  
  
## <a name="using-the-byte-stream-message-encoder"></a><span data-ttu-id="a3a9a-109">使用字节流消息编码器</span><span class="sxs-lookup"><span data-stu-id="a3a9a-109">Using the Byte Stream Message Encoder</span></span>  
 <span data-ttu-id="a3a9a-110">下面的示例演示实现字节流消息编码器的服务协定。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-110">The following example shows a service contract that implements the byte stream message encoder.</span></span>  
  
```csharp  
[OperationContract]  
Void Myfunction(Stream stream);  
```  
  
 <span data-ttu-id="a3a9a-111">下面的示例演示调用的服务。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-111">The following example shows the service being invoked.</span></span>  
  
```csharp  
proxy.MyFunction(stream);  
```  
  
 <span data-ttu-id="a3a9a-112">使用实现消息基础结构（如路由器）的服务时，将直接处理消息，而不进行检查、验证或通过其他方式与消息交互，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-112">In the case of using a service that implements a message infrastructure (such as a router), the message is processed without inspecting, validating, or otherwise interacting with the message, as shown in the following example.</span></span>  
  
```csharp  
[OperationContract]  
void ProcessMessage(Message message) ;  
```  
  
## <a name="scenarios"></a><span data-ttu-id="a3a9a-113">方案</span><span class="sxs-lookup"><span data-stu-id="a3a9a-113">Scenarios</span></span>  
 <span data-ttu-id="a3a9a-114">字节流编码器可在以下方案中使用。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-114">The Byte Stream Encoder is useful in the following scenarios.</span></span>  
  
-   <span data-ttu-id="a3a9a-115">在使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的计算机之间传输 JPEG 图像。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-115">Transferring a JPEG image between computers using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="a3a9a-116">在此方案中，图像会通过传输从外部源到达，而发送的数据会是组成图像的原始字节。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-116">In this scenario, the image will arrive through the transport from an outside source, and the data sent will be the raw bytes that make up the image.</span></span> <span data-ttu-id="a3a9a-117">某个服务会接收二进制数据并显示图像。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-117">A service will receive the binary data and display the image.</span></span>  
  
-   <span data-ttu-id="a3a9a-118">从消息队列读出信息并进行处理。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-118">Reading information out of a message queue and processing it.</span></span> <span data-ttu-id="a3a9a-119">消息会从消息队列管理器中读取，并在消息队列通道中向上传递以进行处理。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-119">The message will be read from a message queue manager, and passed up the message queue channel to be handled.</span></span> <span data-ttu-id="a3a9a-120">消息队列通道会充当 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 通道堆栈中的队列管理器。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-120">The message queue channel will act as a queue manager in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] channel stack.</span></span>  
  
 <span data-ttu-id="a3a9a-121">对于通过消息队列通道发送消息，发送方无法控制从队列管理器接收的字节。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-121">In the case of sending a message over a message queue channel, the sender has no control over the bytes received from the queue manager.</span></span> <span data-ttu-id="a3a9a-122">如果接收进程无法读取原始字节，则消息会以错误格式接收，不会进行处理；假定接收进程能够将接收的字节转换为可用格式。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-122">If the receiving process has no capability to read raw bytes, the message will be received as badly formatted and will not be processed; it is assumed that the receiving process will have the capability of translating the received bytes back into a usable format.</span></span>
