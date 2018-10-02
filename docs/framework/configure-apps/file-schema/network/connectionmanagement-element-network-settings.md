---
title: '&lt;connectionManagement&gt;元素 （网络设置）'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
author: mcleblanc
ms.author: markl
ms.openlocfilehash: bc0b75db5b3f35087df70c9155a1ba3b39ceae4d
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028415"
---
# <a name="ltconnectionmanagementgt-element-network-settings"></a>&lt;connectionManagement&gt;元素 （网络设置）
指定到网络主机的最大连接数。  
  
 \<configuration>  
\<system.net>  
\<connectionManagement >  
  
## <a name="syntax"></a>语法  
  
```xml  
<connectionManagement>   
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[add](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-connectionmanagement-network-settings.md)|将 IP 地址或 DNS 名称添加到连接管理列表。|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-connectionmanagement-network-settings.md)|清除连接管理列表。|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-connectionmanagement-network-settings.md)|从连接管理列表中删除 IP 地址或 DNS 名称。|  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|包含指定 .NET Framework 如何连接到网络的设置。|  
  
## <a name="remarks"></a>备注  
 `connectionManagement`元素到服务器或服务器组中定义的最大连接数。  
  
## <a name="configuration-files"></a>配置文件  
 此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。  
  
## <a name="example"></a>示例  
 下面的示例配置应用程序使用与服务器 www.contoso.com 的四个连接和两个连接到所有其他服务器。  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [网络设置架构](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
