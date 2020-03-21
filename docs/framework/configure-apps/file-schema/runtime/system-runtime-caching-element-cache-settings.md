---
title: <system.runtime.caching> 元素（缓存设置）
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
ms.openlocfilehash: df4887c8801dcf8af06b3826673a03cbc7dbc9b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153849"
---
# <a name="systemruntimecaching-element-cache-settings"></a>\<系统.运行时.缓存>元素（缓存设置）

通过配置文件中的 <xref:System.Runtime.Caching.ObjectCache> 条目为默认内存中的 `memoryCache` 实现提供配置。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;**\<系统.运行时.缓存>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a>特性和元素

下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性

`None`  

### <a name="child-elements"></a>子元素

|元素|说明|  
|-------------|-----------------|  
|[\<内存缓存>](memorycache-element-cache-settings.md)|定义一个用于配置基于 <xref:System.Runtime.Caching.MemoryCache> 类的缓存的元素。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<配置>](../configuration-element.md)|指定通用语言运行时和 .NET Framework 应用程序使用的每个配置文件中的根元素。|  
  
## <a name="remarks"></a>备注

此命名空间中的类提供一种使用诸如 ASP.NET 中缓存功能的方法，但不会在 `System.Web` 程序集上产生依赖。 有关详细信息，请参阅 [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md)。  
  
> [!NOTE]
> 命名空间中的<xref:System.Runtime.Caching>输出缓存功能和类型在 .NET 框架 4 中是新的。  
  
## <a name="example"></a>示例

下面的示例演示如何配置基于 <xref:System.Runtime.Caching.MemoryCache> 类的缓存。 该示例演示如何为内存缓存配置 `namedCaches` 条目实例。 通过将属性设置为"默认"，`name`缓存的名称将设置为默认缓存条目名称。  
  
将 `cacheMemoryLimitMegabytes` 属性和 `physicalMemoryPercentage` 属性设置为零。 将这些特性设置为零意味着默认情况下使用 <xref:System.Runtime.Caching.MemoryCache> 自动调整大小试探法。 每隔两分钟，缓存实现应对当前内存负载和基于百分比的绝对内存限制进行比较。  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- [\<内存缓存>元素（缓存设置）](memorycache-element-cache-settings.md)
