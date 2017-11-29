---
title: "&lt;performanceCounters&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <perfomanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f7fdbb244663e5114880437a5a508270c80a9c79
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltperformancecountersgt-element"></a>&lt;performanceCounters&gt;元素
指定由性能计数器共享的全局内存的大小。  
  
 \<configuration>  
\<system.diagnostics >  
\<performanceCounters >  
  
## <a name="syntax"></a>语法  
  
```xml  
<performanceCounters filemappingsize="524288" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|filemappingsize|必需的特性。<br /><br /> 指定的大小，以字节为单位由性能计数器共享的全局内存。 默认值为 524288。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`Configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`system.diagnostics`|为 ASP.NET 配置节指定根元素。|  
  
## <a name="remarks"></a>备注  
 性能计数器使用内存映射文件或共享的内存，发布性能数据。  共享内存的大小确定可以在一次使用多少个实例。  有两种类型的共享内存： 全局共享内存和单独的共享的内存。  安装的.NET Framework 版本 1.0 或 1.1 的所有性能计数器类别都使用全局共享的内存。  随.NET Framework 2.0 版一起安装的性能计数器类别使用单独的共享的内存，每个性能计数器类别都有自己的内存。  
  
 可以仅使用配置文件设置全局共享内存的大小。  默认大小为 524288 字节、 最大大小为 33554432 字节，和的最小大小为 32,768 字节。  由于全局共享的内存共享由所有进程和类别的第一个创建者指定的大小。  如果应用程序配置文件中定义的大小，如果你的应用程序的第一个应用程序会导致要执行的性能计数器才会使用该大小。  因此指定的正确位置`filemappingsize`值是 Machine.config 文件。  无法通过单个性能计数器，因此，最终全局共享的内存用完时，如果创建了大量的具有不同名称的性能计数器实例释放全局共享内存中的内存。  
  
 对于单独的共享内存大小，在注册表中的 DWORD FileMappingSize 值密钥 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<类别名称 >*引用 \Performance首先后, 跟为配置文件中的全局共享内存指定的值。 如果 FileMappingSize 值不存在，则单独的共享的内存大小设置为一个第四个 (1/4) 配置文件中的全局设置。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Diagnostics.PerformanceCounter>  
 <xref:System.Diagnostics.PerformanceCounterCategory>  
 <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>  
 <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
