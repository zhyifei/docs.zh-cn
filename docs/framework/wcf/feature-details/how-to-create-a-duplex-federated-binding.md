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
# <a name="how-to-create-a-duplex-federated-binding"></a>如何：创建双工联合绑定

<xref:System.ServiceModel.WSFederationHttpBinding> 仅支持数据报和请求/答复消息交换协定。 若要使用双工消息交换协定，必须创建自定义绑定。 下面的过程演示如何使用 HTTP 和 TCP 传输协议的消息模式安全设置，以及使用 TCP 传输协议的混合模式安全设置，在配置中执行此操作。 本主题的结尾是演示所有 3 个绑定的示例代码。

还可以在代码中创建绑定。 有关要创建的绑定元素堆栈的说明, 请参阅[如何:使用 SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)创建自定义绑定。

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a>使用 HTTP 创建双工联合自定义绑定

1. 在配置文件的[绑定>"节点中,创建一个customBinding>元素。\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

2. [ \<](../../../../docs/framework/misc/binding.md) `name` `FederationDuplexHttpMessageSecurityBinding` [在customBinding>元素中,创建一个将属性设置为\<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)的绑定 > 元素。

3. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) `authenticationMode` `SecureConversation` [在绑定>元素中,创建一个属性设置为\<](../../../../docs/framework/misc/binding.md)的安全 > 元素。

4. `IssuedTokenForSslNegotiated` `IssuedTokenForCertificate` `authenticationMode` [在security>元素中,创建一个属性设置为或的secureConversationBootstrap>元素。\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)

5. 按照 security > 元素, 创建一个空[ \<的 compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)元素。 [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)

6. 在[ \<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)元素的后面, 创建一个空[ \<的单向 >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)元素。

7. 按照单向 > 元素, 创建一个空[ \<的 httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)元素。 [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a>使用 TCP 消息安全模式创建双工联合自定义绑定

1. 在配置文件的[绑定>"节点中,创建一个customBinding>元素。\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

2. [ \<](../../../../docs/framework/misc/binding.md) `name` `FederationDuplexTcpMessageSecurityBinding` [在customBinding>元素中,创建一个将属性设置为\<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)的绑定 > 元素。

3. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) `authenticationMode` `SecureConversation` [在绑定>元素中,创建一个属性设置为\<](../../../../docs/framework/misc/binding.md)的安全 > 元素。

4. `IssuedTokenForSslNegotiated` `IssuedTokenForCertificate` `authenticationMode` [在security>元素中,创建一个属性设置为或的secureConversationBootstrap>元素。\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)

5. 按照 security > 元素, 创建一个空[ \<的 tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md)元素。 [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a>使用 TCP 混合安全模式创建双工联合自定义绑定

1. 在配置文件的[绑定>"节点中,创建一个customBinding>元素。\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

2. [ \<](../../../../docs/framework/misc/binding.md) `name` `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` [在customBinding>元素中,创建一个将属性设置为\<](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)的绑定 > 元素。

3. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) `authenticationMode` `SecureConversation` [在绑定>元素中,创建一个属性设置为\<](../../../../docs/framework/misc/binding.md)的安全 > 元素。

4. `IssuedTokenForSslNegotiated` `IssuedTokenForCertificate` `authenticationMode` [在security>元素中,创建一个属性设置为或的secureConversationBootstrap>元素。\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)

5. 按照 security > 元素, 创建一个空[ \<的 custombinding> sslstreamsecurity> >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)元素。 [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)

6. 在[ \<custombinding> sslstreamsecurity> >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)元素的后面, 创建一个空[ \<的 tcpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md)元素。

## <a name="code-sample"></a>代码示例

### <a name="sample-with-3-bindings"></a>包含 3 个绑定的示例

1. 将以下代码插入到配置文件中。

## <a name="example"></a>示例

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
