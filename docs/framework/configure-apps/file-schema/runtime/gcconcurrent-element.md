---
title: "&lt;gcConcurrent&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 254b3be8f270a9186377b264094c919314efb27f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltgcconcurrentgt-element"></a>&lt;gcConcurrent&gt;元素
指定公共语言运行时是否在单独线程上运行垃圾回收。  
  
 \<configuration>  
\<运行时 >  
\<gcConcurrent >  
  
## <a name="syntax"></a>语法  
  
```xml  
<gcConcurrent    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指定运行时是否并发运行服务器垃圾回收。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|描述|  
|-----------|-----------------|  
|`false`|不并发运行垃圾回收。|  
|`true`|并发运行垃圾回收。 这是默认设置。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 在.NET Framework 4 之前，工作站垃圾回收支持并发垃圾回收，在后台对一个单独线程执行垃圾回收。 在.NET Framework 4 中，并发垃圾回收被后台 GC 取代，它还在单独的线程上在后台中执行垃圾回收。 从 .NET Framework 4.5 开始，服务器垃圾回收可提供后台垃圾回收。 `<gcConcurrent>` 元素控制运行时是执行并发还是后台垃圾回收（如果可行），或者是否在前台执行垃圾回收。  
  
> [!WARNING]
>  从.NET Framework 4 开始，并发垃圾回收替换为后台垃圾回收。 条款*并发*和*后台*.NET Framework 文档中互换使用。 若要禁用后台垃圾回收，请使用 `<gcConcurrent>` 元素，如本文所述。  
  
 默认情况下，运行时使用并发或后台垃圾回收，回收针对延迟进行了优化。 如果应用程序涉及大量用户交互，则通过让并发垃圾回收保持启用状态，可最大限度缩短应用程序执行垃圾回收时的暂停时间。 如果将 `enabled` 元素的 `<gcConcurrent>` 特性设置为 `false`，运行时将使用针对吞吐量优化的非并发垃圾回收。 下列配置文件会禁用后台垃圾回收。  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 如果计算机配置文件中有 `<gcConcurrentSetting>` 设置，它会为所有 .NET Framework 应用程序定义默认值。 计算机配置文件设置将重写应用程序配置文件设置。  
  
 有关详细信息并发和后台垃圾回收，请参阅中的"并发垃圾回收"一节[垃圾回收的基础](../../../../../docs/standard/garbage-collection/fundamentals.md)主题。  
  
## <a name="example"></a>示例  
 下列示例启用并发垃圾回收。  
  
```xml  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 [运行时设置架构](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [垃圾回收的基础知识](../../../../../docs/standard/garbage-collection/fundamentals.md)
