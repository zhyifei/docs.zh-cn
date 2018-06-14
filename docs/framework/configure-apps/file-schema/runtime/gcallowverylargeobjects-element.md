---
title: '&lt;gcAllowVeryLargeObjects&gt;元素'
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 750b0dbc925ec484dd80e1796ba991435e354709
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745222"
---
# <a name="ltgcallowverylargeobjectsgt-element"></a>&lt;gcAllowVeryLargeObjects&gt;元素
在 64 位平台上，启用总大小大于 2 千兆字节 (GB) 的数组。  
  
 \<配置 > 元素  
\<运行时 > 元素  
\<gcAllowVeryLargeObjects > 元素  
  
## <a name="syntax"></a>语法  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指定是否在 64 位平台上启用的总大小大于 2 GB 的数组。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|描述|  
|-----------|-----------------|  
|`false`|未启用大于总大小中的 2 GB 的数组。 这是默认设置。|  
|`true`|在 64 位平台上启用大于总大小中的 2 GB 的数组。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关运行时初始化选项的信息。|  
  
## <a name="remarks"></a>备注  
 在应用程序配置文件中使用此元素启用数组是大于 2 GB 的大小，但不会更改对象大小或数组大小上的其他限制：  
  
-   数组中元素的最大数目是<xref:System.UInt32.MaxValue?displayProperty=nameWithType>。  
  
-   任何单个维度中的最大索引是 2,147,483,591 字节数组和单字节结构的数组 (0x7FFFFFC7) 和其他类型的 2,146,435,071 (0X7FEFFFFF)。  
  
-   字符串和其他非数组对象的最大大小保持不变。  
  
> [!CAUTION]
>  启用此功能前，请确保你的应用程序不包括假设所有数组小于 2 GB 大小的不安全代码。 例如，使用数组作为缓冲区的不安全代码可能容易受到缓冲区溢出如果写入假定数组将不会超过 2 GB。  
  
## <a name="example"></a>示例  
 下面的示例演示如何对应用程序启用此功能。  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 [运行时设置架构](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)
