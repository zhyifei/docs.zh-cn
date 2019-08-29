---
title: <namedCaches> 的 <clear> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: a90970e468359714bbbb858f3f300c26b5757a4d
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658861"
---
# <a name="clear-element-for-namedcaches"></a>\<清除 namedCaches 的\<> 元素 >
清除内存`namedCache`缓存的`namedCaches`集合中的所有项。  
  
 \<system.runtime.caching>  
\<memoryCache>  
\<namedCaches>  
\<add>  
  
## <a name="syntax"></a>语法  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>类型  
 `Type`  
  
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
 元素清除内存缓存`namedCache`的命名缓存集合中的所有项。 `clear` `clear` 在`add`使用元素添加新的命名缓存条目之前, 可以使用元素, 以便确定集合中没有其他命名缓存。  
  
## <a name="see-also"></a>请参阅

- [\<namedCaches > 元素 (缓存设置)](namedcaches-element-cache-settings.md)
