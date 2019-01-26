---
title: '&lt;headers&gt;'
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: f47462ba63b9bd8868420ee9d3a320ba18c83c65
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557820"
---
# <a name="ltheadersgt"></a>&lt;headers&gt;
除了其基本 URI 外，终结点可以按一个或多个 SOAP 标头寻址。 这一点在其中很有用的一组方案是一组 SOAP 媒介方案，其中终结点要求该终结点的客户端包括以媒介为目标的 SOAP 头。 此配置元素可用于定义此类自定义地址标头。 终结点标头集合中的项是用户定义的 XML 元素。 每个元素必须是格式良好的 XML。  
  
 \<system.ServiceModel>  
\<client>  
\<endpoint>  
  
## <a name="syntax"></a>语法  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
 用户定义的 XML 元素。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|配置不同类型的终结点。|  
  
## <a name="remarks"></a>备注  
 可选标头提供用于标识终结点或与终结点交互的更多详细寻址信息。 例如，标头可指示如何处理传入消息，终结点应发送答复消息的位置，或在多个实例可用时应使用哪个服务实例处理来自特定用户的传入消息。  
  
## <a name="see-also"></a>请参阅
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [终结点：地址、 绑定和协定](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
