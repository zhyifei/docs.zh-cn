---
title: <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: a68b44d7-7799-43a3-9e63-f07c782810a6
ms.openlocfilehash: a315ec508b378d1a3ba0189b0867c7b6b61e34d2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398320"
---
# <a name="netmsmqbinding"></a><span data-ttu-id="73bb7-101">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="73bb7-101">\<netMsmqBinding></span></span>
<span data-ttu-id="73bb7-102">定义适用于跨计算机通信的排队绑定。</span><span class="sxs-lookup"><span data-stu-id="73bb7-102">Defines a queued binding suitable for cross-machine communication.</span></span>  
  
<span data-ttu-id="73bb7-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="73bb7-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="73bb7-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="73bb7-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="73bb7-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="73bb7-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="73bb7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<netMsmqBinding >**</span><span class="sxs-lookup"><span data-stu-id="73bb7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netMsmqBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73bb7-107">语法</span><span class="sxs-lookup"><span data-stu-id="73bb7-107">Syntax</span></span>  
  
```xml  
<netMsmqBinding>
  <binding closeTimeout="TimeSpan"
           customDeadLetterQueue="Uri"
           deadLetterQueue="Uri"
           durable="Boolean"
           exactlyOnce="Boolean"
           maxBufferPoolSize="Integer"
           maxReceivedMessageSize="Integer"
           maxRetryCycles="Integer"
           name="String"
           openTimeout="TimeSpan"
           poisonMessageHandling="Disabled/EnabledIfSupported"
           queueTransferProtocol="Native/Srmp/SrmpSecure"
           receiveErrorHandling="Drop/Fault/Move/Reject"
           receiveTimeout="TimeSpan"
           receiveRetryCount="Integer"
           rejectAfterLastRetry="Boolean"
           retryCycleDelay="TimeSpan"
           sendTimeout="TimeSpan"
           timeToLive="TimeSpan"
           useActiveDirectory="Boolean"
           useMsmqTracing="Boolean"
           useSourceJournal="Boolean">
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/InfoCard" />
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73bb7-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="73bb7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="73bb7-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="73bb7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73bb7-110">特性</span><span class="sxs-lookup"><span data-stu-id="73bb7-110">Attributes</span></span>  
  
|<span data-ttu-id="73bb7-111">特性</span><span class="sxs-lookup"><span data-stu-id="73bb7-111">Attribute</span></span>|<span data-ttu-id="73bb7-112">描述</span><span class="sxs-lookup"><span data-stu-id="73bb7-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="73bb7-113">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="73bb7-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="73bb7-114">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="73bb7-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="73bb7-115">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="73bb7-115">The default is 00:01:00.</span></span>|  
|`customDeadLetterQueue`|<span data-ttu-id="73bb7-116">一个 URI，包含每个应用程序的死信队列（该队列用于放置已过期的消息或者放置传输或传递失败的消息）的位置。</span><span class="sxs-lookup"><span data-stu-id="73bb7-116">A URI that contains the location of the per-application dead letter queue, where messages that have expired or that have failed transfer or delivery are placed.</span></span><br /><br /> <span data-ttu-id="73bb7-117">死信队列是发送应用程序的队列管理器中的一个队列，用于放置传递失败的过期消息。</span><span class="sxs-lookup"><span data-stu-id="73bb7-117">The dead letter queue is a queue on the queue manager of the sending application for expired messages that have failed to be delivered.</span></span><br /><br /> <span data-ttu-id="73bb7-118"><xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> 指定的 URI 必须使用 net.msmq 方案。</span><span class="sxs-lookup"><span data-stu-id="73bb7-118">The URI that is specified by <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> must use the net.msmq scheme.</span></span>|  
|`deadLetterQueue`|<span data-ttu-id="73bb7-119">一个 <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> 值，该值指定所用死信队列（如果有）的类型。</span><span class="sxs-lookup"><span data-stu-id="73bb7-119">A <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> value specifying which type of dead-letter queue to use, if any.</span></span><br /><br /> <span data-ttu-id="73bb7-120">死信队列是无法传递到应用程序的消息所要传输到的位置。</span><span class="sxs-lookup"><span data-stu-id="73bb7-120">A dead-letter queue is the place where messages that have failed to be delivered to the application will be transferred.</span></span><br /><br /> <span data-ttu-id="73bb7-121">对于需要 `exactlyOnce` 保证（即，`exactlyOnce` 属性设置为 `true`）的消息，此属性默认为 MSMQ 中系统级事务性死信队列。</span><span class="sxs-lookup"><span data-stu-id="73bb7-121">For messages that require `exactlyOnce` assurance (that is, the `exactlyOnce` attribute is set to `true`), this attribute defaults to the system-wide transactional dead-letter queue in MSMQ.</span></span><br /><br /> <span data-ttu-id="73bb7-122">对于不需要保证的消息，此属性默认为 `null`。</span><span class="sxs-lookup"><span data-stu-id="73bb7-122">For messages that require no assurances, this attribute defaults to `null`.</span></span>|  
|`durable`|<span data-ttu-id="73bb7-123">一个布尔值，指示消息在队列中是持久的还是可变的。</span><span class="sxs-lookup"><span data-stu-id="73bb7-123">A Boolean value that indicates whether the message is durable or volatile in the queue.</span></span> <span data-ttu-id="73bb7-124">持久消息能够在队列管理器崩溃后保留下来，而可变消息则不能。</span><span class="sxs-lookup"><span data-stu-id="73bb7-124">A durable message survives a queue manager crash, while a volatile message does not.</span></span> <span data-ttu-id="73bb7-125">当应用程序需要较低的延迟并且可以容忍偶尔丢失消息时，可变消息是有用的。</span><span class="sxs-lookup"><span data-stu-id="73bb7-125">Volatile messages are useful when applications require lower latency and can tolerate occasional lost messages.</span></span> <span data-ttu-id="73bb7-126">如果 `exactlyOnce` 属性设置为 `true`，则消息必须为持久的消息。</span><span class="sxs-lookup"><span data-stu-id="73bb7-126">If the `exactlyOnce` attribute is set to `true`, the messages must be durable.</span></span> <span data-ttu-id="73bb7-127">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="73bb7-127">The default is `true`.</span></span>|  
|`exactlyOnce`|<span data-ttu-id="73bb7-128">一个布尔值，指示是否只传递一次此绑定所处理的每个消息。</span><span class="sxs-lookup"><span data-stu-id="73bb7-128">A Boolean value that indicates whether each message processed by this binding is delivered only once.</span></span> <span data-ttu-id="73bb7-129">然后，将通知发送方有关传递失败的信息。</span><span class="sxs-lookup"><span data-stu-id="73bb7-129">The sender will then be notified of delivery failures.</span></span> <span data-ttu-id="73bb7-130">如果 `durable` 为 `false`，则将忽略此属性并且传输消息，而不会提供传递保证。</span><span class="sxs-lookup"><span data-stu-id="73bb7-130">When `durable` is `false`, this attribute is ignored and messages are transferred without delivery assurance.</span></span> <span data-ttu-id="73bb7-131">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="73bb7-131">The default is `true`.</span></span> <span data-ttu-id="73bb7-132">有关详细信息，请参阅 <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>。</span><span class="sxs-lookup"><span data-stu-id="73bb7-132">For more information, see <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="73bb7-133">一个整数，指定此绑定的最大缓冲池大小。</span><span class="sxs-lookup"><span data-stu-id="73bb7-133">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="73bb7-134">默认值为 8。</span><span class="sxs-lookup"><span data-stu-id="73bb7-134">The default is 8.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="73bb7-135">一个正整数，定义此绑定所处理的最大消息大小（以字节为单位），其中包括标头。</span><span class="sxs-lookup"><span data-stu-id="73bb7-135">A positive integer that defines the maximum message size, in bytes, including headers, that is processed by this binding.</span></span> <span data-ttu-id="73bb7-136">如果消息超出此限制，则发送方将收到 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="73bb7-136">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="73bb7-137">接收方将删除该消息，并在跟踪日志中创建事件项。</span><span class="sxs-lookup"><span data-stu-id="73bb7-137">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="73bb7-138">默认值为 65536。</span><span class="sxs-lookup"><span data-stu-id="73bb7-138">The default is 65536.</span></span> <span data-ttu-id="73bb7-139">对消息大小进行的此限制旨在降低遭受拒绝服务 (DoS) 攻击的可能性。</span><span class="sxs-lookup"><span data-stu-id="73bb7-139">This bound on message size is intended to limit exposure to Denial of Service (DoS) attacks.</span></span>|  
|`maxRetryCycles`|<span data-ttu-id="73bb7-140">一个整数，指示病毒消息检测功能所使用的重试周期数。</span><span class="sxs-lookup"><span data-stu-id="73bb7-140">An integer that indicates the number of retry cycles used by the poison-message detection feature.</span></span> <span data-ttu-id="73bb7-141">如果所有周期的所有传递尝试均失败，则消息将变为病毒消息。</span><span class="sxs-lookup"><span data-stu-id="73bb7-141">A message becomes a poison message when it fails all delivery attempts of all cycles.</span></span> <span data-ttu-id="73bb7-142">默认值为 3。</span><span class="sxs-lookup"><span data-stu-id="73bb7-142">The default is 3.</span></span> <span data-ttu-id="73bb7-143">有关详细信息，请参阅 <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A> 。</span><span class="sxs-lookup"><span data-stu-id="73bb7-143">For more information, see <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A>.</span></span>|  
|`name`|<span data-ttu-id="73bb7-144">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="73bb7-144">Required attribute.</span></span> <span data-ttu-id="73bb7-145">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="73bb7-145">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="73bb7-146">因为此值用作绑定的标识，所以它应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="73bb7-146">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="73bb7-147">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="73bb7-147">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="73bb7-148">有关默认配置和无值绑定和行为的详细信息，请参阅[WCF 服务的](../../../wcf/samples/simplified-configuration-for-wcf-services.md)[简化配置](../../../wcf/simplified-configuration.md)和简化配置。</span><span class="sxs-lookup"><span data-stu-id="73bb7-148">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="73bb7-149">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="73bb7-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="73bb7-150">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="73bb7-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="73bb7-151">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="73bb7-151">The default is 00:01:00.</span></span>|  
|`QueueTransferProtocol`|<span data-ttu-id="73bb7-152">一个有效的 <xref:System.ServiceModel.QueueTransferProtocol> 值，指定此绑定所使用的排队通信通道传输。</span><span class="sxs-lookup"><span data-stu-id="73bb7-152">A valid <xref:System.ServiceModel.QueueTransferProtocol> value that specifies the queued communication channel transport that this binding uses.</span></span> <span data-ttu-id="73bb7-153">在使用 SOAP 可靠消息协议时，MSMQ 不支持 Active Directory 寻址。</span><span class="sxs-lookup"><span data-stu-id="73bb7-153">MSMQ does not support Active Directory addressing when using SOAP Reliable Messaging Protocol.</span></span> <span data-ttu-id="73bb7-154">因此，当`Srmp` `useActiveDirectory`特性设置为`Srmps` `true`时，不应将此特性设置为或。</span><span class="sxs-lookup"><span data-stu-id="73bb7-154">Therefore, you should not set this attribute to `Srmp` or `Srmps` when the `useActiveDirectory` attribute is set to `true`.</span></span>|  
|`receiveErrorHandling`|<span data-ttu-id="73bb7-155">一个 <xref:System.ServiceModel.ReceiveErrorHandling> 值，指定如何处理病毒消息和不可调度的消息。</span><span class="sxs-lookup"><span data-stu-id="73bb7-155">A <xref:System.ServiceModel.ReceiveErrorHandling> value that specifies how poison and nondispatchable messages are handled.</span></span>|  
|`receiveRetryCount`|<span data-ttu-id="73bb7-156">一个整数，指定队列管理器在将消息传输到重试队列前可尝试发送该消息的最大次数。</span><span class="sxs-lookup"><span data-stu-id="73bb7-156">An integer that specifies the maximum number of times the queue manager should attempt to send a message before transferring it to the retry queue.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="73bb7-157">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="73bb7-157">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="73bb7-158">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="73bb7-158">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="73bb7-159">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="73bb7-159">The default is 00:10:00.</span></span>|  
|`retryCycleDelay`|<span data-ttu-id="73bb7-160">一个 TimeSpan 值，指定尝试传递无法立即传递的消息时，各个重试周期之间的时间延迟。</span><span class="sxs-lookup"><span data-stu-id="73bb7-160">A TimeSpan value that specifies the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span> <span data-ttu-id="73bb7-161">该值只定义最小等待时间，因为实际等待时间可能较长。</span><span class="sxs-lookup"><span data-stu-id="73bb7-161">The value defines only the minimum wait time because actual wait time can be longer.</span></span> <span data-ttu-id="73bb7-162">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="73bb7-162">The default value is 00:10:00.</span></span> <span data-ttu-id="73bb7-163">有关详细信息，请参阅 <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A> 。</span><span class="sxs-lookup"><span data-stu-id="73bb7-163">For more information, see <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A>.</span></span>|  
|`sendTimeout`|<span data-ttu-id="73bb7-164">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="73bb7-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="73bb7-165">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="73bb7-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="73bb7-166">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="73bb7-166">The default is 00:01:00.</span></span>|  
|`timeToLive`|<span data-ttu-id="73bb7-167">一个 TimeSpan 值，指定在消息过期并放入死信队列之前消息保持有效的持续时间。</span><span class="sxs-lookup"><span data-stu-id="73bb7-167">A TimeSpan value that specifies how long the messages are valid before they are expired and put into the dead-letter queue.</span></span> <span data-ttu-id="73bb7-168">默认值为 1.00:00:00。</span><span class="sxs-lookup"><span data-stu-id="73bb7-168">The default is 1.00:00:00.</span></span><br /><br /> <span data-ttu-id="73bb7-169">设置此属性可以确保具有时效性的消息不会在由接收应用程序进行处理之前过时。</span><span class="sxs-lookup"><span data-stu-id="73bb7-169">This attribute is set to ensure that time-sensitive messages do not become stale before they are processed by the receiving applications.</span></span> <span data-ttu-id="73bb7-170">如果队列中的消息在指定时间间隔内未被接收应用程序进行处理，则称该消息为过时消息。</span><span class="sxs-lookup"><span data-stu-id="73bb7-170">A message in a queue that is not consumed by the receiving application within the time interval specified is said to be expired.</span></span> <span data-ttu-id="73bb7-171">过时消息被发送到称为“死信队列”的特殊队列中。</span><span class="sxs-lookup"><span data-stu-id="73bb7-171">Expired messages are sent to special queue called the dead letter queue.</span></span> <span data-ttu-id="73bb7-172">死信队列的位置通过 `DeadLetterQueue` 属性进行设置，或基于保证设置为适当的默认值。</span><span class="sxs-lookup"><span data-stu-id="73bb7-172">The location of the dead letter queue is set with the `DeadLetterQueue` attribute or to the appropriate default, based on assurances.</span></span>|  
|`usingActiveDirectory`|<span data-ttu-id="73bb7-173">一个布尔值，指定是否应该使用 Active Directory 转换队列地址。</span><span class="sxs-lookup"><span data-stu-id="73bb7-173">A Boolean value that specifies if queue addresses should be converted using Active Directory.</span></span><br /><br /> <span data-ttu-id="73bb7-174">MSMQ 队列地址可由路径名或直接格式名组成。</span><span class="sxs-lookup"><span data-stu-id="73bb7-174">MSMQ queue addresses can consist of path names or direct format names.</span></span> <span data-ttu-id="73bb7-175">对于直接格式名，MSMQ 会使用 DNS、NetBIOS 或 IP 解析计算机名称。</span><span class="sxs-lookup"><span data-stu-id="73bb7-175">With a direct format name, MSMQ resolves the computer name using DNS, NetBIOS or IP.</span></span> <span data-ttu-id="73bb7-176">对于路径名，MSMQ 会使用 Active Directory 解析计算机名称。</span><span class="sxs-lookup"><span data-stu-id="73bb7-176">With a path name, MSMQ resolves the computer name using Active Directory.</span></span><br /><br /> <span data-ttu-id="73bb7-177">默认情况下，Windows Communication Foundation （WCF）排队传输会将消息队列的 URI 转换为直接格式名。</span><span class="sxs-lookup"><span data-stu-id="73bb7-177">By default, Windows Communication Foundation (WCF) queued transport converts the URI of a message queue to a direct format name.</span></span> <span data-ttu-id="73bb7-178">通过将 `UseActiveDirectory` 属性设置为 True，应用程序可以指定排队传输应使用 Active Directory 而不是 DNS、NetBIOS 或 IP 来解析计算机名称。</span><span class="sxs-lookup"><span data-stu-id="73bb7-178">By setting the `UseActiveDirectory` property to true, an application can specify that the queued transport should resolve the computer name using Active Directory rather than DNS, NetBIOS, or IP.</span></span>|  
|`useMsmqTracing`|<span data-ttu-id="73bb7-179">一个布尔值，指定是否应跟踪由此绑定处理的消息。</span><span class="sxs-lookup"><span data-stu-id="73bb7-179">A Boolean value that specifies whether messages processed by this binding should be traced.</span></span> <span data-ttu-id="73bb7-180">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="73bb7-180">The default is `false`.</span></span> <span data-ttu-id="73bb7-181">如果启用了跟踪，则每当消息离开或到达消息队列计算机时，都会创建报告消息并将其发送到报告队列。</span><span class="sxs-lookup"><span data-stu-id="73bb7-181">When tracing is enabled, report messages are created and sent to the report queue each time the message leaves or arrives at a Message Queuing computer.</span></span>|  
|`useSourceJournal`|<span data-ttu-id="73bb7-182">一个布尔值，指定是否应将由此绑定处理的消息的副本存储在源日志中。</span><span class="sxs-lookup"><span data-stu-id="73bb7-182">A Boolean value that specifies copies of messages processed by this binding should be stored in the source journal.</span></span> <span data-ttu-id="73bb7-183">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="73bb7-183">The default is `false`.</span></span><br /><br /> <span data-ttu-id="73bb7-184">如果排队应用程序要保留已离开计算机传出队列的消息的记录，则可以将这些消息复制到日志队列。</span><span class="sxs-lookup"><span data-stu-id="73bb7-184">Queued applications that want to keep a record of messages that have left the computer's outgoing queue can copy the messages to a journal queue.</span></span> <span data-ttu-id="73bb7-185">在消息离开传出队列，并且接收到目标计算机已接收该消息的确认后，该消息的副本就会保留在发送计算机的系统日志队列中。</span><span class="sxs-lookup"><span data-stu-id="73bb7-185">Once a message leaves the outgoing queue and an acknowledgment is received that the message was received on the destination computer, a copy of the message is kept in the sending computer's system journal queue.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73bb7-186">子元素</span><span class="sxs-lookup"><span data-stu-id="73bb7-186">Child Elements</span></span>  
  
|<span data-ttu-id="73bb7-187">元素</span><span class="sxs-lookup"><span data-stu-id="73bb7-187">Element</span></span>|<span data-ttu-id="73bb7-188">描述</span><span class="sxs-lookup"><span data-stu-id="73bb7-188">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="73bb7-189">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="73bb7-189">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="73bb7-190">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="73bb7-190">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="73bb7-191">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="73bb7-191">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="73bb7-192">\<security></span><span class="sxs-lookup"><span data-stu-id="73bb7-192">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="73bb7-193">定义绑定的安全设置。</span><span class="sxs-lookup"><span data-stu-id="73bb7-193">Defines the security settings for the binding.</span></span> <span data-ttu-id="73bb7-194">此元素的类型为 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="73bb7-194">This element is of type <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="73bb7-195">父元素</span><span class="sxs-lookup"><span data-stu-id="73bb7-195">Parent Elements</span></span>  
  
|<span data-ttu-id="73bb7-196">元素</span><span class="sxs-lookup"><span data-stu-id="73bb7-196">Element</span></span>|<span data-ttu-id="73bb7-197">描述</span><span class="sxs-lookup"><span data-stu-id="73bb7-197">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73bb7-198">\<bindings></span><span class="sxs-lookup"><span data-stu-id="73bb7-198">\<bindings></span></span>](bindings.md)|<span data-ttu-id="73bb7-199">此元素包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="73bb7-199">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73bb7-200">备注</span><span class="sxs-lookup"><span data-stu-id="73bb7-200">Remarks</span></span>  
 <span data-ttu-id="73bb7-201">`netMsmqBinding` 绑定通过利用 Microsoft 消息队列 (MSMQ) 作为传输来提供队列支持，并且为松耦合应用程序、故障隔离、负载均衡和断开连接的操作提供支持。</span><span class="sxs-lookup"><span data-stu-id="73bb7-201">The `netMsmqBinding` binding provides support for queuing by leveraging Microsoft Message Queuing (MSMQ) as a transport and enables support for loosely coupled applications, failure isolation, load leveling and disconnected operations.</span></span> <span data-ttu-id="73bb7-202">有关这些功能的讨论，请参阅[WCF 中的队列](../../../wcf/feature-details/queues-in-wcf.md)。</span><span class="sxs-lookup"><span data-stu-id="73bb7-202">For a discussion of these features, see [Queues in WCF](../../../wcf/feature-details/queues-in-wcf.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="73bb7-203">示例</span><span class="sxs-lookup"><span data-stu-id="73bb7-203">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <netMsmqBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 deadLetterQueue="net.msmq://localhost/blah"
                 durable="true"
                 exactlyOnce="true"
                 maxReceivedMessageSize="1000"
                 maxRetries="11"
                 maxRetryCycles="12"
                 poisonMessageHandling="Disabled"
                 rejectAfterLastRetry="false"
                 retryCycleDelay="00:05:55"
                 timeToLive="00:11:11"
                 sourceJournal="true"
                 useMsmqTracing="true"
                 useActiveDirectory="true">
          <security>
            <message clientCredentialType="Windows" />
          </security>
        </binding>
      </netMsmqBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="73bb7-204">请参阅</span><span class="sxs-lookup"><span data-stu-id="73bb7-204">See also</span></span>

- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement>
- [<span data-ttu-id="73bb7-205">\<binding></span><span class="sxs-lookup"><span data-stu-id="73bb7-205">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="73bb7-206">绑定</span><span class="sxs-lookup"><span data-stu-id="73bb7-206">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="73bb7-207">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="73bb7-207">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="73bb7-208">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="73bb7-208">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="73bb7-209">WCF 中的队列</span><span class="sxs-lookup"><span data-stu-id="73bb7-209">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
