---
title: < Crst_DisableSpinWait > 元素
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cde26250db0b3d11c51a18b7ebd378953ae0958
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704825"
---
# <a name="crstdisablespinwait-element"></a>\<Crst_DisableSpinWait > 元素

指定是否禁用数值调节钮等待关键部分时争用。 \ 
  
 \<configuration>  
\<运行时 >  
\<Crst_DisableSpinWait>  
  
## <a name="syntax"></a>语法  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素

下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|**enabled**|指定当它们争用时是否启用数值调节钮等待关键部分。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|“值”|描述|  
|-----------|-----------------|  
|1|数值调节钮等待已启用。|  
|0|数值调节钮等待处于禁用状态。 这是默认值|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关运行时的各种配置设置的信息。|  
  
## <a name="example"></a>示例  

以下示例禁用数值调节钮-等待在临界区时争用。  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- [运行时设置架构](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)
