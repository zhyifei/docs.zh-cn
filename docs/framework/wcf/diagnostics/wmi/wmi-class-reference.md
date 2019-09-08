---
title: WMI 类引用
ms.date: 03/30/2017
ms.assetid: b95a51f5-8251-4619-ae05-7de88cb90f9a
ms.openlocfilehash: 226e4dedecd152f3a3d4143280529c7823339932
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795871"
---
# <a name="wmi-class-reference"></a><span data-ttu-id="dc3fe-102">WMI 类引用</span><span class="sxs-lookup"><span data-stu-id="dc3fe-102">WMI Class Reference</span></span>
<span data-ttu-id="dc3fe-103">本部分列出了 Windows Communication Foundation （WCF） WMI 提供程序公开的所有 WMI 类。</span><span class="sxs-lookup"><span data-stu-id="dc3fe-103">This section lists all the WMI classes exposed by the Windows Communication Foundation (WCF) WMI provider.</span></span>  
  
## <a name="accessing-wmi-instances"></a><span data-ttu-id="dc3fe-104">访问 WMI 实例</span><span class="sxs-lookup"><span data-stu-id="dc3fe-104">Accessing WMI Instances</span></span>  
 <span data-ttu-id="dc3fe-105">除 Service、AppDomain、Contract、ServiceAppDomain、ServiceToEndpointAssociation 和 Endpoint 外，不能直接实例化 WMI 对象引用中列出的所有类。</span><span class="sxs-lookup"><span data-stu-id="dc3fe-105">All the classes listed in the WMI Object Reference cannot be directly instantiated, except for Service, AppDomain, Contract, ServiceAppDomain, ServiceToEndpointAssociation and Endpoint.</span></span> <span data-ttu-id="dc3fe-106">若要访问其他实例，则可以访问上述顶级类的属性。</span><span class="sxs-lookup"><span data-stu-id="dc3fe-106">To access other instances, you can access the properties of the previously mentioned top level classes.</span></span> <span data-ttu-id="dc3fe-107">例如，你可以从终结点实例-> Binding-> Bindingelement 访问 TransportBindingElement 实例。</span><span class="sxs-lookup"><span data-stu-id="dc3fe-107">For example, you can access the TransportBindingElement instance from the Endpoint instance -> Binding -> BindingElements.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dc3fe-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="dc3fe-108">In This Section</span></span>  
 [<span data-ttu-id="dc3fe-109">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="dc3fe-109">ActivityTransfer</span></span>](activitytransfer.md)  
  
 [<span data-ttu-id="dc3fe-110">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="dc3fe-110">AppDomainInfo</span></span>](appdomaininfo.md)  
  
 [<span data-ttu-id="dc3fe-111">AspNetCompatibilityRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="dc3fe-111">AspNetCompatibilityRequirementsAttribute</span></span>](aspnetcompatibilityrequirementsattribute.md)  
  
 [<span data-ttu-id="dc3fe-112">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-112">AsymmetricSecurityBindingElement</span></span>](asymmetricsecuritybindingelement.md)  
  
 <span data-ttu-id="dc3fe-113">"行为类"</span><span class="sxs-lookup"><span data-stu-id="dc3fe-113">"Behavior class"</span></span>  
  
 [<span data-ttu-id="dc3fe-114">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-114">BinaryMessageEncodingBindingElement</span></span>](binarymessageencodingbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-115">绑定</span><span class="sxs-lookup"><span data-stu-id="dc3fe-115">Binding</span></span>](binding.md)  
  
 [<span data-ttu-id="dc3fe-116">BindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-116">BindingElement</span></span>](bindingelement.md)  
  
 [<span data-ttu-id="dc3fe-117">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="dc3fe-117">CallbackBehavior</span></span>](callbackbehavior.md)  
  
 [<span data-ttu-id="dc3fe-118">Channel 类</span><span class="sxs-lookup"><span data-stu-id="dc3fe-118">Channel class</span></span>](channel-class.md)  
  
 [<span data-ttu-id="dc3fe-119">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="dc3fe-119">ChannelPoolSettings</span></span>](channelpoolsettings.md)  
  
 [<span data-ttu-id="dc3fe-120">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="dc3fe-120">ClientCredentials</span></span>](clientcredentials.md)  
  
 [<span data-ttu-id="dc3fe-121">ClientViaBehavior</span><span class="sxs-lookup"><span data-stu-id="dc3fe-121">ClientViaBehavior</span></span>](clientviabehavior.md)  
  
 [<span data-ttu-id="dc3fe-122">CompositeDuplexBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-122">CompositeDuplexBindingElement</span></span>](compositeduplexbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-123">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-123">ConnectionOrientedTransportBindingElement</span></span>](connectionorientedtransportbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-124">协定</span><span class="sxs-lookup"><span data-stu-id="dc3fe-124">Contract</span></span>](contract.md)  
  
 [<span data-ttu-id="dc3fe-125">CustomBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-125">CustomBindingElement</span></span>](custombindingelement.md)  
  
 [<span data-ttu-id="dc3fe-126">DeliveryRequirementsAttribute</span><span class="sxs-lookup"><span data-stu-id="dc3fe-126">DeliveryRequirementsAttribute</span></span>](deliveryrequirementsattribute.md)  
  
 [<span data-ttu-id="dc3fe-127">终结点</span><span class="sxs-lookup"><span data-stu-id="dc3fe-127">Endpoint</span></span>](endpoint.md)  
  
 [<span data-ttu-id="dc3fe-128">HttpsTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-128">HttpsTransportBindingElement</span></span>](httpstransportbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-129">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-129">HttpTransportBindingElement</span></span>](httptransportbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-130">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="dc3fe-130">LocalServiceSecuritySettings</span></span>](localservicesecuritysettings.md)  
  
 [<span data-ttu-id="dc3fe-131">MatchAllEndpointBehavior</span><span class="sxs-lookup"><span data-stu-id="dc3fe-131">MatchAllEndpointBehavior</span></span>](matchallendpointbehavior.md)  
  
 [<span data-ttu-id="dc3fe-132">MessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-132">MessageEncodingBindingElement</span></span>](messageencodingbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-133">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="dc3fe-133">MsmqBindingElementBase</span></span>](msmqbindingelementbase.md)  
  
 [<span data-ttu-id="dc3fe-134">MsmqIntegrationBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-134">MsmqIntegrationBindingElement</span></span>](msmqintegrationbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-135">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-135">MsmqTransportBindingElement</span></span>](msmqtransportbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-136">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-136">MtomMessageEncodingBindingElement</span></span>](mtommessageencodingbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-137">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="dc3fe-137">MustUnderstandBehavior</span></span>](mustunderstandbehavior.md)  
  
 [<span data-ttu-id="dc3fe-138">NamedPipeConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="dc3fe-138">NamedPipeConnectionPoolSettings</span></span>](namedpipeconnectionpoolsettings.md)  
  
 [<span data-ttu-id="dc3fe-139">NamedPipeTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-139">NamedPipeTransportBindingElement</span></span>](namedpipetransportbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-140">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-140">OneWayBindingElement</span></span>](onewaybindingelement.md)  
  
 <span data-ttu-id="dc3fe-141">"Operation class"</span><span class="sxs-lookup"><span data-stu-id="dc3fe-141">"Operation class"</span></span>  
  
 [<span data-ttu-id="dc3fe-142">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="dc3fe-142">OperationBehaviorAttribute</span></span>](operationbehaviorattribute.md)  
  
 [<span data-ttu-id="dc3fe-143">PeerCustomResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-143">PeerCustomResolverBindingElement</span></span>](peercustomresolverbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-144">PeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-144">PeerResolverBindingElement</span></span>](peerresolverbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-145">PeerSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="dc3fe-145">PeerSecuritySettings</span></span>](peersecuritysettings.md)  
  
 [<span data-ttu-id="dc3fe-146">PeerTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-146">PeerTransportBindingElement</span></span>](peertransportbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-147">PeerTransportSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="dc3fe-147">PeerTransportSecuritySettings</span></span>](peertransportsecuritysettings.md)  
  
 [<span data-ttu-id="dc3fe-148">PnrpPeerResolverBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-148">PnrpPeerResolverBindingElement</span></span>](pnrppeerresolverbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-149">PrivacyNoticeBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-149">PrivacyNoticeBindingElement</span></span>](privacynoticebindingelement.md)  
  
 [<span data-ttu-id="dc3fe-150">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-150">ReliableSessionBindingElement</span></span>](reliablesessionbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-151">SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-151">SecurityBindingElement</span></span>](securitybindingelement.md)  
  
 [<span data-ttu-id="dc3fe-152">服务</span><span class="sxs-lookup"><span data-stu-id="dc3fe-152">Service</span></span>](service.md)  
  
 [<span data-ttu-id="dc3fe-153">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="dc3fe-153">ServiceAppDomain</span></span>](serviceappdomain.md)  
  
 [<span data-ttu-id="dc3fe-154">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="dc3fe-154">ServiceAuthorizationBehavior</span></span>](serviceauthorizationbehavior.md)  
  
 [<span data-ttu-id="dc3fe-155">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="dc3fe-155">ServiceBehaviorAttribute</span></span>](servicebehaviorattribute.md)  
  
 [<span data-ttu-id="dc3fe-156">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="dc3fe-156">ServiceCredentials</span></span>](servicecredentials.md)  
  
 [<span data-ttu-id="dc3fe-157">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="dc3fe-157">ServiceDebugBehavior</span></span>](servicedebugbehavior.md)  
  
 [<span data-ttu-id="dc3fe-158">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="dc3fe-158">ServiceMetadataBehavior</span></span>](servicemetadatabehavior.md)  
  
 [<span data-ttu-id="dc3fe-159">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="dc3fe-159">ServiceSecurityAuditBehavior</span></span>](servicesecurityauditbehavior.md)  
  
 [<span data-ttu-id="dc3fe-160">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="dc3fe-160">ServiceThrottlingBehavior</span></span>](servicethrottlingbehavior.md)  
  
 [<span data-ttu-id="dc3fe-161">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="dc3fe-161">ServiceTimeoutsBehavior</span></span>](servicetimeoutsbehavior.md)  
  
 [<span data-ttu-id="dc3fe-162">ServiceToEndpointAssociation</span><span class="sxs-lookup"><span data-stu-id="dc3fe-162">ServiceToEndpointAssociation</span></span>](servicetoendpointassociation.md)  
  
 [<span data-ttu-id="dc3fe-163">SslStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-163">SslStreamSecurityBindingElement</span></span>](sslstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="dc3fe-164">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-164">SymmetricSecurityBindingElement</span></span>](symmetricsecuritybindingelement.md)  
  
 [<span data-ttu-id="dc3fe-165">SynchronousReceiveBehavior</span><span class="sxs-lookup"><span data-stu-id="dc3fe-165">SynchronousReceiveBehavior</span></span>](synchronousreceivebehavior.md)  
  
 [<span data-ttu-id="dc3fe-166">TcpConnectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="dc3fe-166">TcpConnectionPoolSettings</span></span>](tcpconnectionpoolsettings.md)  
  
 [<span data-ttu-id="dc3fe-167">TcpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-167">TcpTransportBindingElement</span></span>](tcptransportbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-168">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-168">TextMessageEncodingBindingElement</span></span>](textmessageencodingbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-169">TraceListener</span><span class="sxs-lookup"><span data-stu-id="dc3fe-169">TraceListener</span></span>](tracelistener.md)  
  
 [<span data-ttu-id="dc3fe-170">TraceListenerArgument</span><span class="sxs-lookup"><span data-stu-id="dc3fe-170">TraceListenerArgument</span></span>](tracelistenerargument.md)  
  
 [<span data-ttu-id="dc3fe-171">TransactedBatchingBehavior</span><span class="sxs-lookup"><span data-stu-id="dc3fe-171">TransactedBatchingBehavior</span></span>](transactedbatchingbehavior.md)  
  
 [<span data-ttu-id="dc3fe-172">TransactionFlowAttribute</span><span class="sxs-lookup"><span data-stu-id="dc3fe-172">TransactionFlowAttribute</span></span>](transactionflowattribute.md)  
  
 [<span data-ttu-id="dc3fe-173">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-173">TransactionFlowBindingElement</span></span>](transactionflowbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-174">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-174">TransportBindingElement</span></span>](transportbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-175">TransportSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-175">TransportSecurityBindingElement</span></span>](transportsecuritybindingelement.md)  
  
 [<span data-ttu-id="dc3fe-176">UseManagedPresentationBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-176">UseManagedPresentationBindingElement</span></span>](usemanagedpresentationbindingelement.md)  
  
 [<span data-ttu-id="dc3fe-177">WindowsStreamSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="dc3fe-177">WindowsStreamSecurityBindingElement</span></span>](windowsstreamsecuritybindingelement.md)  
  
 [<span data-ttu-id="dc3fe-178">WSAT_TraceEvent</span><span class="sxs-lookup"><span data-stu-id="dc3fe-178">WSAT_TraceEvent</span></span>](wsat-traceevent.md)  
  
 [<span data-ttu-id="dc3fe-179">WSAT_TraceProvider</span><span class="sxs-lookup"><span data-stu-id="dc3fe-179">WSAT_TraceProvider</span></span>](wsat-traceprovider.md)  
  
 [<span data-ttu-id="dc3fe-180">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="dc3fe-180">WSAT_TraceRecord</span></span>](wsat-tracerecord.md)  
  
 [<span data-ttu-id="dc3fe-181">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="dc3fe-181">XmlDictionaryReaderQuotas</span></span>](xmldictionaryreaderquotas.md)  
  
 [<span data-ttu-id="dc3fe-182">XmlSerializerOperationBehavior</span><span class="sxs-lookup"><span data-stu-id="dc3fe-182">XmlSerializerOperationBehavior</span></span>](xmlserializeroperationbehavior.md)
