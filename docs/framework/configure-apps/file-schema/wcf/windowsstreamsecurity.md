---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: dab8505a9ddb348a6f7fe16ae9acb3a0119a8b06
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735896"
---
# <a name="windowsstreamsecurity"></a>\<Windowsstreamsecurity 正在 >
指定自定义绑定的 Windows 流安全设置。  
  
[ **\<configuration>** ](../configuration-element.md)\
\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) \
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<windowsstreamsecurity 正在 >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|protectionLevel|定义消息级安全性。 对消息进行签名可以降低该消息在传输过程中被第三方篡改的风险。 加密可以在传输过程中提供数据级保密。 包括以下有效值：<br /><br /> -None：无保护。<br />-Sign：对消息进行签名。<br />-EncryptAndSign：对消息进行签名和加密。<br /><br /> 默认值为 EncryptAndSign。<br /><br /> 此属性的类型为 <xref:System.Net.Security.ProtectionLevel>。|  
  
### <a name="child-elements"></a>子元素  
 None  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<binding >](bindings.md)|定义自定义绑定的所有绑定功能。|  
  
## <a name="remarks"></a>备注  
 使用面向流协议（如 TCP 和命名管道）的传输支持基于流的传输升级。 特别是 WCF 提供了安全升级。 此传输安全的配置由此配置元素以及可配置并添加到自定义绑定的[\<custombinding> sslstreamsecurity> >](sslstreamsecurity.md)进行封装。  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [绑定](../../../wcf/bindings.md)
- [扩展绑定](../../../wcf/extending/extending-bindings.md)
- [自定义绑定](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
