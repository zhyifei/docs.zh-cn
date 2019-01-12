---
title: '&lt;useManagedPresentation&gt;'
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: a60e1e16b9b41cc5df4ded51cc05d6109dd7b3dc
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147702"
---
# <a name="ltusemanagedpresentationgt"></a>&lt;useManagedPresentation&gt;
一个绑定元素，用于与支持 WS-Trust 的 CardSpace 配置文件的 CardSpace 安全令牌服务进行通信。 此元素没有属性并且以空开关形式存在。  
  
 \<system.serviceModel>  
\<绑定 >  
\<customBinding>  
\<绑定 >  
\<useManagedPresentation >  
  
## <a name="syntax"></a>语法  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<绑定 >](../../../../../docs/framework/misc/binding.md)|定义自定义绑定的所有绑定功能。|  
  
## <a name="remarks"></a>备注  
 标识提供程序使用此元素，用以在它的策略中表明它支持 WS-Trust 的 CardSpace 配置文件这一事实。 发布这种策略断言的标识提供程序应该能够基于该 CardSpace 配置文件颁发令牌。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>  
 <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [绑定](../../../../../docs/framework/wcf/bindings.md)  
 [扩展绑定](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [自定义绑定](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
