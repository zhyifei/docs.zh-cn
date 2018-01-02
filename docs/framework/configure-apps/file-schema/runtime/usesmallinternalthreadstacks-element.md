---
title: "&lt;UseSmallInternalThreadStacks&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c96537cad59034578d1284f7dc432e5775f3730b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltusesmallinternalthreadstacksgt-element"></a>&lt;UseSmallInternalThreadStacks&gt;元素
请求公共语言运行时 (CLR) 减少内存使用通过指定显式的堆栈大小，创建某些它在内部使用，而不是使用默认堆栈大小适用于这些线程的线程时。  
  
 \<配置 > 元素  
\<运行时 > 元素  
\<UseSmallInternalThreadStacks > 元素  
  
## <a name="syntax"></a>语法  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|enabled|必需的特性。<br /><br /> 指定是否请求，而不是默认堆栈大小的 CLR 使用显式的堆栈大小创建某些内部使用的线程时。 显式堆栈大小为小于 1 MB 的默认堆栈大小。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|描述|  
|-----------|-----------------|  
|true|请求显式的堆栈大小。|  
|false|使用默认堆栈大小。 这是默认值[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 此配置元素用来请求减少的虚拟内存使用在过程中，因为对于其内部的线程，使用的 CLR，如果接受请求，为显式线程大小都小于默认大小。  
  
> [!IMPORTANT]
>  此配置元素是对 CLR，而不是绝对要求的请求。 在[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]，则请求响应仅适用于 x86 体系结构。 可能的 CLR，未来版本中完全忽略此元素，或将其替换为显式堆栈大小始终用于所选的内部线程。  
  
 指定此配置元素交易的可靠性较小的虚拟内存使用是否 CLR 接受请求，因为较小的堆栈大小可能会使堆栈更有可能溢出。  
  
## <a name="example"></a>示例  
 下面的示例演示如何请求 CLR 使用显式堆栈调整某些大小它在内部使用的线程。  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 [运行时设置架构](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)
