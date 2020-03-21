---
title: <forcePerformanceCounterUniqueSharedMemoryReads> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 742b444c445ba67d6977b622e615a6a8f591826e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154135"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a>\<强制性能计数器唯一共享内存读取>元素
指定 PerfCounter.dll 是否使用 .NET Framework 版本 1.1 应用程序中的 CategoryOptions 注册表设置，以确定是否加载来自特定于类别的共享内存或全局内存的性能计数器数据。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<强制性能计数器唯一共享内存读取>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指示 PerfCounter.dll 是否使用"类别选项"注册表设置来确定是从特定于类别的共享内存或全局内存加载性能计数器数据。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|说明|  
|-----------|-----------------|  
|`false`|PerfCounter.dll 不使用类别选项注册表设置这是默认值。|  
|`true`|PerfCounter.dll 确实使用类别选项注册表设置。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 在 .NET 框架 4 之前的 .NET 框架版本中，加载的 PerfCounter.dll 版本对应于进程中加载的运行时。 如果计算机同时安装了 .NET 框架版本 1.1 和 .NET Framework 2.0，则 .NET 框架 1.1 应用程序将加载 PerfCounter.dll 的 .NET 框架 1.1 版本。 从 .NET 框架 4 开始，将加载最新的已安装版本的 PerfCounter.dll。 这意味着.NET 框架 1.1 应用程序将加载 .NET 框架 4 版本的 PerfCounter.dll，如果 .NET 框架 4 安装在计算机上。  
  
 从 .NET 框架 4 开始，使用性能计数器时，PerfCounter.dll 会检查每个提供程序的类别选项注册表项，以确定是否应从特定于类别的共享内存或全局共享内存读取该条目。 .NET 框架 1.1 PerfCounter.dll 不读取该注册表项，因为它不知道特定于类别的共享内存;它总是从全局共享内存读取。  
  
 对于向后兼容性，.NET 框架 4 PerfCounter.dll 在 .NET 框架 1.1 应用程序中运行时不检查类别选项注册表项。 它只使用全局共享内存，就像 .NET 框架 1.1 PerfCounter.dll 一样。 但是，您可以指示 .NET 框架 4 PerfCounter.dll 通过启用`<forcePerformanceCounterUniqueSharedMemoryReads>`该元素来检查注册表设置。  
  
> [!NOTE]
> 启用该`<forcePerformanceCounterUniqueSharedMemoryReads>`元素并不保证将使用特定于类别的共享内存。 设置为仅启用`true`PerfCounter.dll 以引用类别选项注册表设置。 "类别选项"的默认设置是使用特定于类别的共享内存;但是，您可以更改类别选项以指示应使用全局共享内存。  
  
 包含"类别选项"设置的注册表项HKEY_LOCAL_MACHINE_System_CurrentControlSet_服务\\<类别名称\>\性能。 默认情况下，类别选项设置为 3，指示 PerfCounter.dll 使用特定于类别的共享内存。 如果类别选项设置为 0，PerfCounter.dll 将使用全局共享内存。 仅当要创建的实例的名称与正在重用的实例相同时，才会重用实例数据。 所有版本将能够写入类别。 如果"类别选项"设置为 1，则使用全局共享内存，但如果类别名称的长度与正在重用的类别长度相同，则可以重复使用实例数据。  
  
 设置 0 和 1 可能导致内存泄漏和性能计数器内存填满。  
  
## <a name="example"></a>示例  
 下面的示例演示如何指定 PerfCounter.dll 应引用类别选项注册表项以确定是否应使用特定于类别的共享内存。  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
