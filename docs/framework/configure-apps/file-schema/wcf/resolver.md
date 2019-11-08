---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 0dc667f392595d895bd4f2773ab69777d7369446
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738738"
---
# <a name="resolver"></a>\<解析程序 >
指定对等解析程序，对等解析程序用于将对等网格 ID 解析为一组对等节点地址，这些地址表示参与网格的若干节点。  
  
[ **\<configuration>** ](../configuration-element.md)\
\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) \
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<解析程序 >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`mode`|一个字符串，指定与此服务关联的对等解析程序实例是特定于 PNRP，还是为自定义解析程序，或者是自动确定的。 此属性的类型为 <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>。|  
|`referralPolicy`|一个字符串，指定在对等端间共享引用的方式。 此属性的类型为 <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<标头 >](headers.md)|指定自定义对等解析程序服务的设置。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<binding >](bindings.md)|定义[\<netPeerTcpBinding >](netpeertcpbinding.md)的所有绑定功能。|  
  
## <a name="remarks"></a>备注  
 对等名解析程序是对等通道用于查找参与对等网格的对等节点的发现服务。 它还可以用于在对等网格中“注册”节点，即对等节点在对等网格中变为已知和可用的机制。 有关对等解析程序的详细信息，请参阅[对等解析](../../../wcf/feature-details/peer-resolvers.md)程序。  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [对等解析程序](../../../wcf/feature-details/peer-resolvers.md)
- [向 PeerChannel 应用程序添加自定义冲突解决程序](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))
