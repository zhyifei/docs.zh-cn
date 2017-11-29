---
title: "&lt;servicePointManager&gt;元素 （网络设置）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#servicePointManager
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/servicePointManager
helpviewer_keywords:
- servicePointManager element
- <servicePointManager> element
ms.assetid: 6e5def51-3646-4ef6-a7bd-c69151321bec
caps.latest.revision: "16"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 85ccad3e2c3b237e286f3737589a5e58994521bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltservicepointmanagergt-element-network-settings"></a>&lt;servicePointManager&gt;元素 （网络设置）
配置对网络资源的连接。  
  
 \<configuration>  
\<system.net >  
\<设置 >  
\<servicePointManager >  
  
## <a name="syntax"></a>语法  
  
```xml  
<servicePointManager  
  checkCertificateName="true|false"  
  checkCertificateRevocationList="true|false"  
  encryptionPolicy="AllowNoEncryption|NoEncryption|RequireEncryption"  
  expect100Continue="true|false"  
  useNagleAlgorithm="true|false"  
  enableDnsRoundRobin="true|false"  
  dnsRefreshTimeout="time"  
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|**特性**|**描述**|  
|-------------------|---------------------|  
|`checkCertificateName`|指定系统是否应验证证书上的名称与之前使用的证书匹配服务器主机名。 默认值为 `true`。|  
|`checkCertificateRevocationList`|指定是否应检查系统，然后才能使用该证书是否已吊销证书。 默认值为 `false`。|  
|`dnsRefreshTimeout`|结合使用 DNS 轮循机制选项，以毫秒为单位指定时长域名服务 (DNS) 解析的缓存。 默认值是 120,000 毫秒（2 分钟）。|  
|`enableDnsRoundRobin`|指定是否具有多个返回的 Internet 协议 (IP) 地址名称的主机的 DNS 解析所有地址或只是第一个。 默认值为 `false`。|  
|`encryptionPolicy`|指定应用到的 SSL/TLS 会话上的加密策略<xref:System.Net.ServicePointManager>实例。 可能的值为等效的值<xref:System.Net.Security.EncryptionPolicy>枚举。 使用<xref:System.Security.Authentication.CipherAlgorithmType.Null>加密策略设置为时需要`NoEncryption`。 默认值为 `RequireEncryption`。|  
|`expect100Continue`|指定是否应该会 POST 方法接收`100-continue`从服务器的响应。 默认值为 `true`。|  
|`useNagleAlgorithm`|指定由服务点管理器控制的连接是否使用 Nagle 算法。 默认值为 `true`。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**描述**|  
|-----------------|---------------------|  
|[设置](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|配置 <xref:System.Net> 命名空间的基本网络选项。|  
  
## <a name="remarks"></a>备注  
  
## <a name="configuration-files"></a>配置文件  
 此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Net.ServicePointManager>  
 <xref:System.Net.Security.EncryptionPolicy>  
 [网络设置架构](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
