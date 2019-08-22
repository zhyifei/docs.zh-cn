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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 876452a0a56d10f169526138cdbbbd153572f457
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658848"
---
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="7497a-102">\<ThrowUnobservedTaskExceptions > 元素</span><span class="sxs-lookup"><span data-stu-id="7497a-102">\<ThrowUnobservedTaskExceptions> Element</span></span>
<span data-ttu-id="7497a-103">指定未经处理的任务异常是否应终止正在运行的进程。</span><span class="sxs-lookup"><span data-stu-id="7497a-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
 <span data-ttu-id="7497a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7497a-104">\<configuration></span></span>  
<span data-ttu-id="7497a-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="7497a-105">\<runtime></span></span>  
<span data-ttu-id="7497a-106">\<ThrowUnobservedTaskExceptions></span><span class="sxs-lookup"><span data-stu-id="7497a-106">\<ThrowUnobservedTaskExceptions></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7497a-107">语法</span><span class="sxs-lookup"><span data-stu-id="7497a-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7497a-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7497a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7497a-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7497a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7497a-110">特性</span><span class="sxs-lookup"><span data-stu-id="7497a-110">Attributes</span></span>  
  
|<span data-ttu-id="7497a-111">特性</span><span class="sxs-lookup"><span data-stu-id="7497a-111">Attribute</span></span>|<span data-ttu-id="7497a-112">描述</span><span class="sxs-lookup"><span data-stu-id="7497a-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="7497a-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="7497a-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="7497a-114">指定未经处理的任务异常是否应终止正在运行的进程。</span><span class="sxs-lookup"><span data-stu-id="7497a-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="7497a-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="7497a-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="7497a-116">值</span><span class="sxs-lookup"><span data-stu-id="7497a-116">Value</span></span>|<span data-ttu-id="7497a-117">描述</span><span class="sxs-lookup"><span data-stu-id="7497a-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="7497a-118">对于未处理的任务异常, 不会终止正在运行的进程。</span><span class="sxs-lookup"><span data-stu-id="7497a-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="7497a-119">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="7497a-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="7497a-120">终止正在运行的进程的未处理任务异常。</span><span class="sxs-lookup"><span data-stu-id="7497a-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7497a-121">子元素</span><span class="sxs-lookup"><span data-stu-id="7497a-121">Child Elements</span></span>  
 <span data-ttu-id="7497a-122">无。</span><span class="sxs-lookup"><span data-stu-id="7497a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7497a-123">父元素</span><span class="sxs-lookup"><span data-stu-id="7497a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7497a-124">元素</span><span class="sxs-lookup"><span data-stu-id="7497a-124">Element</span></span>|<span data-ttu-id="7497a-125">描述</span><span class="sxs-lookup"><span data-stu-id="7497a-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7497a-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="7497a-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7497a-127">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="7497a-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="7497a-128">备注</span><span class="sxs-lookup"><span data-stu-id="7497a-128">Remarks</span></span>  
 <span data-ttu-id="7497a-129">如果未观察到与关联的<xref:System.Threading.Tasks.Task>异常, 则不会进行任何<xref:System.Threading.Tasks.Task.Wait%2A>操作, 也不会附加父级, 并且该<xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType>属性不会被视为未观察到。</span><span class="sxs-lookup"><span data-stu-id="7497a-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="7497a-130">在 .NET Framework 4 中, 默认情况下, 如果<xref:System.Threading.Tasks.Task>存在未观察到异常的, 则终结器将引发异常并终止进程。</span><span class="sxs-lookup"><span data-stu-id="7497a-130">In the .NET Framework 4, by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="7497a-131">进程终止由垃圾回收和终止的时间决定。</span><span class="sxs-lookup"><span data-stu-id="7497a-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="7497a-132">为了使开发人员可以更轻松地根据任务编写异步代码, .NET Framework 4.5 更改未观察到异常的此默认行为。</span><span class="sxs-lookup"><span data-stu-id="7497a-132">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="7497a-133">未观察到异常仍会<xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>引发事件, 但在默认情况下, 进程不会终止。</span><span class="sxs-lookup"><span data-stu-id="7497a-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="7497a-134">相反, 引发事件后将忽略此异常, 而不管事件处理程序是否观察到该异常。</span><span class="sxs-lookup"><span data-stu-id="7497a-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="7497a-135">在 .NET Framework 4.5 中, 可以使用应用程序配置文件中的[ \<ThrowUnobservedTaskExceptions > 元素](throwunobservedtaskexceptions-element.md)来启用引发异常的 .NET Framework 4 行为。</span><span class="sxs-lookup"><span data-stu-id="7497a-135">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="7497a-136">还可以通过以下方式之一指定异常行为:</span><span class="sxs-lookup"><span data-stu-id="7497a-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="7497a-137">通过设置环境变量`COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`)。</span><span class="sxs-lookup"><span data-stu-id="7497a-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="7497a-138">通过在 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\中设置注册表 DWORD 值 ThrowUnobservedTaskExceptions = 1.Netframework 键。</span><span class="sxs-lookup"><span data-stu-id="7497a-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7497a-139">示例</span><span class="sxs-lookup"><span data-stu-id="7497a-139">Example</span></span>  
 <span data-ttu-id="7497a-140">下面的示例演示如何使用应用程序配置文件在任务中启用异常引发。</span><span class="sxs-lookup"><span data-stu-id="7497a-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="7497a-141">示例</span><span class="sxs-lookup"><span data-stu-id="7497a-141">Example</span></span>  
 <span data-ttu-id="7497a-142">下面的示例演示如何从任务中引发未观察到异常。</span><span class="sxs-lookup"><span data-stu-id="7497a-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="7497a-143">必须以发布程序的形式运行代码, 才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="7497a-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7497a-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="7497a-144">See also</span></span>

- [<span data-ttu-id="7497a-145">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="7497a-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7497a-146">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="7497a-146">Configuration File Schema</span></span>](../index.md)
