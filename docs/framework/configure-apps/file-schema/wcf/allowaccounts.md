---
title: '&lt;allowAccounts&gt;'
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: bbfe0d5d531cf61c01f95d0e82ce0f894031d6f3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltallowaccountsgt"></a>&lt;allowAccounts&gt;
包含的指定用户帐户，进程承载 Windows Communication Foundation (WCF) 服务并被授予了对该共享服务的连接访问权限的配置元素的集合。  
  
 \<system.serviceModel.activation>  
  
## <a name="syntax"></a>语法  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|特性|描述|  
|---------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|添加进程的用户帐户，这些进程承载 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服务并被授予了对该共享服务的连接访问权限。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<net.pipe >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md)或[ \<net.tcp >](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)|指定 Net Pipe 或 TCP 共享服务的配置设置。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
