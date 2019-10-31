---
title: <generatePublisherEvidence> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: b04ef53d6e9c3d954b0925ea8634b3d220b36af7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116574"
---
# <a name="generatepublisherevidence-element"></a>\<generatePublisherEvidence > 元素
指定运行时是否创建代码访问安全性（CAS） <xref:System.Security.Policy.Publisher> 证据。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<generatePublisherEvidence >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指定运行时是否创建 <xref:System.Security.Policy.Publisher> 证据。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|“值”|描述|  
|-----------|-----------------|  
|`false`|不创建 <xref:System.Security.Policy.Publisher> 证据。|  
|`true`|创建 <xref:System.Security.Policy.Publisher> 证据。 这是默认设置。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关运行时初始化选项的信息。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 在 .NET Framework 4 及更高版本中，此元素对程序集加载时间没有影响。 有关详细信息，请参阅[安全更改](../../../security/security-changes.md)中的 "安全策略简化" 部分。  
  
 公共语言运行时（CLR）尝试在加载时验证 Authenticode 签名，以创建程序集 <xref:System.Security.Policy.Publisher> 证据。 但是，默认情况下，大多数应用程序不需要 <xref:System.Security.Policy.Publisher> 证据。 标准 CAS 策略不依赖于 <xref:System.Security.Policy.PublisherMembershipCondition>。 除非你的应用程序在具有自定义 CAS 策略的计算机上执行，或者要在部分信任环境中满足 <xref:System.Security.Permissions.PublisherIdentityPermission> 的要求，否则应避免与验证发行者签名相关的不必要的启动成本。 （在完全信任的环境中，标识权限的要求始终成功。）  
  
> [!NOTE]
> 建议服务使用 `<generatePublisherEvidence>` 元素以提高启动性能。  使用此元素还有助于避免可能导致超时和取消服务启动的延迟。  
  
## <a name="configuration-file"></a>配置文件  
 此元素只能在应用程序配置文件中使用。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用 `<generatePublisherEvidence>` 元素禁用应用程序的 CAS 发行者策略检查。  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
