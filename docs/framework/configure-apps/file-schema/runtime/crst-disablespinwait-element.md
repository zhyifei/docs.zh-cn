---
title: < Crst_DisableSpinWait > 元素
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a91e21120ecebbe7af2fb93798bc68d274fa92c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252716"
---
# <a name="crst_disablespinwait-element"></a>\<Crst_DisableSpinWait > 元素

指定是否在争用时禁用临界区等待。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<运行时 >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<Crst_DisableSpinWait >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素

下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|**enabled**|指定禁用已争用的关键部分时，是否旋转等待。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|描述|  
|-----------|-----------------|  
|1|禁用在无法获取关键部分时等待自旋。|  
|0|不要在无法获取关键节时禁用自旋等待。 这是默认值。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关各种运行时配置设置的信息。|  
  
## <a name="example"></a>示例  

下面的示例在争用时在关键部分禁用自旋。  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
