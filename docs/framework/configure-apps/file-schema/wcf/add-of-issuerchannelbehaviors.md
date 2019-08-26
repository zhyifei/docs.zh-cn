---
title: <add> 的 <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 325d6b8111115384b18547bd11ccec8a4a8af711
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920115"
---
# <a name="add-of-issuerchannelbehaviors"></a>\<添加 issuerChannelBehaviors > \<的 >

添加在与 STS 进行通信时要使用的终结点行为。

> [!NOTE]
> 如果任何终结点行为包含[ \<clientCredentials >](clientcredentials.md)元素, 则会引发异常。

\<system.ServiceModel>\
\<行为 > \
endpointBehaviors 部分\<行为 > \
\<clientCredentials > \
\<issuedToken > \
\<issuerChannelBehaviors > 元素 \
\<add>

## <a name="syntax"></a>语法

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a>特性和元素

以下几节描述了特性、子元素和父元素。

### <a name="attributes"></a>特性

|特性|描述|
|---------------|-----------------|
|issuerAddress|要与之通信的安全令牌颁发者的 URI。|
|behaviorConfiguration|在同一个配置文件中定义的终结点行为的名称。|

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)|包含与指定的服务令牌服务通信时要使用的 Windows Communication Foundation (WCF) 客户端终结点行为的集合。|

## <a name="remarks"></a>备注

`issuerAddress` 包含客户端希望与之进行通信的安全令牌服务的 URI。 `behaviorConfiguration`指向应用程序在 Windows Communication Foundation (WCF) 创建的通道中使用的终结点行为, 以从安全令牌服务获取已颁发的令牌。

## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [服务标识和身份验证](../../../wcf/feature-details/service-identity-and-authentication.md)
- [安全行为](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [联合令牌与颁发的令牌](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [保护服务和客户端的安全](../../../wcf/feature-details/securing-services-and-clients.md)
- [保护客户端](../../../wcf/securing-clients.md)
- [如何：创建联合客户端](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [如何：配置本地颁发者](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [联合令牌与颁发的令牌](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)
