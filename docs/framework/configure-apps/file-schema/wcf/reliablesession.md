---
title: <reliableSession>
ms.date: 03/30/2017
ms.assetid: 129b4a59-37f0-4030-b664-03795d257d29
ms.openlocfilehash: 324c46d88d084605dc2b873c65d2a7e7c7a2c4fb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188378"
---
# <a name="reliablesession"></a><span data-ttu-id="082e2-101">\<reliableSession></span><span class="sxs-lookup"><span data-stu-id="082e2-101">\<reliableSession></span></span>
<span data-ttu-id="082e2-102">定义 WS-ReliableMessaging 的设置。</span><span class="sxs-lookup"><span data-stu-id="082e2-102">Defines setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="082e2-103">如果将该元素添加到自定义绑定，则生成的通道可支持一次性传递保证。</span><span class="sxs-lookup"><span data-stu-id="082e2-103">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span>  
  
 <span data-ttu-id="082e2-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="082e2-104">\<system.serviceModel></span></span>  
<span data-ttu-id="082e2-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="082e2-105">\<bindings></span></span>  
<span data-ttu-id="082e2-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="082e2-106">\<customBinding></span></span>  
<span data-ttu-id="082e2-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="082e2-107">\<binding></span></span>  
<span data-ttu-id="082e2-108">\<reliableSession></span><span class="sxs-lookup"><span data-stu-id="082e2-108">\<reliableSession></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="082e2-109">语法</span><span class="sxs-lookup"><span data-stu-id="082e2-109">Syntax</span></span>  
  
```xml  
<reliableSession acknowledgementInterval="TimeSpan"
                 flowControlEnabled="Boolean"
                 inactivityTimeout="TimeSpan"
                 maxPendingChannels="Integer"
                 maxRetryCount="Integer"
                 maxTransferWindowSize="Integer"
                 reliableMessagingVersion="Default/WSReliableMessagingFebruary2005/WSReliableMessaging11"
                 ordered="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="082e2-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="082e2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="082e2-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="082e2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="082e2-112">特性</span><span class="sxs-lookup"><span data-stu-id="082e2-112">Attributes</span></span>  
  
|<span data-ttu-id="082e2-113">特性</span><span class="sxs-lookup"><span data-stu-id="082e2-113">Attribute</span></span>|<span data-ttu-id="082e2-114">描述</span><span class="sxs-lookup"><span data-stu-id="082e2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="082e2-115">acknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="082e2-115">acknowledgementInterval</span></span>|<span data-ttu-id="082e2-116">一个 <xref:System.TimeSpan>，包含最大时间间隔，通道在等待此时间间隔后才会发送截至该时刻所收到的消息的确认。</span><span class="sxs-lookup"><span data-stu-id="082e2-116">A <xref:System.TimeSpan> that contains the maximum time interval the channel is going to wait to send an acknowledgment for messages received up to that point.</span></span> <span data-ttu-id="082e2-117">默认值为 00:00:0.2。</span><span class="sxs-lookup"><span data-stu-id="082e2-117">The default is 00:00:0.2.</span></span>|  
|<span data-ttu-id="082e2-118">flowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="082e2-118">flowControlEnabled</span></span>|<span data-ttu-id="082e2-119">一个布尔值，指示是否激活高级流控制（特定于 Microsoft 的 WS-ReliableMessaging 流控制实现）。</span><span class="sxs-lookup"><span data-stu-id="082e2-119">A Boolean value that indicates whether advanced flow control, a Microsoft-specific implementation of flow control for WS-Reliable messaging, is activated.</span></span> <span data-ttu-id="082e2-120">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="082e2-120">The default is `true`.</span></span>|  
|<span data-ttu-id="082e2-121">inactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="082e2-121">inactivityTimeout</span></span>|<span data-ttu-id="082e2-122">一个 <xref:System.TimeSpan>，指定通道在出错之前允许其他通信方不发送任何消息的最大持续时间。</span><span class="sxs-lookup"><span data-stu-id="082e2-122">A <xref:System.TimeSpan> that specifies the maximum duration that the channel is going to allow the other communication party not to send any messages, before faulting the channel.</span></span> <span data-ttu-id="082e2-123">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="082e2-123">The default is 00:10:00.</span></span><br /><br /> <span data-ttu-id="082e2-124">通道上的活动被定义为接收应用程序消息或基础结构消息。</span><span class="sxs-lookup"><span data-stu-id="082e2-124">Activity on a channel is defined as receiving an application or infrastructure messages.</span></span> <span data-ttu-id="082e2-125">此属性控制保持非活动会话存在的最长时间。</span><span class="sxs-lookup"><span data-stu-id="082e2-125">This property controls the maximum amount of time to keep an inactive session alive.</span></span> <span data-ttu-id="082e2-126">如果经过此最长时间后该会话仍不活动，则基础结构会中止该会话，且通道会出错。</span><span class="sxs-lookup"><span data-stu-id="082e2-126">If longer time passes with no activity, the session is aborted by the infrastructure and the channel faults.</span></span> <span data-ttu-id="082e2-127">**注意：** 应用程序无需定期发送消息即可保持连接状态。</span><span class="sxs-lookup"><span data-stu-id="082e2-127">**Note:**  It is not necessary for the application to periodically send messages to keep the connection alive.</span></span>|  
|<span data-ttu-id="082e2-128">maxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="082e2-128">maxPendingChannels</span></span>|<span data-ttu-id="082e2-129">一个整数，指定侦听器上可等待接受的最大通道数。</span><span class="sxs-lookup"><span data-stu-id="082e2-129">An integer that specifies the maximum number of channels that can wait on the listener to be accepted.</span></span> <span data-ttu-id="082e2-130">该值应介于 1 至 16384 之间（包括这两个值）。</span><span class="sxs-lookup"><span data-stu-id="082e2-130">This value should be between 1 to 16384 inclusive.</span></span> <span data-ttu-id="082e2-131">默认值为 4。</span><span class="sxs-lookup"><span data-stu-id="082e2-131">The default is 4.</span></span><br /><br /> <span data-ttu-id="082e2-132">通道在等待被接受时处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="082e2-132">Channels are pending when they are waiting to be accepted.</span></span> <span data-ttu-id="082e2-133">达到此限制后，将不创建任何通道。</span><span class="sxs-lookup"><span data-stu-id="082e2-133">Once that limit is reached, no channels are created.</span></span> <span data-ttu-id="082e2-134">确切地说，在达到此数值之前（通过接受挂起的通道来实现），通道处于挂起模式。</span><span class="sxs-lookup"><span data-stu-id="082e2-134">Rather, they are put in pending mode until this number goes down (by accepting pending channels).</span></span> <span data-ttu-id="082e2-135">这是对每个工厂的限制。</span><span class="sxs-lookup"><span data-stu-id="082e2-135">This is a per-factory limit.</span></span><br /><br /> <span data-ttu-id="082e2-136">当达到此阈值时如果远程应用程序尝试建立新的可靠会话，则会拒绝请求且打开操作将提示此错误。</span><span class="sxs-lookup"><span data-stu-id="082e2-136">When the threshold is reached and a remote application tries to establish a new reliable session, the request is denied and the open operation that prompted this faults.</span></span> <span data-ttu-id="082e2-137">此限制不适用于挂起的传出通道数。</span><span class="sxs-lookup"><span data-stu-id="082e2-137">This limit does not apply to the number of pending outgoing channels.</span></span>|  
|<span data-ttu-id="082e2-138">maxRetryCount</span><span class="sxs-lookup"><span data-stu-id="082e2-138">maxRetryCount</span></span>|<span data-ttu-id="082e2-139">一个整数，指定可靠通道未收到消息确认时，在其基础通道上调用 Send 尝试重新传输该消息的最大尝试次数。</span><span class="sxs-lookup"><span data-stu-id="082e2-139">An integer that specifies the maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgment for, by calling Send on its underlying channel.</span></span><br /><br /> <span data-ttu-id="082e2-140">此值应大于零。</span><span class="sxs-lookup"><span data-stu-id="082e2-140">This value should be greater than zero.</span></span> <span data-ttu-id="082e2-141">默认值为 8。</span><span class="sxs-lookup"><span data-stu-id="082e2-141">The default is 8.</span></span><br /><br /> <span data-ttu-id="082e2-142">此值应为大于零的整数。</span><span class="sxs-lookup"><span data-stu-id="082e2-142">This value should be an integer greater than zero.</span></span> <span data-ttu-id="082e2-143">如果在最后一次重新传输后未收到确认，则通道出错。</span><span class="sxs-lookup"><span data-stu-id="082e2-143">If an acknowledgment is not received after the last retransmission, the channel faults.</span></span><br /><br /> <span data-ttu-id="082e2-144">如果接收方在接收时确认了消息的传递，则认为该消息已传输。</span><span class="sxs-lookup"><span data-stu-id="082e2-144">A message is considered to be transferred if its delivery at the recipient has been acknowledged by the recipient.</span></span><br /><br /> <span data-ttu-id="082e2-145">如果在传输消息后的一段确定时间内未收到确认，则基础结构将自动重新传输该消息。</span><span class="sxs-lookup"><span data-stu-id="082e2-145">If an acknowledgment has not been received within a certain amount of time for a message that has been transmitted, the infrastructure automatically retransmits the message.</span></span> <span data-ttu-id="082e2-146">此基础结构尝试重新发送消息的次数最多为此属性指定的次数。</span><span class="sxs-lookup"><span data-stu-id="082e2-146">The infrastructure tries to resend the message for at most the number of times specified by this property.</span></span> <span data-ttu-id="082e2-147">如果在最后一次重新传输后未收到确认，则通道出错。</span><span class="sxs-lookup"><span data-stu-id="082e2-147">If an acknowledgment is not received after the last retransmission, the channel faults.</span></span><br /><br /> <span data-ttu-id="082e2-148">基础结构使用指数补偿算法根据计算的平均往返时间来确定何时重新传输。</span><span class="sxs-lookup"><span data-stu-id="082e2-148">The infrastructure uses an exponential back-off algorithm to determine when to retransmit, based on a computed average round-trip time.</span></span> <span data-ttu-id="082e2-149">在重新传输之前，此时间最初为 1 秒钟，每尝试一次，延迟时间便会加倍，因此在第一次尝试传输和最后一次尝试传输之间大约会经过 8.5 分钟。</span><span class="sxs-lookup"><span data-stu-id="082e2-149">The time initially starts at 1 second before retransmission and doubling the delay with every attempt, which results in approximately 8.5 minutes passing between the first transmission attempt and the last retransmission attempt.</span></span> <span data-ttu-id="082e2-150">可以根据计算的往返时间来调整第一次尝试重新传输的时间，因此这些尝试所经历的时间将会相应地发生变化。</span><span class="sxs-lookup"><span data-stu-id="082e2-150">The time for the first retransmission attempt is adjusted according to the calculated round-trip time and the resulting stretch of time that those attempts take varies accordingly.</span></span> <span data-ttu-id="082e2-151">这样，可以使重新传输时间动态地适应不断变化的网络条件。</span><span class="sxs-lookup"><span data-stu-id="082e2-151">This allows the retransmission time to dynamically adapt to varying network conditions.</span></span>|  
|<span data-ttu-id="082e2-152">maxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="082e2-152">maxTransferWindowSize</span></span>|<span data-ttu-id="082e2-153">一个指定缓冲区最大大小的整数。</span><span class="sxs-lookup"><span data-stu-id="082e2-153">An integer that specifies the maximum size of the buffer.</span></span> <span data-ttu-id="082e2-154">有效值介于 1 和 4096 之间（包括这两个值）。</span><span class="sxs-lookup"><span data-stu-id="082e2-154">Valid values are from 1 to 4096 inclusive.</span></span><br /><br /> <span data-ttu-id="082e2-155">在客户端上，该属性定义可靠通道在保存接收者尚未确认的消息时所使用的缓冲区的最大大小。</span><span class="sxs-lookup"><span data-stu-id="082e2-155">On the client, this attribute defines the maximum size of the buffer used by a reliable channel to hold messages not yet acknowledged by the receiver.</span></span> <span data-ttu-id="082e2-156">此配额的单位是消息。</span><span class="sxs-lookup"><span data-stu-id="082e2-156">The unit of the quota is a message.</span></span> <span data-ttu-id="082e2-157">如果缓冲区已满，将阻止后来的“发送”操作。</span><span class="sxs-lookup"><span data-stu-id="082e2-157">If the buffer is full, further SEND operations are blocked.</span></span><br /><br /> <span data-ttu-id="082e2-158">在接收方上，该属性定义通道在存储尚未发送到应用程序的传入消息时所使用的缓冲区的最大大小。</span><span class="sxs-lookup"><span data-stu-id="082e2-158">On the receiver, this attribute defines the maximum size of the buffer used by the channel to store incoming messages not yet dispatched to the application.</span></span> <span data-ttu-id="082e2-159">如果缓冲区已满，则接收方将删除后来的消息而不会给出任何提示并要求客户端重新传输。</span><span class="sxs-lookup"><span data-stu-id="082e2-159">If the buffer is full, further messages are silently dropped by the receiver and require retransmission by the client.</span></span>|  
|<span data-ttu-id="082e2-160">ordered</span><span class="sxs-lookup"><span data-stu-id="082e2-160">ordered</span></span>|<span data-ttu-id="082e2-161">一个布尔值，指定是否保证消息以其发送顺序抵达。</span><span class="sxs-lookup"><span data-stu-id="082e2-161">A Boolean that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span> <span data-ttu-id="082e2-162">如果此设置为 `false`，则消息可以不按顺序抵达。</span><span class="sxs-lookup"><span data-stu-id="082e2-162">If this setting is `false`, messages can arrive out of order.</span></span> <span data-ttu-id="082e2-163">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="082e2-163">The default is `true`.</span></span>|  
|<span data-ttu-id="082e2-164">reliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="082e2-164">reliableMessagingVersion</span></span>|<span data-ttu-id="082e2-165"><xref:System.ServiceModel.ReliableMessagingVersion> 中的一个有效值，指定要使用的 WS-ReliableMessaging 版本。</span><span class="sxs-lookup"><span data-stu-id="082e2-165">A valid value from <xref:System.ServiceModel.ReliableMessagingVersion> that specifies the WS-ReliableMessaging version to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="082e2-166">子元素</span><span class="sxs-lookup"><span data-stu-id="082e2-166">Child Elements</span></span>  
 <span data-ttu-id="082e2-167">None</span><span class="sxs-lookup"><span data-stu-id="082e2-167">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="082e2-168">父元素</span><span class="sxs-lookup"><span data-stu-id="082e2-168">Parent Elements</span></span>  
  
|<span data-ttu-id="082e2-169">元素</span><span class="sxs-lookup"><span data-stu-id="082e2-169">Element</span></span>|<span data-ttu-id="082e2-170">描述</span><span class="sxs-lookup"><span data-stu-id="082e2-170">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="082e2-171">\<binding></span><span class="sxs-lookup"><span data-stu-id="082e2-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="082e2-172">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="082e2-172">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="082e2-173">备注</span><span class="sxs-lookup"><span data-stu-id="082e2-173">Remarks</span></span>  
 <span data-ttu-id="082e2-174">可靠会话提供可靠的消息和会话功能。</span><span class="sxs-lookup"><span data-stu-id="082e2-174">Reliable sessions provide features for reliable messaging and sessions.</span></span> <span data-ttu-id="082e2-175">可靠消息在失败时重新尝试通信并允许指定传递保证（如消息按顺序抵达）。</span><span class="sxs-lookup"><span data-stu-id="082e2-175">Reliable messaging retries communication on failure and allows delivery assurances such as in-order arrival of messages to be specified.</span></span> <span data-ttu-id="082e2-176">会话在调用之间将保持客户端的状态。</span><span class="sxs-lookup"><span data-stu-id="082e2-176">Sessions maintain state for clients between calls.</span></span> <span data-ttu-id="082e2-177">此元素还可以选择提供有序消息传递。</span><span class="sxs-lookup"><span data-stu-id="082e2-177">This element also optionally provides ordered message delivery.</span></span> <span data-ttu-id="082e2-178">这个已实现的会话可通过 SOAP 和传输中介。</span><span class="sxs-lookup"><span data-stu-id="082e2-178">This implemented session can cross SOAP and transport intermediaries.</span></span>  
  
 <span data-ttu-id="082e2-179">发送或接收消息时，每个绑定元素都表示一个处理步骤。</span><span class="sxs-lookup"><span data-stu-id="082e2-179">Each binding element represents a processing step when sending or receiving messages.</span></span> <span data-ttu-id="082e2-180">在运行时，绑定元素会创建必要的通道工厂和侦听器，用以生成发送和接收消息所需的传出和传入通道堆栈。</span><span class="sxs-lookup"><span data-stu-id="082e2-180">At runtime, binding elements create the channel factories and listeners that are necessary to build outgoing and incoming channel stacks required to send and receive messages.</span></span> <span data-ttu-id="082e2-181">`reliableSession` 会在堆栈中提供一个可选层，该可选层可在终结点之间建立可靠会话并配置此会话的行为。</span><span class="sxs-lookup"><span data-stu-id="082e2-181">The `reliableSession` provides an optional layer in the stack that can establish a reliable session between endpoints and configure the behavior of this session.</span></span>  
  
 <span data-ttu-id="082e2-182">有关详细信息，请参阅[可靠会话](../../../../../docs/framework/wcf/feature-details/reliable-sessions.md)。</span><span class="sxs-lookup"><span data-stu-id="082e2-182">For more information, see [Reliable Sessions](../../../../../docs/framework/wcf/feature-details/reliable-sessions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="082e2-183">示例</span><span class="sxs-lookup"><span data-stu-id="082e2-183">Example</span></span>  
 <span data-ttu-id="082e2-184">下面的示例演示如何用各种传输和消息编码元素配置自定义绑定，并特别启用可靠会话，这将保持客户端状态并指定按顺序传递保证。</span><span class="sxs-lookup"><span data-stu-id="082e2-184">The following example demonstrates how to configure a custom binding with various transport and message encoding elements, especially enabling reliable sessions, which maintains client state and specifies in-order delivery assurances.</span></span> <span data-ttu-id="082e2-185">此功能是在客户端和服务的应用程序配置文件中配置的。</span><span class="sxs-lookup"><span data-stu-id="082e2-185">This feature is configured in the application configuration files for the client and service.</span></span> <span data-ttu-id="082e2-186">此示例显示了服务配置。</span><span class="sxs-lookup"><span data-stu-id="082e2-186">The example show the service configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by host: http://localhost/servicemodelsamples/service.svc -->
        <!-- specify customBinding binding and a binding configuration to use -->
        <endpoint address=""
                  binding="customBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <!-- custom binding configuration - configures HTTP transport, reliable sessions -->
    <bindings>
      <customBinding>
        <binding name="Binding1">
          <reliableSession />
          <security authenticationMode="SecureConversation"
                    requireSecurityContextCancellation="true">
          </security>
          <compositeDuplex />
          <oneWay />
          <textMessageEncoding messageVersion="Soap12WSAddressing10"
                               writeEncoding="utf-8" />
          <httpTransport authenticationScheme="Anonymous"
                         bypassProxyOnLocal="false"
                         hostNameComparisonMode="StrongWildcard"
                         proxyAuthenticationScheme="Anonymous"
                         realm=""
                         useDefaultWebProxy="true" />
        </binding>
      </customBinding>
    </bindings>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="082e2-187">请参阅</span><span class="sxs-lookup"><span data-stu-id="082e2-187">See also</span></span>

- <xref:System.ServiceModel.Configuration.ReliableSessionElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
- [<span data-ttu-id="082e2-188">可靠会话</span><span class="sxs-lookup"><span data-stu-id="082e2-188">Reliable Sessions</span></span>](../../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
- [<span data-ttu-id="082e2-189">绑定</span><span class="sxs-lookup"><span data-stu-id="082e2-189">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="082e2-190">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="082e2-190">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="082e2-191">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="082e2-191">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="082e2-192">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="082e2-192">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
