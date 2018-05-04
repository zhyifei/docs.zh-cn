---
title: '&lt;删除&gt;connectionManagement （网络设置） 的元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 8d503e06139fc6ce14f4d2c50c46e4bcfeb1b860
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltremovegt-element-for-connectionmanagement-network-settings"></a>&lt;删除&gt;connectionManagement （网络设置） 的元素
从连接管理列表中删除 IP 地址或 DNS 名称。  
  
 \<configuration>  
\<system.net>  
\<connectionManagement >  
\<remove>  
  
## <a name="syntax"></a>语法  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|**特性**|**说明**|  
|-------------------|---------------------|  
|`address`|IP 地址或 DNS 名称。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|指定到网络主机的最大连接数。|  
  
## <a name="remarks"></a>备注  
 `remove`元素中移除指定的服务器的连接管理列表项。  
  
 值`address`属性应为有效的 IP 地址或主机名。  
  
## <a name="configuration-files"></a>配置文件  
 此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。  
  
## <a name="example"></a>示例  
 下面的示例中移除服务器 www.adventure-works.com 所有连接管理列表条目，然后配置应用程序使用 4 个到 www.contoso.com 和两个连接到所有其他服务器。  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [网络设置架构](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
