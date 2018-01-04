---
title: "如何：创建双工联合绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5d40d13ca861cd18cf5f2a72e94d1aca146c2c19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="d5e89-102">如何：创建双工联合绑定</span><span class="sxs-lookup"><span data-stu-id="d5e89-102">How to: Create a Duplex Federated Binding</span></span>
<span data-ttu-id="d5e89-103"><xref:System.ServiceModel.WSFederationHttpBinding> 仅支持数据报和请求/答复消息交换协定。</span><span class="sxs-lookup"><span data-stu-id="d5e89-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="d5e89-104">若要使用双工消息交换协定，必须创建自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="d5e89-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="d5e89-105">下面的过程演示如何使用 HTTP 和 TCP 传输协议的消息模式安全设置，以及使用 TCP 传输协议的混合模式安全设置，在配置中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d5e89-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="d5e89-106">本主题的结尾是演示所有 3 个绑定的示例代码。</span><span class="sxs-lookup"><span data-stu-id="d5e89-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>  
  
 <span data-ttu-id="d5e89-107">还可以在代码中创建绑定。</span><span class="sxs-lookup"><span data-stu-id="d5e89-107">You can also create the binding in code.</span></span> <span data-ttu-id="d5e89-108">要创建的绑定元素堆栈的说明，请参阅[如何： 自定义绑定使用 SecurityBindingElement 创建](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)。</span><span class="sxs-lookup"><span data-stu-id="d5e89-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="d5e89-109">使用 HTTP 创建双工联合自定义绑定</span><span class="sxs-lookup"><span data-stu-id="d5e89-109">To create a duplex federated custom binding with HTTP</span></span>  
  
1.  <span data-ttu-id="d5e89-110">在[\<绑定 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)节点的配置文件中，创建[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="d5e89-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>  
  
2.  <span data-ttu-id="d5e89-111">内部[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)元素，创建[\<绑定 >](../../../../docs/framework/misc/binding.md)具有元素`name`属性设置为`FederationDuplexHttpMessageSecurityBinding`。</span><span class="sxs-lookup"><span data-stu-id="d5e89-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>  
  
3.  <span data-ttu-id="d5e89-112">内部[\<绑定 >](../../../../docs/framework/misc/binding.md)元素，创建[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)具有元素`authenticationMode`属性设置为`SecureConversation`。</span><span class="sxs-lookup"><span data-stu-id="d5e89-112">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4.  <span data-ttu-id="d5e89-113">内部[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)元素，创建[ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)具有元素`authenticationMode`属性设置为`IssuedTokenForCertificate`或`IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="d5e89-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5.  <span data-ttu-id="d5e89-114">以下[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)元素，创建一个空[ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)元素。</span><span class="sxs-lookup"><span data-stu-id="d5e89-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>  
  
6.  <span data-ttu-id="d5e89-115">以下[ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)元素，创建一个空[ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)元素。</span><span class="sxs-lookup"><span data-stu-id="d5e89-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>  
  
7.  <span data-ttu-id="d5e89-116">以下[ \<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)元素，创建一个空[ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)元素。</span><span class="sxs-lookup"><span data-stu-id="d5e89-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="d5e89-117">使用 TCP 消息安全模式创建双工联合自定义绑定</span><span class="sxs-lookup"><span data-stu-id="d5e89-117">To create a duplex federated custom binding with TCP message security mode</span></span>  
  
1.  <span data-ttu-id="d5e89-118">在[\<绑定 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)节点的配置文件中，创建[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="d5e89-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2.  <span data-ttu-id="d5e89-119">内部[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)元素，创建[\<绑定 >](../../../../docs/framework/misc/binding.md)具有元素`name`属性设置为`FederationDuplexTcpMessageSecurityBinding`。</span><span class="sxs-lookup"><span data-stu-id="d5e89-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>  
  
3.  <span data-ttu-id="d5e89-120">内部[\<绑定 >](../../../../docs/framework/misc/binding.md)元素，创建[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)具有元素`authenticationMode`属性设置为`SecureConversation`。</span><span class="sxs-lookup"><span data-stu-id="d5e89-120">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4.  <span data-ttu-id="d5e89-121">内部[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)元素，创建[ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)具有元素`authenticationMode`属性设置为`IssuedTokenForCertificate`或`IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="d5e89-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5.  <span data-ttu-id="d5e89-122">以下[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)元素，创建一个空[ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md)元素。</span><span class="sxs-lookup"><span data-stu-id="d5e89-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
### <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="d5e89-123">使用 TCP 混合安全模式创建双工联合自定义绑定</span><span class="sxs-lookup"><span data-stu-id="d5e89-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>  
  
1.  <span data-ttu-id="d5e89-124">在[\<绑定 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)节点的配置文件中，创建[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="d5e89-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>   
  
2.  <span data-ttu-id="d5e89-125">内部[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)元素，创建[\<绑定 >](../../../../docs/framework/misc/binding.md)具有元素`name`属性设置为`FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`。</span><span class="sxs-lookup"><span data-stu-id="d5e89-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>  
  
3.  <span data-ttu-id="d5e89-126">内部[\<绑定 >](../../../../docs/framework/misc/binding.md)元素，创建[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)具有元素`authenticationMode`属性设置为`SecureConversation`。</span><span class="sxs-lookup"><span data-stu-id="d5e89-126">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>  
  
4.  <span data-ttu-id="d5e89-127">内部[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)元素，创建[ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)具有元素`authenticationMode`属性设置为`IssuedTokenForCertificate`或`IssuedTokenForSslNegotiated`.</span><span class="sxs-lookup"><span data-stu-id="d5e89-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>  
  
5.  <span data-ttu-id="d5e89-128">以下[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)元素，创建一个空[ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)元素。</span><span class="sxs-lookup"><span data-stu-id="d5e89-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>  
  
6.  <span data-ttu-id="d5e89-129">以下[ \<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)元素，创建一个空[ \<tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md)元素。</span><span class="sxs-lookup"><span data-stu-id="d5e89-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>  
  
## <a name="code-sample"></a><span data-ttu-id="d5e89-130">代码示例</span><span class="sxs-lookup"><span data-stu-id="d5e89-130">Code Sample</span></span>  
  
#### <a name="sample-with-3-bindings"></a><span data-ttu-id="d5e89-131">包含 3 个绑定的示例</span><span class="sxs-lookup"><span data-stu-id="d5e89-131">Sample with 3 Bindings</span></span>  
  
1.  <span data-ttu-id="d5e89-132">将以下代码插入到配置文件中。</span><span class="sxs-lookup"><span data-stu-id="d5e89-132">Insert the following code into your configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5e89-133">示例</span><span class="sxs-lookup"><span data-stu-id="d5e89-133">Example</span></span>  
  
```xml  
<bindings>  
   <customBinding>  
      <binding name="FederationDuplexHttpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <compositeDuplex />  
          <oneWay />  
          <httpTransport />  
       </binding>  
<!-- duplex over https is not supported -->  
       <binding name="FederationDuplexTcpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <tcpTransport />  
       </binding>              
       <binding name="FederationDuplexTcpTransportSecurityWithMessageCredentialsBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenOverTransport" />  
          </security>  
<!-- requireClientCertificate = true or <windowsStreamSecurity /> can be used, but does not make sense for most scenarios -->  
          <sslStreamSecurity />  
          <tcpTransport />  
       </binding>              
    </customBinding>  
</bindings>  
```
