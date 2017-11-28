---
title: '&lt;remove&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4058e2f1-7db4-4d1a-84dd-1b52836f2ae6
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 0c8fd5a9a5c4d6007ff0f67132b97b0aa5d98256
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltremovegt"></a>&lt;remove&gt;
从标记处理程序集合中移除指定的安全令牌处理程序。  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<删除 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <remove type=xs:string >  
      </remove>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|类型|要删除的令牌处理程序的 CLR 类型名称。 有关如何指定详细信息`type`属性，请参阅[自定义类型引用](http://msdn.microsoft.com/en-us/7286d2e3-c63d-49fd-abdc-ce2705f22c24)。 必需。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<securityTokenHandlers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|指定与终结点注册的安全令牌处理程序的集合。|  
  
## <a name="example"></a>示例  
 下面的 XML 演示如何使用`<add>`和`<remove>`元素使用的自定义会话令牌处理程序替换默认会话令牌处理程序。 XML 取自`ClaimsAwareWebFarm`示例。  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
