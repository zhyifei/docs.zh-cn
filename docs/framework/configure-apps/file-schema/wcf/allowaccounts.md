---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: c62f29c53d807cab397ff09c6163d924a71ea319
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926601"
---
# <a name="allowaccounts"></a>\<allowAccounts>
包含一个配置元素集合, 这些元素为承载 Windows Communication Foundation (WCF) 服务且被授予对共享服务的连接访问权限的进程指定用户帐户。  
  
 \<system.serviceModel.activation>  
  
## <a name="syntax"></a>语法  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|特性|描述|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|为承载 WCF 服务且被授予对共享服务的连接访问权限的进程添加用户帐户|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)|指定 Net Pipe 或 TCP 共享服务的配置设置。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
