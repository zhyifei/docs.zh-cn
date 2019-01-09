---
title: '&lt;localServiceSettings&gt; 元素'
ms.date: 03/30/2017
ms.assetid: 0658549c-3f65-46dd-8c5c-9895441ed734
ms.openlocfilehash: 5d5150590bc0a8a0d21662eadc7dda67aad872ef
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150274"
---
# <a name="ltlocalservicesettingsgt-element"></a><span data-ttu-id="74250-102">&lt;localServiceSettings&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="74250-102">&lt;localServiceSettings&gt; element</span></span>
<span data-ttu-id="74250-103">指定此绑定的本地服务安全设置。</span><span class="sxs-lookup"><span data-stu-id="74250-103">Specifies the security settings of a local service for this binding.</span></span>  
  
 <span data-ttu-id="74250-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="74250-104">\<system.serviceModel></span></span>  
<span data-ttu-id="74250-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="74250-105">\<bindings></span></span>  
<span data-ttu-id="74250-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="74250-106">\<customBinding></span></span>  
<span data-ttu-id="74250-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="74250-107">\<binding></span></span>  
<span data-ttu-id="74250-108">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="74250-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74250-109">语法</span><span class="sxs-lookup"><span data-stu-id="74250-109">Syntax</span></span>  
  
```xml  
<security>
  <localServiceSettings detectReplays="Boolean"
                        inactivityTimeout="TimeSpan"
                        issuedCookieLifeTime="TimeSpan"
                        maxCachedCookies="Integer"
                        maxClockSkew="TimeSpan"
                        maxPendingSessions="Integer"
                        maxStatefulNegotiations="Integer"
                        negotiationTimeout="TimeSpan"
                        reconnectTransportOnFailure="Boolean"
                        replayCacheSize="Integer"
                        replayWindow="TimeSpan"
                        sessionKeyRenewalInterval="TimeSpan"
                        sessionKeyRolloverInterval="TimeSpan"
                        timestampValidityDuration="TimeSpan" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74250-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="74250-110">Attributes and Elements</span></span>  
 <span data-ttu-id="74250-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="74250-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74250-112">特性</span><span class="sxs-lookup"><span data-stu-id="74250-112">Attributes</span></span>  
  
|<span data-ttu-id="74250-113">特性</span><span class="sxs-lookup"><span data-stu-id="74250-113">Attribute</span></span>|<span data-ttu-id="74250-114">描述</span><span class="sxs-lookup"><span data-stu-id="74250-114">Description</span></span>|  
|---------------|-----------------|  
|`detectReplays`|<span data-ttu-id="74250-115">一个布尔值，指定是否自动检测和处理针对通道的重放攻击。</span><span class="sxs-lookup"><span data-stu-id="74250-115">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span> <span data-ttu-id="74250-116">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="74250-116">The default is `false`.</span></span>|  
|`inactivityTimeout`|<span data-ttu-id="74250-117">一个正的 <xref:System.TimeSpan>，指定通道在超时之前等待的无活动持续时间。默认值为“01:00:00”。</span><span class="sxs-lookup"><span data-stu-id="74250-117">A positive <xref:System.TimeSpan> that specifies the duration of inactivity the channel waits before it times out. The default is "01:00:00".</span></span>|  
|`issuedCookieLifeTime`|<span data-ttu-id="74250-118">一个 <xref:System.TimeSpan>，指定颁发给所有新安全 Cookie 的生存期。</span><span class="sxs-lookup"><span data-stu-id="74250-118">A <xref:System.TimeSpan> that specifies the lifetime issued to all new security cookies.</span></span> <span data-ttu-id="74250-119">超过生存期的 Cookie 会被回收，且需要再次对其进行协商。</span><span class="sxs-lookup"><span data-stu-id="74250-119">Cookies that exceed their lifetime are recycled and need to be negotiated again.</span></span> <span data-ttu-id="74250-120">默认值为“10:00:00”。</span><span class="sxs-lookup"><span data-stu-id="74250-120">The default value is "10:00:00".</span></span>|  
|`maxCachedCookies`|<span data-ttu-id="74250-121">一个正整数，指定可以缓存的最大 Cookie 数。</span><span class="sxs-lookup"><span data-stu-id="74250-121">A positive integer that specifies the maximum number of cookies that can be cached.</span></span> <span data-ttu-id="74250-122">默认值为 1000。</span><span class="sxs-lookup"><span data-stu-id="74250-122">The default is 1000.</span></span>|  
|`maxClockSkew`|<span data-ttu-id="74250-123">一个 <xref:System.TimeSpan>，指定通信双方的系统时钟之间的最大时间差异。</span><span class="sxs-lookup"><span data-stu-id="74250-123">A <xref:System.TimeSpan> that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span> <span data-ttu-id="74250-124">默认值为“00:05:00”。</span><span class="sxs-lookup"><span data-stu-id="74250-124">The default value is "00:05:00".</span></span><br /><br /> <span data-ttu-id="74250-125">当此值被设置为默认值时，接收方所接受的消息的发送时间时间戳最多可比消息接收时间晚或早 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="74250-125">When this value is set to the default, the receiver accepts messages with send-time time stamps up to 5 minutes later or earlier than the time the message was received.</span></span> <span data-ttu-id="74250-126">未通过发送时间测试的消息会被拒绝。</span><span class="sxs-lookup"><span data-stu-id="74250-126">Messages that do not pass the send-time test are rejected.</span></span> <span data-ttu-id="74250-127">此设置与 `replayWindow` 属性结合使用。</span><span class="sxs-lookup"><span data-stu-id="74250-127">This setting is used in conjunction with the `replayWindow` attribute.</span></span>|  
|`maxPendingSessions`|<span data-ttu-id="74250-128">一个正整数，指定服务支持的最大挂起安全会话数。</span><span class="sxs-lookup"><span data-stu-id="74250-128">A positive integer that specifies the maximum number of pending security sessions that the service supports.</span></span> <span data-ttu-id="74250-129">达到此限制时，所有新客户端都会接收到 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="74250-129">When this limit is reached, all new clients receive SOAP faults.</span></span> <span data-ttu-id="74250-130">默认值为 1000。</span><span class="sxs-lookup"><span data-stu-id="74250-130">The default value is 1000.</span></span>|  
|`maxStatefulNegotiations`|<span data-ttu-id="74250-131">一个正整数，指定可以同时处于活动状态的最大安全协商数。</span><span class="sxs-lookup"><span data-stu-id="74250-131">A positive integer that specifies the number of security negotiations that can be active concurrently.</span></span> <span data-ttu-id="74250-132">超出此限制的协商会话需要排队，直到会话数低于限制值。</span><span class="sxs-lookup"><span data-stu-id="74250-132">Negotiation sessions in excess of the limit are queued and can only be completed when a space below the limit becomes available.</span></span> <span data-ttu-id="74250-133">默认值为 1024。</span><span class="sxs-lookup"><span data-stu-id="74250-133">The default value is 1024.</span></span>|  
|`negotiationTimeout`|<span data-ttu-id="74250-134">一个 <xref:System.TimeSpan>，指定通道使用的安全策略的生存期。</span><span class="sxs-lookup"><span data-stu-id="74250-134">A <xref:System.TimeSpan> that specifies the lifetime of the security policy used by channel.</span></span> <span data-ttu-id="74250-135">如果超过此时间，则通道将与客户端重新协商新的安全策略。</span><span class="sxs-lookup"><span data-stu-id="74250-135">When the time expires, the channel renegotiates with the client for a new security policy.</span></span> <span data-ttu-id="74250-136">默认值为“00:02:00”。</span><span class="sxs-lookup"><span data-stu-id="74250-136">The default value is "00:02:00".</span></span>|  
|`reconnectTransportOnFailure`|<span data-ttu-id="74250-137">一个布尔值，指定使用 WS-ReliableMessaging 的连接是否将在传输失败后尝试重新连接。</span><span class="sxs-lookup"><span data-stu-id="74250-137">A Boolean value that specifies whether connections using WS-Reliable messaging will attempt to reconnect after transport failures.</span></span> <span data-ttu-id="74250-138">默认值为 `true`，表示将进行无限次重新连接尝试。</span><span class="sxs-lookup"><span data-stu-id="74250-138">The default is `true`, which means that infinite attempts to reconnect are attempted.</span></span> <span data-ttu-id="74250-139">非活动超时能够打断此循环；非活动超时在无法重新连接通道时使其引发异常。</span><span class="sxs-lookup"><span data-stu-id="74250-139">The cycle is broken by the inactivity time-out, which causes the channel to throw an exception when it cannot be reconnected.</span></span>|  
|`replayCacheSize`|<span data-ttu-id="74250-140">一个正整数，指定用于重播检测的缓存 Nonce 的数目。</span><span class="sxs-lookup"><span data-stu-id="74250-140">A positive integer that specifies the number of cached nonces used for replay detection.</span></span> <span data-ttu-id="74250-141">如果超出此限制，则会移除最旧的 Nonce，并且为新消息创建一个新的 Nonce。</span><span class="sxs-lookup"><span data-stu-id="74250-141">If this limit is exceeded, the oldest nonce is removed and a new nonce is created for the new message.</span></span> <span data-ttu-id="74250-142">默认值为 500000。</span><span class="sxs-lookup"><span data-stu-id="74250-142">The default value is 500000.</span></span>|  
|`replayWindow`|<span data-ttu-id="74250-143">一个 <xref:System.TimeSpan>，指定单个消息 Nonce 有效的持续时间。</span><span class="sxs-lookup"><span data-stu-id="74250-143">A <xref:System.TimeSpan> that specifies the duration in which individual message nonces are valid.</span></span><br /><br /> <span data-ttu-id="74250-144">在此持续时间之后，如果发送的消息与之前发送的消息具有相同的 Nonce，则该消息将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="74250-144">After this duration, a message sent with the same nonce as the one sent before will not be accepted.</span></span> <span data-ttu-id="74250-145">此属性与 `maxClockSkew` 属性结合使用，以防止遭受重放攻击。</span><span class="sxs-lookup"><span data-stu-id="74250-145">This attribute is used in conjunction with the `maxClockSkew` attribute to prevent replay attacks.</span></span> <span data-ttu-id="74250-146">攻击者可以在其重放时间窗口过期之后重放消息。</span><span class="sxs-lookup"><span data-stu-id="74250-146">An attacker could replay a message after its replay window has expired.</span></span> <span data-ttu-id="74250-147">但是，该消息将无法通过 `maxClockSkew` 测试；如果消息的发送时间时间戳比消息接收时间晚或早指定的时间，则该测试会拒绝消息。</span><span class="sxs-lookup"><span data-stu-id="74250-147">This message, however, would fail the `maxClockSkew` test which rejects messages with send-time timestamps up to a specified time later or earlier than the time the message was received.</span></span>|  
|`sessionKeyRenewalInterval`|<span data-ttu-id="74250-148">一个 <xref:System.TimeSpan>，指定一段持续时间，发起方在此段时间之后将续订安全会话的密钥。</span><span class="sxs-lookup"><span data-stu-id="74250-148">A <xref:System.TimeSpan> that specifies the duration after which the initiator will renew the key for the security session.</span></span> <span data-ttu-id="74250-149">默认值为“10:00:00”。</span><span class="sxs-lookup"><span data-stu-id="74250-149">The default is "10:00:00".</span></span>|  
|`sessionKeyRolloverInterval`|<span data-ttu-id="74250-150">一个 <xref:System.TimeSpan>，指定在密钥续订期间，上一个会话密钥对于传入消息有效的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="74250-150">A <xref:System.TimeSpan> that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span> <span data-ttu-id="74250-151">默认值为“00:05:00”。</span><span class="sxs-lookup"><span data-stu-id="74250-151">The default is "00:05:00".</span></span><br /><br /> <span data-ttu-id="74250-152">在密钥续订期间，客户端和服务器必须总是使用最新的可用密钥来发送消息。</span><span class="sxs-lookup"><span data-stu-id="74250-152">During key renewal, the client and server must always send messages using the most current available key.</span></span> <span data-ttu-id="74250-153">在延期时间到期前，双方都可以接受以上一个会话密钥加密的传入消息。</span><span class="sxs-lookup"><span data-stu-id="74250-153">Both parties will accept incoming messages secured with the previous session key until the rollover time expires.</span></span>|  
|`timestampValidityDuration`|<span data-ttu-id="74250-154">一个值为正的 <xref:System.TimeSpan>，指定时间戳有效的持续时间。</span><span class="sxs-lookup"><span data-stu-id="74250-154">A positive <xref:System.TimeSpan> that specifies the duration in which a time stamp is valid.</span></span> <span data-ttu-id="74250-155">默认值为“00:15:00”。</span><span class="sxs-lookup"><span data-stu-id="74250-155">The default is "00:15:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74250-156">子元素</span><span class="sxs-lookup"><span data-stu-id="74250-156">Child Elements</span></span>  
 <span data-ttu-id="74250-157">无。</span><span class="sxs-lookup"><span data-stu-id="74250-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74250-158">父元素</span><span class="sxs-lookup"><span data-stu-id="74250-158">Parent Elements</span></span>  
  
|<span data-ttu-id="74250-159">元素</span><span class="sxs-lookup"><span data-stu-id="74250-159">Element</span></span>|<span data-ttu-id="74250-160">描述</span><span class="sxs-lookup"><span data-stu-id="74250-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74250-161">\<security></span><span class="sxs-lookup"><span data-stu-id="74250-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="74250-162">指定自定义绑定的安全选项。</span><span class="sxs-lookup"><span data-stu-id="74250-162">Specifies the security options for a custom binding.</span></span>|  
|[<span data-ttu-id="74250-163">\<secureConversationBootstrap ></span><span class="sxs-lookup"><span data-stu-id="74250-163">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="74250-164">指定用于启动安全对话服务的默认值。</span><span class="sxs-lookup"><span data-stu-id="74250-164">Specifies the default values used for initiating a secure conversation service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74250-165">备注</span><span class="sxs-lookup"><span data-stu-id="74250-165">Remarks</span></span>  
 <span data-ttu-id="74250-166">这些设置并非作为安全策略的组成部分而发布，而且不影响客户端绑定，因此是本地的。</span><span class="sxs-lookup"><span data-stu-id="74250-166">The settings are local because they are not published as part of the security policy of the service and do not affect the client's binding.</span></span>  
  
 <span data-ttu-id="74250-167">`localServiceSecuritySettings` 元素的下列属性有助于缓解拒绝服务 (DOS) 安全攻击：</span><span class="sxs-lookup"><span data-stu-id="74250-167">The following attributes of the `localServiceSecuritySettings` element can help mitigate a denial-of-service (DOS) security attack:</span></span>  
  
-   <span data-ttu-id="74250-168">`maxCachedCookies`：控制在执行 SPNEGO 或 SSL 协商之后服务器所缓存的有时限的 SecurityContextToken 的最大数目。</span><span class="sxs-lookup"><span data-stu-id="74250-168">`maxCachedCookies`: controls the maximum number of time-bounded SecurityContextTokens that are cached by the server after doing SPNEGO or SSL negotiation.</span></span>  
  
-   <span data-ttu-id="74250-169">`issuedCookieLifetime`：控制在进行 SPNEGO 或 SSL 协商之后服务器所发布的 SecurityContextToken 的生命周期。</span><span class="sxs-lookup"><span data-stu-id="74250-169">`issuedCookieLifetime`: controls the lifetime of the SecurityContextTokens that are issued by the server following SPNEGO or SSL negotiation.</span></span> <span data-ttu-id="74250-170">服务器在此段时间之内缓存 SecurityContextToken。</span><span class="sxs-lookup"><span data-stu-id="74250-170">The server caches the SecurityContextTokens for this period of time.</span></span>  
  
-   <span data-ttu-id="74250-171">`maxPendingSessions`：控制在服务器上建立但尚未针为其处理任何应用程序消息的安全对话的最大数目。</span><span class="sxs-lookup"><span data-stu-id="74250-171">`maxPendingSessions`: controls the maximum number of secure conversations that are established at the server but for which no application messages have been processed.</span></span> <span data-ttu-id="74250-172">此配额可防止客户端在服务上建立安全对话而导致服务维护每个客户端的状态，但是从不使用这些状态。</span><span class="sxs-lookup"><span data-stu-id="74250-172">This quota prevents clients from establishing secure conversations at the service, thereby causing the service to maintain state for each client, but never using them.</span></span>  
  
-   <span data-ttu-id="74250-173">`inactivityTimeout`：控制服务使安全对话保持活动状态（但不接收服务上的应用程序消息）的最长时间。</span><span class="sxs-lookup"><span data-stu-id="74250-173">`inactivityTimeout`: controls the maximum time that the service keeps a secure conversation alive without ever receiving an application message on it.</span></span> <span data-ttu-id="74250-174">此配额可防止客户端在服务上建立安全对话而导致服务维护每个客户端的状态，但是从不使用这些状态。</span><span class="sxs-lookup"><span data-stu-id="74250-174">This quota prevents clients from establishing secure conversations at the service, thereby causing the service to maintain state for each client, but never using them.</span></span>  
  
 <span data-ttu-id="74250-175">请注意，在安全对话会话中，绑定上的 `inactivityTimeout` 和 `receiveTimeout` 属性将影响会话超时。</span><span class="sxs-lookup"><span data-stu-id="74250-175">In a secure conversation session, note that both `inactivityTimeout` and the `receiveTimeout` attributes on the binding affect session timeout.</span></span> <span data-ttu-id="74250-176">两个属性中时间较短者将确定何时发生超时。</span><span class="sxs-lookup"><span data-stu-id="74250-176">The shorter of the two determines when timeouts occur.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74250-177">请参阅</span><span class="sxs-lookup"><span data-stu-id="74250-177">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.LocalServiceSettings%2A>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A>  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="74250-178">绑定</span><span class="sxs-lookup"><span data-stu-id="74250-178">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="74250-179">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="74250-179">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="74250-180">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="74250-180">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="74250-181">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="74250-181">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="74250-182">如何：创建自定义绑定使用 SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="74250-182">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="74250-183">自定义绑定安全性</span><span class="sxs-lookup"><span data-stu-id="74250-183">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
