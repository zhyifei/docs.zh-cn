---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: a5c773ea91de882920775ac8dc0ecc1da68a6c9f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738788"
---
# <a name="oneway"></a>\<单向 >
对自定义绑定启用数据包路由并使用单向方法。  
  
[ **\<configuration>** ](../configuration-element.md)\
\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) \
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<单向 >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`packetRoutable`|一个布尔值，指定是否启用数据包路由。 默认值为 `false`。|  
|`MaxAcceptedChannels`|一个整数，指定可接受的最大通道数。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<channelPoolSettings >](channelpoolsettings.md)|一个 <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> 对象，包含当前通道的通道池的属性。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<binding >](bindings.md)|定义自定义绑定的所有绑定功能。|  
  
## <a name="remarks"></a>备注  
 若要启用数据包路由，必须使用此元素提供的单向转换层。 用户可以创建一个自定义绑定，将此绑定置于具有会话功能或请求/答复传输的上层，使之可进行数据包路由。 如果希望以更自然的方式公开单向方法，则此元素也十分有用。 在这一层上可应用更多的转换，如复合双工和可靠消息。  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [绑定](../../../wcf/bindings.md)
- [扩展绑定](../../../wcf/extending/extending-bindings.md)
- [自定义绑定](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
