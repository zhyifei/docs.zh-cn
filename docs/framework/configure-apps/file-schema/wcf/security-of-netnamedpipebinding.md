---
title: '&lt;netNamedPipeBinding&gt; 的 &lt;security&gt;'
ms.date: 03/30/2017
ms.assetid: bb3cb022-637e-49fd-92e8-6766038affa7
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 74bf0d14b0acfd8a5382575d2ee1e51174b6b6b8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752788"
---
# <a name="ltsecuritygt-of-ltnetnamedpipebindinggt"></a>&lt;netNamedPipeBinding&gt; 的 &lt;security&gt;
定义绑定的安全设置。  
  
 \<system.ServiceModel>  
\<绑定 >  
\<netNamedPipeBinding>  
\<绑定 >  
\<安全 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<netNamedPipeBinding>  
      <binding>  
            <security mode="None/Transport">  
                        <transport protectionLevel="None/Sign/EncryptAndSign" />  
            </security>  
      </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|mode|指定应用于此绑定的安全类型。 包括以下有效值：<br /><br /> -None： 禁用安全性。<br />-传输： 使用基础的基于的传输安全提供安全性。 可以通过此模式来控制保护级别。<br />-默认值为 Transport。 此属性的类型为 <xref:System.ServiceModel.NetNamedPipeSecurityMode>。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|传输|定义传输的安全设置。 此元素的类型为 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|绑定|绑定元素[ \<netNamedPipeBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.NetNamedPipeSecurity>  
 <xref:System.ServiceModel.NetNamedPipeBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement>  
 [保护服务和客户端的安全](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [选择凭据类型](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [绑定](../../../../../docs/framework/wcf/bindings.md)  
 [配置系统提供的绑定](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [使用绑定来配置 Windows Communication Foundation 服务和客户端](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<绑定 >](../../../../../docs/framework/misc/binding.md)
