---
title: "&lt;smtp&gt;元素 （网络设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: f5b2a3b7eec17fbdd12181c29f610d2b2ad32bd4
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="ltsmtpgt-element-network-settings"></a>&lt;smtp&gt;元素 （网络设置）
配置传递格式、 传递方法和发件人发送电子邮件地址。  
  
 \<configuration>  
\<system.net>  
\<mailSettings>  
\<smtp>  
  
## <a name="syntax"></a>语法  
  
```xml  
      <smtp  
        deliveryFormat="format"   
        deliveryMethod="method"   
        from="from address">
          <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
          <network> … </network>  
      </smtp>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`deliveryFormat`|指定传出电子邮件的传送格式。 可接受的值为 SevenBit 和 International。|  
|`deliveryMethod`|指定电子邮件的传递方法。 可接受的值是网络、 pickupDirectoryFromIis 和 specifiedPickupDirectory。|  
|`from`|指定发件人的传出电子邮件地址。|  
  
### <a name="child-elements"></a>子元素  
  
|特性|描述|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|配置简单邮件传输协议 (SMTP) 服务器的本地目录。|  
|`network`|配置外部的 SMTP 服务器的网络选项。|  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[\<mailSettings> 元素（网络设置）](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|配置邮件发送选项。|  
  
## <a name="example"></a>示例  
 下面的示例指定适当的 SMTP 参数，以使用默认网络凭据发送电子邮件。  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpDeliveryFormat>  
 <xref:System.Net.Mail.SmtpDeliveryMethod>  
 [网络设置架构](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
