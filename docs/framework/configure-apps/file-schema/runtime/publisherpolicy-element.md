---
title: <publisherPolicy> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
ms.openlocfilehash: 89fa8a991cc7d0352eb0a13cdfd3a6063ea468e7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115850"
---
# <a name="publisherpolicy-element"></a>\<Publisherpolicy apply > 元素
指定运行时是否使用发布者策略。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp; &nbsp; &nbsp; &nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md) \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dependentAssembly >** ](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<publisherpolicy apply >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`apply`|指定是否应用发布者策略。|  
  
## <a name="apply-attribute"></a>应用属性  
  
|“值”|描述|  
|-----------|-----------------|  
|`yes`|应用发布者策略。 此为默认设置。|  
|`no`|不应用发布者策略。|  
  
### <a name="child-elements"></a>子元素  

无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`assemblyBinding`|包含有关程序集版本重定向和程序集位置的信息。|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`dependentAssembly`|封装每个程序集的绑定策略和程序集位置。 为每个程序集使用一个 `<dependentAssembly>` 元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 当组件供应商发布程序集的新版本时，供应商可以包括发行者策略，以便使用旧版本的应用程序现在使用新版本。 若要指定是否将发布服务器策略应用于特定程序集，请将 **\<publisherpolicy apply >** 元素放在 **\<dependentAssembly >** 元素中。  
  
 **Apply**属性的默认设置为 **"是"** 。 如果将**apply**特性设置为 "**否**"，则将替代程序集以前的 **"是"** 设置。  
  
 若要让应用程序使用应用程序配置文件中的[\<publisherpolicy apply apply = "no"/>](publisherpolicy-element.md)元素显式忽略发行者策略，则需要权限。 通过设置 <xref:System.Security.Permissions.SecurityPermission>上的 <xref:System.Security.Permissions.SecurityPermissionFlag> 标志来授予权限。 有关详细信息，请参阅[程序集绑定重定向安全权限](../../assembly-binding-redirection-security-permission.md)。  
  
## <a name="example"></a>示例  
 下面的示例将关闭程序集的发行者策略 `myAssembly`。  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
- [运行时如何定位程序集](../../../deployment/how-the-runtime-locates-assemblies.md)
- [重定向程序集版本](../../redirect-assembly-versions.md)
