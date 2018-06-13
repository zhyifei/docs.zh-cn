---
title: '&lt;namedCaches&gt;元素 （缓存设置）'
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: fac50aedbb11eba40482fab71c912f587d85f855
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744650"
---
# <a name="ltnamedcachesgt-element-cache-settings"></a>&lt;namedCaches&gt;元素 （缓存设置）
指定的配置设置的命名集合<xref:System.Runtime.Caching.MemoryCache>实例。 <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A>属性引用的配置设置的集合从一个或多个`namedCaches`配置文件的元素。  
  
 \<configuration>  
\< system.runtime.caching >  
\<memoryCache>  
\<namedCaches >  
  
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
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|一个整数值，指定的最大大小，单位为兆字节，该实例<xref:System.Runtime.Caching.MemoryCache>可以增长到。 默认值为 0，这意味着的自动调整大小试探法<xref:System.Runtime.Caching.MemoryCache>默认情况下使用类。|  
|`name`|缓存的名称。|  
|`physicalMemoryLimitPercentage`|指定以物理方式安装的计算机可以由缓存使用的内存的最大百分比整数值介于 0 和 100 之间。 默认值为 0，这意味着的自动调整大小试探法<xref:System.Runtime.Caching.MemoryCache>默认情况下使用类。|  
|`pollingInterval`|一个时间间隔的值，在该时间间隔之后，缓存实现会将当前内存负载与为缓存实例设置的基于绝对值和百分比的内存限制进行比较。 "Hh: mm:"格式输入此值。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/runtime/add-element-for-namedcaches.md)|向内存缓存的 `namedCaches` 集合添加一个命名的缓存。|  
|[\<clear>](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md)|清除内存缓存的 `namedCaches` 集合。|  
|[\<remove>](../../../../../docs/framework/configure-apps/file-schema/runtime/remove-element-for-namedcaches.md)|从内存缓存的 `namedCaches` 集合中删除一个命名的缓存条目。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<memoryCache>](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)|定义一个用于配置基于 <xref:System.Runtime.Caching.MemoryCache> 类的缓存的元素。|  
  
## <a name="remarks"></a>备注  
 Web.config 文件的内存缓存配置节可以包含`add`， `remove`，和`clear`属性`namedCaches`集合。 每个`namedCaches`项都由唯一标识`name`属性。  
  
 可以通过引用应用程序配置文件中的信息来检索实例的内存缓存条目。 默认情况下，默认的缓存实例配置文件中有一个条目。 默认缓存实例是从返回的实例<xref:System.Runtime.Caching.MemoryCache.Default%2A>属性。  
  
 如果设置为"默认值"的名称属性，元素将使用默认内存缓存实例。  
  
## <a name="example"></a>示例  
 下面的示例演示如何将缓存的名称设置为默认缓存项名称，通过设置`name`属性设置为"default"。  
  
 将 `cacheMemoryLimitMegabytes` 属性和 `physicalMemoryPercentage` 属性设置为零。 将这些特性设置为零意味着的自动调整大小试探法<xref:System.Runtime.Caching.MemoryCache>类使用。 缓存实现将比较当前的内存负载与每隔两分钟的绝对和基于百分比的内存限制。  
  
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
  
## <a name="see-also"></a>请参阅  
 [\<memoryCache > 元素 （缓存设置）](../../../../../docs/framework/configure-apps/file-schema/runtime/memorycache-element-cache-settings.md)
