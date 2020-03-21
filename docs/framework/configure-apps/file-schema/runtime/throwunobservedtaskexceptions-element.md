---
title: <ThrowUnobservedTaskExceptions> 元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
ms.openlocfilehash: de5a686bcbd88fc52173b488103f033575623d62
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153810"
---
# <a name="throwunobservedtaskexceptions-element"></a>\<引发未观察到的任务异常>元素
指定未经处理的任务异常是否应终止正在运行的进程。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<引发未观察到的任务异常>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指定未处理的任务异常是否应终止正在运行的进程。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|说明|  
|-----------|-----------------|  
|`false`|不终止未处理的任务异常的运行进程。 这是默认值。|  
|`true`|终止未处理的任务异常的运行进程。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关运行时初始化选项的信息。|  
|||  
  
## <a name="remarks"></a>备注  
 如果未观察到与<xref:System.Threading.Tasks.Task>关联的异常，则没有<xref:System.Threading.Tasks.Task.Wait%2A>操作，父项未连接，并且<xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType>未读取该属性，则任务异常被视为未观察到。  
  
 默认情况下，在 .NET 框架 4 中<xref:System.Threading.Tasks.Task>，如果正在回收具有未观察到异常的 异常，则终结器将引发异常并终止进程。 流程的终止取决于垃圾回收和定稿的时间。  
  
 为了使开发人员更容易基于任务编写异步代码，.NET Framework 4.5 会更改此默认行为，以进行未观察到的异常。 未观察到的异常仍会导致<xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>引发事件，但默认情况下，进程不会终止。 相反，无论事件处理程序是否遵守异常，在引发事件后将忽略异常。  
  
 在 .NET 框架 4.5 中，可以使用应用程序配置文件中的[\<ThrowUnununununtaskexception> 元素](throwunobservedtaskexceptions-element.md)来启用引发异常的 .NET 框架 4 行为。  
  
 还可以通过以下方式之一指定异常行为：  
  
- 通过设置环境变量`COMPlus_ThrowUnobservedTaskExceptions`（。`set COMPlus_ThrowUnobservedTaskExceptions=1`  
  
- 通过设置注册表 DWORD 值"ThrowUnunun_TaskExceptions " HKEY_LOCAL_MACHINE_SOFTWARE_Microsoft\\中为 1。NETFramework 密钥。  
  
## <a name="example"></a>示例  
 下面的示例演示如何通过使用应用程序配置文件在任务中启用异常的引发。  
  
```xml  
<configuration>
    <runtime>
        <ThrowUnobservedTaskExceptions enabled="true"/>
    </runtime>
</configuration>  
```  
  
## <a name="example"></a>示例  
 下面的示例演示如何从任务中引发未观察到的异常。 代码必须作为已发布的程序运行才能正常工作。  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a>另请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
