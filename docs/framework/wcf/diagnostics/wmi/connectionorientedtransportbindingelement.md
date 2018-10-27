---
title: ConnectionOrientedTransportBindingElement
ms.date: 03/30/2017
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
ms.openlocfilehash: 49f030c05f02280d483ac2a836cbe75716b7b5cc
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185049"
---
# <a name="connectionorientedtransportbindingelement"></a><span data-ttu-id="c0a50-102">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="c0a50-102">ConnectionOrientedTransportBindingElement</span></span>
<span data-ttu-id="c0a50-103">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="c0a50-103">ConnectionOrientedTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0a50-104">语法</span><span class="sxs-lookup"><span data-stu-id="c0a50-104">Syntax</span></span>  
  
```csharp
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c0a50-105">方法</span><span class="sxs-lookup"><span data-stu-id="c0a50-105">Methods</span></span>  
 <span data-ttu-id="c0a50-106">ConnectionOrientedTransportBindingElement 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="c0a50-106">The ConnectionOrientedTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c0a50-107">属性</span><span class="sxs-lookup"><span data-stu-id="c0a50-107">Properties</span></span>  
 <span data-ttu-id="c0a50-108">ConnectionOrientedTransportBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="c0a50-108">The ConnectionOrientedTransportBindingElement class has the following properties:</span></span>  
  
### <a name="channelinitializationtimeout"></a><span data-ttu-id="c0a50-109">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="c0a50-109">ChannelInitializationTimeout</span></span>  
 <span data-ttu-id="c0a50-110">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="c0a50-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="c0a50-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c0a50-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0a50-112">指定在超时前可用于完成通道初始化的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="c0a50-112">The timespan that specifies how long the channel initialization has to complete before timing out.</span></span>  
  
### <a name="connectionbuffersize"></a><span data-ttu-id="c0a50-113">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="c0a50-113">ConnectionBufferSize</span></span>  
 <span data-ttu-id="c0a50-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="c0a50-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="c0a50-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c0a50-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0a50-116">用于从客户端或服务传输网络上的序列化消息块的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="c0a50-116">The size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="c0a50-117">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="c0a50-117">HostNameComparisonMode</span></span>  
 <span data-ttu-id="c0a50-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="c0a50-118">Data type: string</span></span>  
  
 <span data-ttu-id="c0a50-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c0a50-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0a50-120">一个值，指示在对 URI 进行匹配时，是否使用主机名来访问服务。</span><span class="sxs-lookup"><span data-stu-id="c0a50-120">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="c0a50-121">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="c0a50-121">MaxBufferSize</span></span>  
 <span data-ttu-id="c0a50-122">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="c0a50-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="c0a50-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c0a50-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0a50-124">要使用的缓冲区最大大小。</span><span class="sxs-lookup"><span data-stu-id="c0a50-124">The maximum size of the buffer to use.</span></span>  
  
### <a name="maxoutputdelay"></a><span data-ttu-id="c0a50-125">MaxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="c0a50-125">MaxOutputDelay</span></span>  
 <span data-ttu-id="c0a50-126">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="c0a50-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="c0a50-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c0a50-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0a50-128">消息块或完整消息在发出之前可以在内存中保持缓冲的最大时间间隔。</span><span class="sxs-lookup"><span data-stu-id="c0a50-128">The maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>  
  
### <a name="maxpendingaccepts"></a><span data-ttu-id="c0a50-129">MaxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="c0a50-129">MaxPendingAccepts</span></span>  
 <span data-ttu-id="c0a50-130">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="c0a50-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="c0a50-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c0a50-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0a50-132">可用于处理服务上的传入连接的最大挂起异步接受线程数。</span><span class="sxs-lookup"><span data-stu-id="c0a50-132">The maximum number of pending asynchronous accept threads that are available for processing incoming connections on the service.</span></span>  
  
### <a name="maxpendingconnections"></a><span data-ttu-id="c0a50-133">MaxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="c0a50-133">MaxPendingConnections</span></span>  
 <span data-ttu-id="c0a50-134">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="c0a50-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="c0a50-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c0a50-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0a50-136">最大挂起连接数。</span><span class="sxs-lookup"><span data-stu-id="c0a50-136">The maximum number of pending connections.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="c0a50-137">TransferMode</span><span class="sxs-lookup"><span data-stu-id="c0a50-137">TransferMode</span></span>  
 <span data-ttu-id="c0a50-138">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="c0a50-138">Data type: string</span></span>  
  
 <span data-ttu-id="c0a50-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c0a50-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c0a50-140">一个值，指定通过面向连接的传输对消息进行缓冲还是流处理。</span><span class="sxs-lookup"><span data-stu-id="c0a50-140">A value that specifies whether the messages are buffered or streamed with the connection-oriented transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0a50-141">要求</span><span class="sxs-lookup"><span data-stu-id="c0a50-141">Requirements</span></span>  
  
|<span data-ttu-id="c0a50-142">MOF</span><span class="sxs-lookup"><span data-stu-id="c0a50-142">MOF</span></span>|<span data-ttu-id="c0a50-143">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="c0a50-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c0a50-144">命名空间</span><span class="sxs-lookup"><span data-stu-id="c0a50-144">Namespace</span></span>|<span data-ttu-id="c0a50-145">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="c0a50-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0a50-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0a50-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
