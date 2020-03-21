---
title: <gcAllowVeryLargeObjects> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 8b2f39a0867228474afdee788474fda11f14ca82
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154122"
---
# <a name="gcallowverylargeobjects-element"></a>\<gcAllow非常大的对象>元素
在 64 位平台上，启用总大小大于 2 千兆字节 (GB) 的数组。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllow 非常大的对象>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<gcAllowVeryLargeObjects
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指定是否在 64 位平台上启用总大小大于 2 GB 的阵列。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|说明|  
|-----------|-----------------|  
|`false`|未启用总大小大于 2 GB 的数组。 这是默认值。|  
|`true`|在 64 位平台上启用总大小大于 2 GB 的阵列。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关运行时初始化选项的信息。|  
  
## <a name="remarks"></a>备注  
 在应用程序配置文件中使用此元素可启用大小大于 2 GB 但不会改变对对象大小或数组大小的其他限制的数组：  
  
- 数组中的最大元素数为<xref:System.UInt32.MaxValue?displayProperty=nameWithType>。  
  
- 对于单字节结构的字节数组和数组，任何单个维度中的最大索引为 2，147，483，591 （0x7FFFFFC7），其他类型的为 2，146，435，071 （0X7FFFFF）。  
  
- 字符串和其他非数组对象的最大大小保持不变。  
  
> [!CAUTION]
> 在启用此功能之前，请确保应用程序不包含假定所有数组大小小于 2 GB 的不安全代码。 例如，如果使用数组作为缓冲区的不安全代码，如果编写时假定数组不会超过 2 GB，则很容易出现缓冲区溢出。  
  
## <a name="example"></a>示例  
 下面的示例演示如何为应用程序启用此功能。  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a>受以下版本支持：

.NET 框架 4.5 及更高版本

## <a name="see-also"></a>另请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
