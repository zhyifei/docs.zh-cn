---
title: <NetFx40_LegacySecurityPolicy> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 848c56773c0ff2986f0bec3e82a08a3d0dd35434
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456481"
---
# <a name="netfx40legacysecuritypolicy-element"></a>\<NetFx40_LegacySecurityPolicy > 元素
指定运行时是否使用旧版代码访问安全性 (CAS) 策略。  
  
 \<configuration>  
\<运行时 >  
<NetFx40_LegacySecurityPolicy>  
  
## <a name="syntax"></a>语法  
  
```xml  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指定运行时是否使用旧版 CAS 策略。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|描述|  
|-----------|-----------------|  
|`false`|在运行时不使用旧版 CAS 策略。 这是默认设置。|  
|`true`|运行时使用旧版 CAS 策略。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关运行时初始化选项的信息。|  
  
## <a name="remarks"></a>备注  
 在.NET Framework 版本 3.5 和更早版本中，CAS 策略都起作用。 在[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]，必须启用 CAS 策略。  
  
 CAS 策略是特定于版本的。 .NET Framework 4 中，必须再次指定自定义.NET Framework 的早期版本中存在的 CAS 策略。  
  
 将应用`<NetFx40_LegacySecurityPolicy>`元素[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]程序集不会影响[安全透明代码](../../../../../docs/framework/misc/security-transparent-code.md); 透明度规则仍然适用。  
  
> [!IMPORTANT]
>  将应用`<NetFx40_LegacySecurityPolicy>`元素创建的本机映像程序集可能导致显著的性能损失[本机映像生成器 (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md)是否未安装在[全局程序集缓存](../../../../../docs/framework/app-domains/gac.md). 性能下降由运行时无法应用该特性为本机图像加载程序集，从而导致其被加载，在实时程序集。  
  
> [!NOTE]
>  如果指定的目标.NET Framework 版本早于.NET Framework 4 中的项目设置为你的 Visual Studio 项目，将启用 CAS 策略，包括为该版本指定任何自定义 CA 策略。 但是，您将不能使用新的.NET Framework 4 类型和成员。 此外可以通过使用指定的.NET framework 早期版本[ \<supportedRuntime > 元素](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)启动设置架构中你[应用程序配置文件](../../../../../docs/framework/configure-apps/index.md)。  
  
> [!NOTE]
>  配置文件语法是区分大小写。 在语法和示例部分中所述，应使用语法。  
  
## <a name="configuration-file"></a>配置文件  
 仅在应用程序配置文件中，可以使用此元素。  
  
## <a name="example"></a>示例  
 下面的示例演示如何启用旧版 CAS 策略的应用程序。  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- [运行时设置架构](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)
