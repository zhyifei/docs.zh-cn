---
title: <generatePublisherEvidence> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: 24a5ea02992a5bce681b5bab4fb7f75505bd225d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154097"
---
# <a name="generatepublisherevidence-element"></a>\<generatePublisherEvidence> 元素
指定运行时是否为代码访问<xref:System.Security.Policy.Publisher>安全性 （CAS） 创建证据。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<生成发布者证据>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指定运行时是否创建<xref:System.Security.Policy.Publisher>证据。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|说明|  
|-----------|-----------------|  
|`false`|不创建<xref:System.Security.Policy.Publisher>证据。|  
|`true`|创建<xref:System.Security.Policy.Publisher>证据。 这是默认值。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关运行时初始化选项的信息。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 在 .NET 框架 4 及更高版本中，此元素对程序集加载时间没有影响。 有关详细信息，请参阅[安全更改](../../../security/security-changes.md)中的"安全策略简化"部分。  
  
 通用语言运行时 （CLR） 尝试在加载时验证身份验证签名，以创建程序集<xref:System.Security.Policy.Publisher>的证据。 但是，默认情况下，大多数应用程序不需要<xref:System.Security.Policy.Publisher>证据。 标准 CAS 策略不依赖于<xref:System.Security.Policy.PublisherMembershipCondition>。 您应该避免与验证发布者签名相关的不必要的启动成本，除非您的应用程序在具有自定义 CAS 策略的计算机上执行，或者打算满足部分信任环境中的需求<xref:System.Security.Permissions.PublisherIdentityPermission>。 （对标识权限的要求总是在完全信任的环境中成功。  
  
> [!NOTE]
> 我们建议服务使用 元素`<generatePublisherEvidence>`来提高启动性能。  使用此元素还有助于避免可能导致超时和服务启动取消的延迟。  
  
## <a name="configuration-file"></a>配置文件  
 此元素只能在应用程序配置文件中使用。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用 元素`<generatePublisherEvidence>`来禁用检查应用程序的 CAS 发布者策略。  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
