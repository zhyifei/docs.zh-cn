---
title: <namedCaches> 的 <remove> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: e9b126cee83bc8109606d915ea48549beea970c9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663477"
---
# <a name="remove-element-for-namedcaches"></a>\<删除 namedCaches > 的\<> 元素
从内存缓存的 `namedCaches` 集合中删除一个命名的缓存条目。  
  
 \<system.runtime.caching>  
\<memoryCache>  
\<namedCaches>  
\<remove>  
  
## <a name="syntax"></a>语法  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>类型  
 `None`  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 `None`  
  
### <a name="child-elements"></a>子元素  
 `None`  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|包含命名<xref:System.Runtime.Caching.MemoryCache>实例的配置设置的集合。|  
  
## <a name="remarks"></a>备注  
 元素从内存缓存`namedCache`的命名缓存集合中删除一个条目。 `remove`  
  
## <a name="see-also"></a>请参阅

- [\<namedCaches > 元素 (缓存设置)](namedcaches-element-cache-settings.md)
