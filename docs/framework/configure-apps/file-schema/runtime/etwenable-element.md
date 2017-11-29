---
title: "&lt;etwEnable&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b36c52338754df0f4fd3c963848e36afeb140501
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltetwenablegt-element"></a>&lt;etwEnable&gt;元素
指定是否为公共语言运行时事件启用 Windows 事件跟踪 (ETW)。  
  
 \<配置 > 元素  
\<运行时 > 元素  
\<etwEnabled >  
  
## <a name="syntax"></a>语法  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|enabled|必需的特性。<br /><br /> 指定是否应启用 ETW。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|描述|  
|-----------|-----------------|  
|true|启用 ETW。 这是从开始在 Windows Vista 和 Windows Server 2008 操作系统的 Windows 版本的默认值。|  
|false|禁用 ETW。 这是早期版本的 Windows 的默认值。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 从 Windows Vista 开始，将默认启用 ETW。 使用此元素用于禁用 ETW 的应用程序。 在早期版本的 Windows 中，使用此元素可为应用程序启用 ETW。  
  
> [!NOTE]
>  可以启用或通过使用注册表设置的服务器上全局禁用 ETW。 请参阅[控制.NET Framework 日志记录](../../../../../docs/framework/performance/controlling-logging.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示如何启用应用程序的 ETW 跟踪。  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅  
 [运行时设置架构](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [控制 .NET Framework 日志记录](../../../../../docs/framework/performance/controlling-logging.md)
