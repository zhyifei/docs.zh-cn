---
title: <namedCaches> 元素（缓存设置）
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: e0640ca18d386141f3c03135019eb4fe959b5bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153953"
---
# <a name="namedcaches-element-cache-settings"></a>\<命名缓存>元素（缓存设置）
指定命名<xref:System.Runtime.Caching.MemoryCache>实例的配置设置集合。 该<xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A>属性引用配置文件的一个或多个`namedCaches`元素的配置设置集合。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.运行时.缓存>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<内存缓存>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<命名缓存>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<namedCaches>  
  <add name="default"/>
</namedCaches>  
```  
  
## <a name="type"></a>类型  
 `None`  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|指定 a<xref:System.Runtime.Caching.MemoryCache>实例可以增长到的最大允许大小（以兆字节为单位）的整数值。 默认值为 0，这意味着默认情况下使用<xref:System.Runtime.Caching.MemoryCache>类的自动启发式调整大小。|  
|`name`|缓存的名称。|  
|`physicalMemoryLimitPercentage`|介于 0 和 100 之间的整数值，指定缓存可以使用的物理安装计算机内存的最大百分比。 默认值为 0，这意味着默认情况下使用<xref:System.Runtime.Caching.MemoryCache>类的自动启发式调整大小。|  
|`pollingInterval`|一个时间间隔的值，在该时间间隔之后，缓存实现会将当前内存负载与为缓存实例设置的基于绝对值和百分比的内存限制进行比较。 此值以"HH：MM：SS"格式输入。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<添加>](add-element-for-namedcaches.md)|向内存缓存的 `namedCaches` 集合添加一个命名的缓存。|  
|[\<明确>](clear-element-for-namedcaches.md)|清除内存缓存的 `namedCaches` 集合。|  
|[\<删除>](remove-element-for-namedcaches.md)|从内存缓存的 `namedCaches` 集合中删除一个命名的缓存条目。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<配置>](../configuration-element.md)|指定通用语言运行时和 .NET Framework 应用程序使用的每个配置文件中的根元素。|  
|[\<内存缓存>](memorycache-element-cache-settings.md)|定义一个用于配置基于 <xref:System.Runtime.Caching.MemoryCache> 类的缓存的元素。|  
|[\<系统.运行时.缓存>](system-runtime-caching-element-cache-settings.md)|包含允许您在内置于 .NET 框架中的应用程序中实现输出缓存的类型。|  
  
## <a name="remarks"></a>备注  
 Web.config`add`文件的内存缓存配置部分可以包含 集合`remove`的`namedCaches``clear`和 属性。 每个`namedCaches`条目都由`name`属性唯一标识。  
  
 您可以通过引用应用程序配置文件中的信息来检索内存缓存条目的实例。 默认情况下，只有默认缓存实例在配置文件中具有条目。 默认缓存实例是从属性返回的<xref:System.Runtime.Caching.MemoryCache.Default%2A>实例。  
  
 如果将名称属性设置为"默认"，则元素将使用默认内存缓存实例。  
  
## <a name="example"></a>示例  
 下面的示例演示如何通过将`name`属性设置为"默认"来将缓存的名称设置为默认缓存条目名称。  
  
 将 `cacheMemoryLimitMegabytes` 属性和 `physicalMemoryPercentage` 属性设置为零。 将这些属性设置为零意味着使用<xref:System.Runtime.Caching.MemoryCache>类的自动启发式调整大小。 缓存实现将当前内存负载与绝对内存限制和基于百分比的内存限制每两分钟进行比较。  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"
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
