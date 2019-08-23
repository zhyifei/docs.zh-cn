---
title: <soapProcessing>
ms.date: 03/30/2017
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
ms.openlocfilehash: 678b1f71ac15d3ad30df28cec5abbe403fb08c95
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937053"
---
# <a name="soapprocessing"></a><span data-ttu-id="6afcd-101">\<soapProcessing></span><span class="sxs-lookup"><span data-stu-id="6afcd-101">\<soapProcessing></span></span>

<span data-ttu-id="6afcd-102">定义用于封送不同绑定类型和消息版本之间消息的客户端终结点行为。</span><span class="sxs-lookup"><span data-stu-id="6afcd-102">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>

<span data-ttu-id="6afcd-103">**\<system.ServiceModel>**  </span><span class="sxs-lookup"><span data-stu-id="6afcd-103">**\<system.ServiceModel>** </span></span>  
<span data-ttu-id="6afcd-104">&nbsp;&nbsp; **\<behaviors>**  </span><span class="sxs-lookup"><span data-stu-id="6afcd-104">&nbsp;&nbsp;**\<behaviors>** </span></span>  
<span data-ttu-id="6afcd-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<endpointBehaviors>**  </span><span class="sxs-lookup"><span data-stu-id="6afcd-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointBehaviors>** </span></span>  
<span data-ttu-id="6afcd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<behavior>**  </span><span class="sxs-lookup"><span data-stu-id="6afcd-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>** </span></span>  
<span data-ttu-id="6afcd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<soapProcessing>**</span><span class="sxs-lookup"><span data-stu-id="6afcd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="6afcd-108">语法</span><span class="sxs-lookup"><span data-stu-id="6afcd-108">Syntax</span></span>  
  
```xml  
<soapProcessing processMessages="true|false" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6afcd-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6afcd-109">Attributes and elements</span></span>  
  
<span data-ttu-id="6afcd-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6afcd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6afcd-111">特性</span><span class="sxs-lookup"><span data-stu-id="6afcd-111">Attributes</span></span>  
  
|                   | <span data-ttu-id="6afcd-112">描述</span><span class="sxs-lookup"><span data-stu-id="6afcd-112">Description</span></span> |
| ----------------- | ----------- |
| `processMessages` | <span data-ttu-id="6afcd-113">一个布尔值，指定是否应封送 SOAP 消息版本之间的消息。</span><span class="sxs-lookup"><span data-stu-id="6afcd-113">A Boolean value that specifies whether messages should be marshaled between SOAP message versions.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="6afcd-114">子元素</span><span class="sxs-lookup"><span data-stu-id="6afcd-114">Child elements</span></span>

<span data-ttu-id="6afcd-115">无</span><span class="sxs-lookup"><span data-stu-id="6afcd-115">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6afcd-116">父元素</span><span class="sxs-lookup"><span data-stu-id="6afcd-116">Parent elements</span></span>

|     | <span data-ttu-id="6afcd-117">描述</span><span class="sxs-lookup"><span data-stu-id="6afcd-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6afcd-118"> **\<behavior>** </span><span class="sxs-lookup"><span data-stu-id="6afcd-118">**\<behavior>**</span></span>](behavior-of-endpointbehaviors.md) | <span data-ttu-id="6afcd-119">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="6afcd-119">Specifies an endpoint behavior.</span></span> |

## <a name="remarks"></a><span data-ttu-id="6afcd-120">备注</span><span class="sxs-lookup"><span data-stu-id="6afcd-120">Remarks</span></span>

<span data-ttu-id="6afcd-121">SOAP 处理是指在各消息版本之间转换消息的过程。</span><span class="sxs-lookup"><span data-stu-id="6afcd-121">SOAP processing is the process where messages are converted between message versions.</span></span>

<span data-ttu-id="6afcd-122">Windows Communication Foundation (WCF) 路由服务可以将消息从一个协议转换为另一个协议。</span><span class="sxs-lookup"><span data-stu-id="6afcd-122">The Windows Communication Foundation (WCF) Routing Service can convert messages from one protocol to another.</span></span> <span data-ttu-id="6afcd-123">如果传入消息和传出消息的版本不相同，则会创建一条具有正确版本的新消息。</span><span class="sxs-lookup"><span data-stu-id="6afcd-123">If the incoming and outgoing Message Versions are different, a new message of the correct version is created.</span></span> <span data-ttu-id="6afcd-124">通过构造新的 WCF 消息（该消息包含传入 WCF 消息的正文部分和相关标头）来完成对一个 <xref:System.ServiceModel.Channels.MessageVersion> 到另一个  的消息的处理。</span><span class="sxs-lookup"><span data-stu-id="6afcd-124">Processing messages from one <xref:System.ServiceModel.Channels.MessageVersion> to another is accomplished by constructing a new WCF message that contains the body part and relevant headers from the incoming WCF message.</span></span> <span data-ttu-id="6afcd-125">在构造新的 WCF 消息的过程中，不会使用特定于寻址的标头或在路由器级别理解的标头，这是因为这些标头要么具有不同的版本（如果为寻址标头），要么已作为客户端和路由器之间的通信的一部分处理。</span><span class="sxs-lookup"><span data-stu-id="6afcd-125">Headers that are specific to addressing, or that are understood at the router level, are not used during construction of the new WCF message because these headers are either of a different version (in the case of addressing headers) or have been processed as part of the communication between the client and the router.</span></span>

<span data-ttu-id="6afcd-126">是否将一个标头置于出站消息内由此标头在通过传入通道层时是否已标记为已理解来决定。</span><span class="sxs-lookup"><span data-stu-id="6afcd-126">Whether a header is placed in the outbound message is determined by whether or not it was marked as understood as it passed through the incoming channel layer.</span></span> <span data-ttu-id="6afcd-127">不会移除不理解的标头（如自定义标头），并且会将此标头复制到出站消息中，以通过路由服务。</span><span class="sxs-lookup"><span data-stu-id="6afcd-127">Headers that are not understood (such as custom headers) are not removed and so pass through the routing service by being copied to the outbound message.</span></span> <span data-ttu-id="6afcd-128">系统会将消息正文复制到出站消息中，</span><span class="sxs-lookup"><span data-stu-id="6afcd-128">The body of the message is copied to the outbound message.</span></span> <span data-ttu-id="6afcd-129">然后将此消息外发到出站通道，此时将创建和添加特定于该通信协议/传输的所有标头和其他信封数据。</span><span class="sxs-lookup"><span data-stu-id="6afcd-129">The message is then sent out the outbound channel, at which point all of the headers and other envelope data specific to that communication protocol/transport will be created and added.</span></span>

<span data-ttu-id="6afcd-130">当指定了 SOAP 处理行为时，将执行此类处理步骤。</span><span class="sxs-lookup"><span data-stu-id="6afcd-130">Such processing steps take place when the SOAP processing behavior is specified.</span></span> <span data-ttu-id="6afcd-131">[此\<soapProcessingExtension >](soapprocessing.md)行为是在启动路由服务时应用于所有客户端 (传出) 终结点的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="6afcd-131">This [\<soapProcessingExtension>](soapprocessing.md) behavior is an endpoint behavior that is applied to all client (outgoing) endpoints when the Routing Service starts up.</span></span> <span data-ttu-id="6afcd-132">默认情况下, [ \<路由 >](routing-of-servicebehavior.md)行为将为每个客户端终结点`processMessages`创建并`true`附加一个新[ \<的 soapProcessingExtension >](soapprocessing.md)行为, 并将设置为。</span><span class="sxs-lookup"><span data-stu-id="6afcd-132">default, the [\<routing>](routing-of-servicebehavior.md) behavior creates and attaches a new [\<soapProcessingExtension>](soapprocessing.md) behavior with `processMessages` set to `true` for each client endpoint.</span></span> <span data-ttu-id="6afcd-133">如果您具有路由服务无法理解的协议，或者希望重写默认处理行为，则可以针对整个路由服务或仅针对特定终结点禁用 SOAP 处理。</span><span class="sxs-lookup"><span data-stu-id="6afcd-133">If you have a protocol that the Routing Service does not understand, or wish to override the default processing behavior, you can disable SOAP processing either for the entire Routing Service or just for particular endpoints.</span></span>  <span data-ttu-id="6afcd-134">若要对所有终结点上的整个路由服务禁用 SOAP 处理, `soapProcessing`请将[ \<路由 >](routing-of-servicebehavior.md)行为的特性`false`设置为。</span><span class="sxs-lookup"><span data-stu-id="6afcd-134">To disable SOAP processing for the entire routing service on all endpoints, set the `soapProcessing` attribute of the [\<routing>](routing-of-servicebehavior.md) behavior to `false`.</span></span> <span data-ttu-id="6afcd-135">若要针对特定终结点禁用 SOAP 处理，请使用此行为，并将其 `processMessages` 特性设置为 `false`，然后将此行为附加到不希望运行默认处理代码的终结点。</span><span class="sxs-lookup"><span data-stu-id="6afcd-135">To turn off SOAP processing for a particular endpoint, use this behavior and set its `processMessages` attribute to `false`, then attach this behavior to the endpoint you do not want the default processing code to run at.</span></span>  <span data-ttu-id="6afcd-136">当[路由 > 行为设置路由服务时, 它将跳过重新应用终结点行为, 因为已存在一个终结点行为。 \<](routing-of-servicebehavior.md)</span><span class="sxs-lookup"><span data-stu-id="6afcd-136">When the [\<routing>](routing-of-servicebehavior.md) behavior sets up the Routing Service, it will skip reapplying the endpoint behavior since one already exists.</span></span>
