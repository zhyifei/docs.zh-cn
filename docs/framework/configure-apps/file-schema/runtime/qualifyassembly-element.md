---
title: <qualifyAssembly> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
ms.openlocfilehash: 74e83900c68ab4b3fe01beb3f97657b0140d78ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153914"
---
# <a name="qualifyassembly-element"></a>\<限定装配>元素
指定使用部分名称时应动态加载的程序集全名。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<程序集绑定>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<符合条件>**  
  
## <a name="syntax"></a>语法  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`partialName`|必需的特性。<br /><br /> 指定程序集的部分名称，因为它出现在代码中。|  
|`fullName`|必需的特性。<br /><br /> 指定程序集的全名，因为它出现在全局程序集缓存中。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`assemblyBinding`|包含有关程序集版本重定向和程序集位置的信息。|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 使用部分<xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>程序集名称调用 方法会导致公共语言运行时仅在应用程序基目录中查找程序集。 使用应用程序配置文件中的**\<限定程序集>** 元素提供完整的程序集信息（名称、版本、公钥令牌和区域性），并导致通用语言运行时在全局程序集缓存中搜索程序集。  
  
 **fullName**属性必须包括程序集标识的四个字段：名称、版本、公钥令牌和区域性。 **部分名称**属性必须部分引用程序集。 必须至少指定程序集的文本名称（最常见的情况），但还可以包括版本、公钥令牌或区域性（或四者中的任何组合，但不是全部四个）。 **部分名称**必须与呼叫中指定的名称匹配。 例如，您不能在配置文件中`"math"`指定为**部分Name**属性，并在代码中调用`Assembly.Load("math, Version=3.3.3.3")`。  
  
## <a name="example"></a>示例  
 以下示例从逻辑上将调用`Assembly.Load("math")`转换为`Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`。  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- [运行时设置架构](index.md)
- [运行时如何定位程序集](../../../deployment/how-the-runtime-locates-assemblies.md)
- [部分程序集引用](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))
