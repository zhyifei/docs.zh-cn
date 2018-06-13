---
title: 使用字节流编码器编码二进制对象
ms.date: 03/30/2017
ms.assetid: 020ee981-c889-4b12-a3ea-91823ef46444
ms.openlocfilehash: 9619fdf6979833c30159e1ea02b3f8d6b98a6629
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489477"
---
# <a name="encoding-binary-objects-with-bytestream-encoder"></a><span data-ttu-id="46ef7-102">使用字节流编码器编码二进制对象</span><span class="sxs-lookup"><span data-stu-id="46ef7-102">Encoding Binary Objects with ByteStream Encoder</span></span>
<span data-ttu-id="46ef7-103">使用配置发送和接收原始二进制数据与 Windows Communication Foundation (WCF) <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="46ef7-103">Sending and receiving raw binary data with Windows Communication Foundation (WCF) is configured using <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>.</span></span>  
  
## <a name="byte-stream-message-encoder-architecture"></a><span data-ttu-id="46ef7-104">字节流消息编码器体系结构</span><span class="sxs-lookup"><span data-stu-id="46ef7-104">Byte Stream Message Encoder Architecture</span></span>  
 <span data-ttu-id="46ef7-105">WCF 使用二进制消息编码器有没有功能可用于处理、 验证或标识消息中的基础二进制数据。</span><span class="sxs-lookup"><span data-stu-id="46ef7-105">The binary message encoder used by WCF has no facility for processing, validating, or identifying the underlying binary data in the message.</span></span> <span data-ttu-id="46ef7-106">数据包会编码为 XML 进行发送、接收和解码。</span><span class="sxs-lookup"><span data-stu-id="46ef7-106">The data package is encoded into XML, sent, received, and decoded.</span></span> <span data-ttu-id="46ef7-107">编码器在数据传递到传输之后但在消息发送到消息队列之前处理数据。</span><span class="sxs-lookup"><span data-stu-id="46ef7-107">The encoder processes the data after being passed to the transport and before the message is sent to the message queue.</span></span> <span data-ttu-id="46ef7-108">在功能上，二进制编码器将消息数据包装在 `<binary>` 元素中进行发送，并在收到消息之后删除元素。</span><span class="sxs-lookup"><span data-stu-id="46ef7-108">Functionally, the binary encoder wraps the message data in `<binary>` elements for sending and removes the elements after the message is received.</span></span>  
  
## <a name="using-the-byte-stream-message-encoder"></a><span data-ttu-id="46ef7-109">使用字节流消息编码器</span><span class="sxs-lookup"><span data-stu-id="46ef7-109">Using the Byte Stream Message Encoder</span></span>  
 <span data-ttu-id="46ef7-110">下面的示例演示实现字节流消息编码器的服务协定。</span><span class="sxs-lookup"><span data-stu-id="46ef7-110">The following example shows a service contract that implements the byte stream message encoder.</span></span>  
  
```csharp  
[OperationContract]  
Void Myfunction(Stream stream);  
```  
  
 <span data-ttu-id="46ef7-111">下面的示例演示调用的服务。</span><span class="sxs-lookup"><span data-stu-id="46ef7-111">The following example shows the service being invoked.</span></span>  
  
```csharp  
proxy.MyFunction(stream);  
```  
  
 <span data-ttu-id="46ef7-112">使用实现消息基础结构（如路由器）的服务时，将直接处理消息，而不进行检查、验证或通过其他方式与消息交互，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="46ef7-112">In the case of using a service that implements a message infrastructure (such as a router), the message is processed without inspecting, validating, or otherwise interacting with the message, as shown in the following example.</span></span>  
  
```csharp  
[OperationContract]  
void ProcessMessage(Message message) ;  
```  
  
## <a name="scenarios"></a><span data-ttu-id="46ef7-113">方案</span><span class="sxs-lookup"><span data-stu-id="46ef7-113">Scenarios</span></span>  
 <span data-ttu-id="46ef7-114">字节流编码器可在以下方案中使用。</span><span class="sxs-lookup"><span data-stu-id="46ef7-114">The Byte Stream Encoder is useful in the following scenarios.</span></span>  
  
-   <span data-ttu-id="46ef7-115">使用 WCF 的计算机之间传输 JPEG 图像。</span><span class="sxs-lookup"><span data-stu-id="46ef7-115">Transferring a JPEG image between computers using WCF.</span></span> <span data-ttu-id="46ef7-116">在此方案中，图像会通过传输从外部源到达，而发送的数据会是组成图像的原始字节。</span><span class="sxs-lookup"><span data-stu-id="46ef7-116">In this scenario, the image will arrive through the transport from an outside source, and the data sent will be the raw bytes that make up the image.</span></span> <span data-ttu-id="46ef7-117">某个服务会接收二进制数据并显示图像。</span><span class="sxs-lookup"><span data-stu-id="46ef7-117">A service will receive the binary data and display the image.</span></span>  
  
-   <span data-ttu-id="46ef7-118">从消息队列读出信息并进行处理。</span><span class="sxs-lookup"><span data-stu-id="46ef7-118">Reading information out of a message queue and processing it.</span></span> <span data-ttu-id="46ef7-119">消息会从消息队列管理器中读取，并在消息队列通道中向上传递以进行处理。</span><span class="sxs-lookup"><span data-stu-id="46ef7-119">The message will be read from a message queue manager, and passed up the message queue channel to be handled.</span></span> <span data-ttu-id="46ef7-120">消息队列通道会充当 WCF 通道堆栈中的队列管理器。</span><span class="sxs-lookup"><span data-stu-id="46ef7-120">The message queue channel will act as a queue manager in the WCF channel stack.</span></span>  
  
 <span data-ttu-id="46ef7-121">对于通过消息队列通道发送消息，发送方无法控制从队列管理器接收的字节。</span><span class="sxs-lookup"><span data-stu-id="46ef7-121">In the case of sending a message over a message queue channel, the sender has no control over the bytes received from the queue manager.</span></span> <span data-ttu-id="46ef7-122">如果接收进程无法读取原始字节，则消息会以错误格式接收，不会进行处理；假定接收进程能够将接收的字节转换为可用格式。</span><span class="sxs-lookup"><span data-stu-id="46ef7-122">If the receiving process has no capability to read raw bytes, the message will be received as badly formatted and will not be processed; it is assumed that the receiving process will have the capability of translating the received bytes back into a usable format.</span></span>
