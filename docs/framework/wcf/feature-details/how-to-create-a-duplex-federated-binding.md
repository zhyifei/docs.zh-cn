---
title: 如何：创建双工联合绑定
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 71c970fa45d7d4ccd55fceddb2360d0aa0a768f8
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972058"
---
# <a name="how-to-create-a-duplex-federated-binding"></a><span data-ttu-id="80440-102">如何：创建双工联合绑定</span><span class="sxs-lookup"><span data-stu-id="80440-102">How to: Create a Duplex Federated Binding</span></span>

<span data-ttu-id="80440-103"><xref:System.ServiceModel.WSFederationHttpBinding> 仅支持数据报和请求/答复消息交换协定。</span><span class="sxs-lookup"><span data-stu-id="80440-103"><xref:System.ServiceModel.WSFederationHttpBinding> only supports the datagram and request/reply message exchange contracts.</span></span> <span data-ttu-id="80440-104">若要使用双工消息交换协定，必须创建自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="80440-104">To use the duplex message exchange contract, you must create a custom binding.</span></span> <span data-ttu-id="80440-105">下面的过程演示如何使用 HTTP 和 TCP 传输协议的消息模式安全设置，以及使用 TCP 传输协议的混合模式安全设置，在配置中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="80440-105">The following procedures show how to do this in configuration, using Message mode security for the HTTP and TCP transports, and using mixed mode security for the TCP transport.</span></span> <span data-ttu-id="80440-106">本主题的结尾是演示所有 3 个绑定的示例代码。</span><span class="sxs-lookup"><span data-stu-id="80440-106">Sample code showing all 3 bindings is at the end of this topic.</span></span>

<span data-ttu-id="80440-107">还可以在代码中创建绑定。</span><span class="sxs-lookup"><span data-stu-id="80440-107">You can also create the binding in code.</span></span> <span data-ttu-id="80440-108">有关要创建的绑定元素堆栈的说明, 请参阅[如何:使用 SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)创建自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="80440-108">For a description of the binding elements stack to create, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a><span data-ttu-id="80440-109">使用 HTTP 创建双工联合自定义绑定</span><span class="sxs-lookup"><span data-stu-id="80440-109">To create a duplex federated custom binding with HTTP</span></span>

1. <span data-ttu-id="80440-110">在配置文件的[绑定>"节点中,创建一个customBinding>元素。\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="80440-110">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="80440-111">[ \<](../../../../docs/framework/misc/binding.md) `name` `FederationDuplexHttpMessageSecurityBinding` [在customBinding>元素中,创建一个将属性设置为\<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)的绑定 > 元素。</span><span class="sxs-lookup"><span data-stu-id="80440-111">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexHttpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="80440-112">[ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) `authenticationMode` `SecureConversation` [在绑定>元素中,创建一个属性设置为\<](../../../../docs/framework/misc/binding.md)的安全 > 元素。</span><span class="sxs-lookup"><span data-stu-id="80440-112">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="80440-113">`IssuedTokenForSslNegotiated` `IssuedTokenForCertificate` `authenticationMode` [在security>元素中,创建一个属性设置为或的secureConversationBootstrap>元素。\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)</span><span class="sxs-lookup"><span data-stu-id="80440-113">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="80440-114">按照 security > 元素, 创建一个空[ \<的 compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)元素。 [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="80440-114">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element.</span></span>

6. <span data-ttu-id="80440-115">在[ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)元素的后面, 创建一个空[ \<的单向 >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)元素。</span><span class="sxs-lookup"><span data-stu-id="80440-115">Following the [\<compositeDuplex>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) element, create an empty [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element.</span></span>

7. <span data-ttu-id="80440-116">按照单向 > 元素, 创建一个空[ \<的 httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)元素。 [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)</span><span class="sxs-lookup"><span data-stu-id="80440-116">Following the [\<oneWay>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) element, create an empty [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a><span data-ttu-id="80440-117">使用 TCP 消息安全模式创建双工联合自定义绑定</span><span class="sxs-lookup"><span data-stu-id="80440-117">To create a duplex federated custom binding with TCP message security mode</span></span>

1. <span data-ttu-id="80440-118">在配置文件的[绑定>"节点中,创建一个customBinding>元素。\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="80440-118">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="80440-119">[ \<](../../../../docs/framework/misc/binding.md) `name` `FederationDuplexTcpMessageSecurityBinding` [在customBinding>元素中,创建一个将属性设置为\<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)的绑定 > 元素。</span><span class="sxs-lookup"><span data-stu-id="80440-119">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpMessageSecurityBinding`.</span></span>

3. <span data-ttu-id="80440-120">[ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) `authenticationMode` `SecureConversation` [在绑定>元素中,创建一个属性设置为\<](../../../../docs/framework/misc/binding.md)的安全 > 元素。</span><span class="sxs-lookup"><span data-stu-id="80440-120">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="80440-121">`IssuedTokenForSslNegotiated` `IssuedTokenForCertificate` `authenticationMode` [在security>元素中,创建一个属性设置为或的secureConversationBootstrap>元素。\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)</span><span class="sxs-lookup"><span data-stu-id="80440-121">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="80440-122">按照 security > 元素, 创建一个空[ \<的 tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md)元素。 [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="80440-122">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a><span data-ttu-id="80440-123">使用 TCP 混合安全模式创建双工联合自定义绑定</span><span class="sxs-lookup"><span data-stu-id="80440-123">To create a duplex federated custom binding with TCP mixed security mode</span></span>

1. <span data-ttu-id="80440-124">在配置文件的[绑定>"节点中,创建一个customBinding>元素。\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="80440-124">In the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) node of the configuration file, create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element.</span></span>

2. <span data-ttu-id="80440-125">[ \<](../../../../docs/framework/misc/binding.md) `name` `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` [在customBinding>元素中,创建一个将属性设置为\<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)的绑定 > 元素。</span><span class="sxs-lookup"><span data-stu-id="80440-125">Inside the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) element, create a [\<binding>](../../../../docs/framework/misc/binding.md) element with the `name` attribute set to `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`.</span></span>

3. <span data-ttu-id="80440-126">[ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) `authenticationMode` `SecureConversation` [在绑定>元素中,创建一个属性设置为\<](../../../../docs/framework/misc/binding.md)的安全 > 元素。</span><span class="sxs-lookup"><span data-stu-id="80440-126">Inside the [\<binding>](../../../../docs/framework/misc/binding.md) element, create a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element with the `authenticationMode` attribute set to `SecureConversation`.</span></span>

4. <span data-ttu-id="80440-127">`IssuedTokenForSslNegotiated` `IssuedTokenForCertificate` `authenticationMode` [在security>元素中,创建一个属性设置为或的secureConversationBootstrap>元素。\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)</span><span class="sxs-lookup"><span data-stu-id="80440-127">Inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element with the `authenticationMode` attribute set to `IssuedTokenForCertificate` or `IssuedTokenForSslNegotiated`.</span></span>

5. <span data-ttu-id="80440-128">按照 security > 元素, 创建一个空[ \<的 custombinding> sslstreamsecurity> >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)元素。 [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="80440-128">Following the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element, create an empty [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element.</span></span>

6. <span data-ttu-id="80440-129">在[ \<custombinding> sslstreamsecurity> >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)元素的后面, 创建一个空[ \<的 tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md)元素。</span><span class="sxs-lookup"><span data-stu-id="80440-129">Following the [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) element, create an empty [\<tcpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) element.</span></span>

## <a name="code-sample"></a><span data-ttu-id="80440-130">代码示例</span><span class="sxs-lookup"><span data-stu-id="80440-130">Code Sample</span></span>

### <a name="sample-with-3-bindings"></a><span data-ttu-id="80440-131">包含 3 个绑定的示例</span><span class="sxs-lookup"><span data-stu-id="80440-131">Sample with 3 Bindings</span></span>

1. <span data-ttu-id="80440-132">将以下代码插入到配置文件中。</span><span class="sxs-lookup"><span data-stu-id="80440-132">Insert the following code into your configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="80440-133">示例</span><span class="sxs-lookup"><span data-stu-id="80440-133">Example</span></span>

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
