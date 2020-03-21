---
title: <namedCaches> 的 <add> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: c1345022b79df371ad9c89a39a0a8b625e26608c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154500"
---
# <a name="add-element-for-namedcaches"></a>\<为\<命名缓存添加>元素>
向`namedCache`内存缓存`namedCaches`的集合添加条目。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统.运行时.缓存>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<内存缓存>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<命名缓存>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<添加>**  
  
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
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|-|-|  
|`CacheMemoryLimitMegabytes`|指定 a<xref:System.Runtime.Caching.MemoryCache>实例可以增长到的最大允许大小（以兆字节为单位）的整数值。 默认值为 0，这意味着默认情况下使用<xref:System.Runtime.Caching.MemoryCache>类的自动调整启发式。|  
|`Name`|缓存的名称。|  
|`PhysicalMemoryLimitPercentage`|介于 0 和 100 之间的整数值，指定缓存可以使用的物理安装计算机内存的最大百分比。 默认值为 0，这意味着默认情况下使用<xref:System.Runtime.Caching.MemoryCache>类的自动调整启发式。|  
|`PollingInterval`|一个时间间隔的值，在该时间间隔之后，缓存实现会将当前内存负载与为缓存实例设置的基于绝对值和百分比的内存限制进行比较。 此值以"HH：MM：SS"格式输入。|  
  
### <a name="child-elements"></a>子元素  
 `None`  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<命名缓存>](namedcaches-element-cache-settings.md)|包含命名<xref:System.Runtime.Caching.MemoryCache>实例的配置设置集合。|  
  
## <a name="remarks"></a>备注  
 该`add`元素向内存缓存`namedCaches`的集合添加一个条目。 在使用 元素[clear](clear-element-for-namedcaches.md)之前，`add`可以使用 clear 元素来确保集合中没有其他命名缓存。 此元素可用于计算机.config 文件和 Web.config 文件中。  
  
## <a name="example"></a>示例  
 下面的示例演示如何为内存缓存集合的`namedCache``namedCaches`默认条目定义设置。  
  
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
  
## <a name="see-also"></a>另请参阅

- [\<命名缓存>元素（缓存设置）](namedcaches-element-cache-settings.md)
