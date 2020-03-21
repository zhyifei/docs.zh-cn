---
title: connectionManagement 的 <remove> 元素（网络设置）
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
ms.openlocfilehash: 39ce85c3c15a2d4bdfce801a35e9ca088bd5091b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154733"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a>\<删除连接管理的>元素（网络设置）
从连接管理列表中删除 IP 地址或 DNS 名称。  

[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<连接管理>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<删除>**

## <a name="syntax"></a>语法  
  
```xml  
<remove
  address="server name or IP address"
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|**属性**|**说明**|  
|-------------------|---------------------|  
|`address`|IP 地址或 DNS 名称。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[connectionManagement](connectionmanagement-element-network-settings.md)|指定到网络主机的最大连接数。|  
  
## <a name="remarks"></a>备注  
 该`remove`元素将删除指定服务器的连接管理列表条目。  
  
 `address`属性的值应为有效的 IP 地址或主机名。  
  
## <a name="configuration-files"></a>配置文件  
 此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。  
  
## <a name="example"></a>示例  
 下面的示例删除服务器`www.adventure-works.com`的任何连接管理列表条目，然后将应用程序配置为使用到服务器`www.contoso.com`的四个连接和到所有其他服务器的两个连接。  
  
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
  
## <a name="see-also"></a>另请参阅

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [网络设置架构](index.md)
