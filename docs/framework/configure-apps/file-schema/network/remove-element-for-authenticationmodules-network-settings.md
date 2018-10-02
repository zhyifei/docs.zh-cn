---
title: '&lt;删除&gt;authenticationModules （网络设置） 的'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/authenticationModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, authenticationModules
- <authenticationModules>, remove element
- <remove> element, authenticationModules
- authenticationModules, remove element
ms.assetid: abf79949-b05c-465a-b51c-bbeda9a74173
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 332f8eb4fb1a5a02df76c5745522037b029a2407
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028532"
---
# <a name="ltremovegt-element-for-authenticationmodules-network-settings"></a>&lt;删除&gt;authenticationModules （网络设置） 的
从应用程序中删除身份验证模块。  
  
 \<configuration>  
\<system.net>  
\<authenticationModules >  
\<remove>  
  
## <a name="syntax"></a>语法  
  
```xml  
<remove   
   type="authentication module name"   
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|**特性**|**说明**|  
|-------------------|---------------------|  
|**type**|要删除的身份验证模块的名称。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|**元素**|**说明**|  
|-----------------|---------------------|  
|[authenticationModules](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|指定使用网络请求进行身份验证模块。|  
  
## <a name="remarks"></a>备注  
 `remove`元素中删除配置文件中或在配置层次结构中较高级别上前面定义的身份验证模块。  
  
 值为`type`属性应为有效的类名。  
  
## <a name="configuration-files"></a>配置文件  
 此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。  
  
## <a name="example"></a>示例  
 以下示例删除身份验证模块。  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <remove type="System.Net.NtlmClient" />  
    </authenticationModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Net.IAuthenticationModule>  
 <xref:System.Net.AuthenticationManager>  
 [网络设置架构](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
