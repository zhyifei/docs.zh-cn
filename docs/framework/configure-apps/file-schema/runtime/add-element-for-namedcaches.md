---
title: <namedCaches> 的 <add> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: 076d940e0c15cf48013480fef68b8fac42cf76e9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252893"
---
# <a name="add-element-for-namedcaches"></a>\<添加 namedCaches 的\<> 元素 >
向内存缓存的`namedCaches`集合中添加项。`namedCache`  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> 缓存**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache >** ](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<namedCaches >** ](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>类型  
 `None`  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|-|-|  
|`CacheMemoryLimitMegabytes`|一个整数值，指定的<xref:System.Runtime.Caching.MemoryCache>实例可以增长到的最大允许大小（以 mb 为单位）。 默认值为0，这意味着<xref:System.Runtime.Caching.MemoryCache>默认情况下使用类的自动调整试探法。|  
|`Name`|缓存的名称。|  
|`PhysicalMemoryLimitPercentage`|一个介于0到100之间的整数值，用于指定缓存可使用的实际安装计算机内存的最大百分比。 默认值为0，这意味着<xref:System.Runtime.Caching.MemoryCache>默认情况下使用类的自动调整试探法。|  
|`PollingInterval`|一个时间间隔的值，在该时间间隔之后，缓存实现会将当前内存负载与为缓存实例设置的基于绝对值和百分比的内存限制进行比较。 此值以 "HH： MM： SS" 格式输入。|  
  
### <a name="child-elements"></a>子元素  
 `None`  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|包含命名<xref:System.Runtime.Caching.MemoryCache>实例的配置设置的集合。|  
  
## <a name="remarks"></a>备注  
 元素向内存缓存的`namedCaches`集合中添加项。 `add` 您可以在使用 `add` 元素之前使用 [clear](clear-element-for-namedcaches.md) 元素，以确保集合中没有其他命名缓存。 此元素可在 machine.config 文件和 web.config 文件中使用。  
  
## <a name="example"></a>示例  
 下面的示例演示如何为内存缓存的`namedCache` `namedCaches`集合定义默认项的设置。  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- [\<namedCaches > 元素（缓存设置）](namedcaches-element-cache-settings.md)
