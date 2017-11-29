---
title: "&lt;windowsstreamsecurity 正在&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 5a0d3b61f473b49abdb2470a9fa5381dc9929274
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltwindowsstreamsecuritygt"></a>&lt;windowsstreamsecurity 正在&gt;
指定自定义绑定的 Windows 流安全设置。  
  
 \<system.serviceModel >  
\<绑定 >  
\<customBinding >  
\<绑定 >  
\<windowsstreamsecurity 正在 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|protectionLevel|定义消息级安全性。 对消息进行签名可以降低该消息在传输过程中被第三方篡改的风险。 加密可以在传输过程中提供数据级保密。 包括以下有效值：<br /><br /> -None： 无保护。<br />-Sign： 消息进行签名。<br />-EncryptAndSign： 消息签名并加密。<br /><br /> 默认值为 EncryptAndSign。<br /><br /> 此属性的类型为 <xref:System.Net.Security.ProtectionLevel>。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<绑定 >](../../../../../docs/framework/misc/binding.md)|定义自定义绑定的所有绑定功能。|  
  
## <a name="remarks"></a>备注  
 使用面向流协议（如 TCP 和命名管道）的传输支持基于流的传输升级。 特别是 WCF 提供了安全升级。 此配置元素包装以及通过此传输安全配置[ \<sslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)，可以将配置并将添加到自定义绑定  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
 [绑定](../../../../../docs/framework/wcf/bindings.md)  
 [扩展绑定](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [自定义绑定](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
