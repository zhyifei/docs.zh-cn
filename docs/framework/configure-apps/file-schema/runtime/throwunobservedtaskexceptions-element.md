---
title: "&lt;ThrowUnobservedTaskExceptions&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d171c2058a79476d99c5952cc6a697f126af81c4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltthrowunobservedtaskexceptionsgt-element"></a>&lt;ThrowUnobservedTaskExceptions&gt;元素
指定未经处理的任务异常是否应终止正在运行的进程。  
  
 \<configuration>  
\<运行时 >  
\<ThrowUnobservedTaskExceptions >  
  
## <a name="syntax"></a>语法  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指定未经处理的任务异常是否应终止正在运行的进程。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|描述|  
|-----------|-----------------|  
|`false`|不会终止正在运行的未经处理的任务异常进程。 这是默认设置。|  
|`true`|终止正在运行的未经处理的任务异常进程。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关运行时初始化选项的信息。|  
|||  
  
## <a name="remarks"></a>备注  
 如果与关联的异常<xref:System.Threading.Tasks.Task>具有尚未观察到，没有任何<xref:System.Threading.Tasks.Task.Wait%2A>未附加操作，父级，请与<xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType>属性不读取任务异常被视为未观察到。  
  
 在[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]，也可由默认情况下，如果<xref:System.Threading.Tasks.Task>，其未观察到异常进行垃圾回收、 终结器引发异常，并终止进程。 垃圾回收和终止的时间取决于进程终止。  
  
 为了更加便于开发人员编写基于任务的异步代码[!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)]更改未观察到异常此默认行为。 仍会导致的异常未观察到<xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>事件被引发，但默认情况下，不终止进程。 相反，该异常被忽略后引发事件时，无论是否事件处理程序观察到异常。  
  
 在[!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)]，你可以使用[ \<ThrowUnobservedTaskExceptions > 元素](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md)中启用的应用程序配置文件[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]引发异常的行为。  
  
 你还可以通过以下方式之一指定的异常行为：  
  
-   通过设置环境变量`COMPlus_ThrowUnobservedTaskExceptions`(`set COMPlus_ThrowUnobservedTaskExceptions=1`)。  
  
-   通过设置注册表 DWORD 值 ThrowUnobservedTaskExceptions = 1 在 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\。NETFramework 键。  
  
## <a name="example"></a>示例  
 下面的示例演示如何启用任务中的异常引发通过使用应用程序配置文件。  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a>示例  
 下面的示例演示如何从任务引发未观察到的异常。 作为发布程序正常工作，必须运行代码。  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a>另请参阅  
 [运行时设置架构](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)
