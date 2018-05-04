---
title: '&lt;pnrpPeerResolver&gt;'
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: f0874d38c3432f066d1bec5cc84f53e1f3730180
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltpnrppeerresolvergt"></a>&lt;pnrpPeerResolver&gt;
指定要将 PNRP（对等名称解析协议）解析程序用作解析程序。 此元素是可选的，因为 PNRP 是默认解析程序。  
  
 \<system.serviceModel>  
\<绑定 >  
\<customBinding>  
\<绑定 >  
\<pnrpResolver >  
  
## <a name="syntax"></a>语法  
  
```xml  
<pnrpResolver resolverType="String" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|resolverType|一个字符串，指定要使用的解析程序。 此属性是可选的。 如果不设置，或者将其设置为空字符串，则使用 PNRP。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<绑定 >](../../../../../docs/framework/misc/binding.md)|定义自定义绑定的所有绑定功能。|  
  
## <a name="example"></a>示例  
  
```xml  
<pnrpResolver resolverType="" />  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>  
 <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [绑定](../../../../../docs/framework/wcf/bindings.md)  
 [扩展绑定](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [自定义绑定](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [对等解析程序](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
