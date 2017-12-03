---
title: '&lt;soapProcessing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e83bfc0f868526ad5366032f08956a6c14a1056
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltsoapprocessinggt"></a><span data-ttu-id="8db87-102">&lt;soapProcessing&gt;</span><span class="sxs-lookup"><span data-stu-id="8db87-102">&lt;soapProcessing&gt;</span></span>

<span data-ttu-id="8db87-103">定义用于封送不同绑定类型和消息版本之间消息的客户端终结点行为。</span><span class="sxs-lookup"><span data-stu-id="8db87-103">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>

<span data-ttu-id="8db87-104">**\<系统。ServiceModel >** </span><span class="sxs-lookup"><span data-stu-id="8db87-104">**\<system.ServiceModel>** </span></span>  
<span data-ttu-id="8db87-105">&nbsp;&nbsp;**\<行为 >** </span><span class="sxs-lookup"><span data-stu-id="8db87-105">&nbsp;&nbsp;**\<behaviors>** </span></span>  
<span data-ttu-id="8db87-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointBehaviors >** </span><span class="sxs-lookup"><span data-stu-id="8db87-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointBehaviors>** </span></span>  
<span data-ttu-id="8db87-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<行为 >** </span><span class="sxs-lookup"><span data-stu-id="8db87-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>** </span></span>  
<span data-ttu-id="8db87-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing >**</span><span class="sxs-lookup"><span data-stu-id="8db87-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8db87-109">语法</span><span class="sxs-lookup"><span data-stu-id="8db87-109">Syntax</span></span>

```xml
<soapProcessing processMessages="true|false" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8db87-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8db87-110">Attributes and elements</span></span>

<span data-ttu-id="8db87-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8db87-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8db87-112">特性</span><span class="sxs-lookup"><span data-stu-id="8db87-112">Attributes</span></span>

|                   | <span data-ttu-id="8db87-113">描述</span><span class="sxs-lookup"><span data-stu-id="8db87-113">Description</span></span> |
| ----------------- | ----------- |
| `processMessages` | <span data-ttu-id="8db87-114">一个布尔值，指定是否应封送 SOAP 消息版本之间的消息。</span><span class="sxs-lookup"><span data-stu-id="8db87-114">A Boolean value that specifies whether messages should be marshaled between SOAP message versions.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="8db87-115">子元素</span><span class="sxs-lookup"><span data-stu-id="8db87-115">Child elements</span></span>

<span data-ttu-id="8db87-116">无</span><span class="sxs-lookup"><span data-stu-id="8db87-116">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8db87-117">父元素</span><span class="sxs-lookup"><span data-stu-id="8db87-117">Parent elements</span></span>

|     | <span data-ttu-id="8db87-118">描述</span><span class="sxs-lookup"><span data-stu-id="8db87-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8db87-119">**\<行为 >**</span><span class="sxs-lookup"><span data-stu-id="8db87-119">**\<behavior>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) | <span data-ttu-id="8db87-120">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="8db87-120">Specifies an endpoint behavior.</span></span> |

## <a name="remarks"></a><span data-ttu-id="8db87-121">备注</span><span class="sxs-lookup"><span data-stu-id="8db87-121">Remarks</span></span>

<span data-ttu-id="8db87-122">SOAP 处理是指在各消息版本之间转换消息的过程。</span><span class="sxs-lookup"><span data-stu-id="8db87-122">SOAP processing is the process where messages are converted between message versions.</span></span>

<span data-ttu-id="8db87-123">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 路由服务可以将消息从一个协议转换为另一个协议。</span><span class="sxs-lookup"><span data-stu-id="8db87-123">The [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Routing Service can convert messages from one protocol to another.</span></span> <span data-ttu-id="8db87-124">如果传入消息和传出消息的版本不相同，则会创建一条具有正确版本的新消息。</span><span class="sxs-lookup"><span data-stu-id="8db87-124">If the incoming and outgoing Message Versions are different, a new message of the correct version is created.</span></span> <span data-ttu-id="8db87-125">处理消息从一个<!--zz <xref:System.ServiceModel.Channel.MessageVersion> -->`MessageVersion`到另一个通过构造一个新实现[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]包含正文部分和相关标头从传入消息[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]消息。</span><span class="sxs-lookup"><span data-stu-id="8db87-125">Processing messages from one <!--zz <xref:System.ServiceModel.Channel.MessageVersion> --> `MessageVersion`  to another is accomplished by constructing a new [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] message that contains the body part and relevant headers from the incoming [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] message.</span></span> <span data-ttu-id="8db87-126">在构造新的 WCF 消息的过程中，不会使用特定于寻址的标头或在路由器级别理解的标头，这是因为这些标头要么具有不同的版本（如果为寻址标头），要么已作为客户端和路由器之间的通信的一部分处理。</span><span class="sxs-lookup"><span data-stu-id="8db87-126">Headers that are specific to addressing, or that are understood at the router level, are not used during construction of the new WCF message because these headers are either of a different version (in the case of addressing headers) or have been processed as part of the communication between the client and the router.</span></span>

<span data-ttu-id="8db87-127">是否将一个标头置于出站消息内由此标头在通过传入通道层时是否已标记为已理解来决定。</span><span class="sxs-lookup"><span data-stu-id="8db87-127">Whether a header is placed in the outbound message is determined by whether or not it was marked as understood as it passed through the incoming channel layer.</span></span> <span data-ttu-id="8db87-128">不会移除不理解的标头（如自定义标头），并且会将此标头复制到出站消息中，以通过路由服务。</span><span class="sxs-lookup"><span data-stu-id="8db87-128">Headers that are not understood (such as custom headers) are not removed and so pass through the routing service by being copied to the outbound message.</span></span> <span data-ttu-id="8db87-129">系统会将消息正文复制到出站消息中，</span><span class="sxs-lookup"><span data-stu-id="8db87-129">The body of the message is copied to the outbound message.</span></span> <span data-ttu-id="8db87-130">然后将此消息外发到出站通道，此时将创建和添加特定于该通信协议/传输的所有标头和其他信封数据。</span><span class="sxs-lookup"><span data-stu-id="8db87-130">The message is then sent out the outbound channel, at which point all of the headers and other envelope data specific to that communication protocol/transport will be created and added.</span></span>

<span data-ttu-id="8db87-131">当指定了 SOAP 处理行为时，将执行此类处理步骤。</span><span class="sxs-lookup"><span data-stu-id="8db87-131">Such processing steps take place when the SOAP processing behavior is specified.</span></span> <span data-ttu-id="8db87-132">这[ \<soapProcessingExtension >](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md)行为是在路由服务启动时应用于所有客户端 （传出） 终结点的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="8db87-132">This [\<soapProcessingExtension>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) behavior is an endpoint behavior that is applied to all client (outgoing) endpoints when the Routing Service starts up.</span></span> <span data-ttu-id="8db87-133">默认情况下， [\<路由 >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)行为创建并附加一个新[ \<soapProcessingExtension >](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md)行为`processMessages`设置为`true`每个客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="8db87-133">default, the [\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) behavior creates and attaches a new [\<soapProcessingExtension>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) behavior with `processMessages` set to `true` for each client endpoint.</span></span> <span data-ttu-id="8db87-134">如果您具有路由服务无法理解的协议，或者希望重写默认处理行为，则可以针对整个路由服务或仅针对特定终结点禁用 SOAP 处理。</span><span class="sxs-lookup"><span data-stu-id="8db87-134">If you have a protocol that the Routing Service does not understand, or wish to override the default processing behavior, you can disable SOAP processing either for the entire Routing Service or just for particular endpoints.</span></span>  <span data-ttu-id="8db87-135">若要禁用 SOAP 处理所有终结点上的整个路由服务，设置`soapProcessing`属性[\<路由 >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)到行为`false`。</span><span class="sxs-lookup"><span data-stu-id="8db87-135">To disable SOAP processing for the entire routing service on all endpoints, set the `soapProcessing` attribute of the [\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) behavior to `false`.</span></span> <span data-ttu-id="8db87-136">若要针对特定终结点禁用 SOAP 处理，请使用此行为，并将其 `processMessages` 特性设置为 `false`，然后将此行为附加到不希望运行默认处理代码的终结点。</span><span class="sxs-lookup"><span data-stu-id="8db87-136">To turn off SOAP processing for a particular endpoint, use this behavior and set its `processMessages` attribute to `false`, then attach this behavior to the endpoint you do not want the default processing code to run at.</span></span>  <span data-ttu-id="8db87-137">当[\<路由 >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)行为将路由服务设置，则将跳过重新应用终结点行为，因为其中一个已存在。</span><span class="sxs-lookup"><span data-stu-id="8db87-137">When the [\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) behavior sets up the Routing Service, it will skip reapplying the endpoint behavior since one already exists.</span></span>
