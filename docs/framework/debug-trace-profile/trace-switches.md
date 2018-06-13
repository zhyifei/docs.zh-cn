---
title: 跟踪开关
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tracing [.NET Framework], trace switches
- trace switches, about trace switches
- tracing [.NET Framework], level of detail
- switches, trace
- trace switches
- trace switches, creating custom
ms.assetid: 8ab913aa-f400-4406-9436-f45bc6e54fbe
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8b8ee0d04644cf504354767c296f504a937055d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397489"
---
# <a name="trace-switches"></a><span data-ttu-id="742d5-102">跟踪开关</span><span class="sxs-lookup"><span data-stu-id="742d5-102">Trace Switches</span></span>
<span data-ttu-id="742d5-103">跟踪开关用于启用、禁用和筛选跟踪输出。</span><span class="sxs-lookup"><span data-stu-id="742d5-103">Trace switches enable you to enable, disable, and filter tracing output.</span></span> <span data-ttu-id="742d5-104">它们是代码中存在并可通过 .config 文件在外部配置的对象。</span><span class="sxs-lookup"><span data-stu-id="742d5-104">They are objects that exist in your code and can be configured externally through the .config file.</span></span> <span data-ttu-id="742d5-105">.NET Framework 中提供三种跟踪开关类型： <xref:System.Diagnostics.BooleanSwitch> 类、 <xref:System.Diagnostics.TraceSwitch> 类和 <xref:System.Diagnostics.SourceSwitch> 类。</span><span class="sxs-lookup"><span data-stu-id="742d5-105">There are three types of trace switches provided in the .NET Framework: the <xref:System.Diagnostics.BooleanSwitch> class, the <xref:System.Diagnostics.TraceSwitch> class, and the <xref:System.Diagnostics.SourceSwitch> class.</span></span> <span data-ttu-id="742d5-106"><xref:System.Diagnostics.BooleanSwitch> 类充当切换开关，可启用或禁用各种跟踪语句。</span><span class="sxs-lookup"><span data-stu-id="742d5-106">The <xref:System.Diagnostics.BooleanSwitch> class acts as a toggle switch, either enabling or disabling a variety of trace statements.</span></span> <span data-ttu-id="742d5-107">使用 <xref:System.Diagnostics.TraceSwitch> 和 <xref:System.Diagnostics.SourceSwitch> 类，可以启用特定跟踪级别的跟踪开关，以确保出现为该级别以及其下所有级别指定的 <xref:System.Diagnostics.Trace> 或 <xref:System.Diagnostics.TraceSource> 消息。</span><span class="sxs-lookup"><span data-stu-id="742d5-107">The <xref:System.Diagnostics.TraceSwitch> and <xref:System.Diagnostics.SourceSwitch> classes allow you to enable a trace switch for a particular tracing level so that the <xref:System.Diagnostics.Trace> or <xref:System.Diagnostics.TraceSource> messages specified for that level and all levels below it appear.</span></span> <span data-ttu-id="742d5-108">如果禁用此开关，则不会出现跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="742d5-108">If you disable the switch, the trace messages will not appear.</span></span> <span data-ttu-id="742d5-109">所有这些类均派生自抽象 (MustInherit**T:System.Diagnostics.Switch**) 类 **Switch**，用户开发的任何开关也应如此。</span><span class="sxs-lookup"><span data-stu-id="742d5-109">All these classes derive from the abstract (**MustInherit**) class **Switch**, as should any user-developed switches.</span></span>  
  
 <span data-ttu-id="742d5-110">跟踪开关可用于筛选信息。</span><span class="sxs-lookup"><span data-stu-id="742d5-110">Trace switches can be useful for filtering information.</span></span> <span data-ttu-id="742d5-111">例如，你可能希望查看数据访问模块中的每条跟踪消息，但只查看应用程序其余部分的错误消息。</span><span class="sxs-lookup"><span data-stu-id="742d5-111">For example, you might want to see every tracing message in a data access module, but only error messages in the rest of the application.</span></span> <span data-ttu-id="742d5-112">在这种情况下，则需要分别对数据访问模块和应用程序的其余部分使用一个跟踪开关。</span><span class="sxs-lookup"><span data-stu-id="742d5-112">In that case, you would use one trace switch for the data access module and one switch for the rest of the application.</span></span> <span data-ttu-id="742d5-113">通过使用 .config 文件将开关配置为相应的设置，便可以控制接收的跟踪消息类型。</span><span class="sxs-lookup"><span data-stu-id="742d5-113">By using the .config file to configure the switches to the appropriate settings, you could control what types of trace message you received.</span></span> <span data-ttu-id="742d5-114">有关详细信息，请参阅[如何：创建、初始化和配置跟踪开关](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)。</span><span class="sxs-lookup"><span data-stu-id="742d5-114">For more information, see [How to: Create, Initialize and Configure Trace Switches](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md).</span></span>  
  
 <span data-ttu-id="742d5-115">通常情况下，会在禁用开关的情况下执行已部署的应用程序，以确保在应用程序运行时用户不会看到屏幕上出现的或填满日志文件的不相关跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="742d5-115">Typically, a deployed application is executed with its switches disabled, so that users need not observe a lot of irrelevant trace messages appearing on a screen or filling up a log file as the application runs.</span></span> <span data-ttu-id="742d5-116">如果应用程序执行期间出现了问题，可以停止应用程序，启用开关，然后重新启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="742d5-116">If a problem arises during application execution, you can stop the application, enable the switches, and restart the application.</span></span> <span data-ttu-id="742d5-117">然后，将显示跟踪消息。</span><span class="sxs-lookup"><span data-stu-id="742d5-117">Then the tracing messages will be displayed.</span></span>  
  
 <span data-ttu-id="742d5-118">若要使用开关，首先必须在 BooleanSwitch **T:System.Diagnostics.Switch** 类、 **TraceSwitch** 类或开发人员定义的开关类中创建一个开关对象。</span><span class="sxs-lookup"><span data-stu-id="742d5-118">To use a switch you must first create a switch object from a **BooleanSwitch** class, a **TraceSwitch** class, or a developer-defined switch class.</span></span> <span data-ttu-id="742d5-119">有关创建开发人员定义的开关的详细信息，请参阅 .NET Framework 引用中的 <xref:System.Diagnostics.Switch> 类。</span><span class="sxs-lookup"><span data-stu-id="742d5-119">For more information about creating developer-defined switches, see the <xref:System.Diagnostics.Switch> class in the .NET Framework reference.</span></span> <span data-ttu-id="742d5-120">然后，将设置一个指定何时使用该开关对象的配置值。</span><span class="sxs-lookup"><span data-stu-id="742d5-120">Then you set a configuration value that specifies when the switch object is to be used.</span></span> <span data-ttu-id="742d5-121">然后，可以在各种 Trace **T:System.Diagnostics.Switch** （或 **Debug**）跟踪方法中测试该开关对象的设置。</span><span class="sxs-lookup"><span data-stu-id="742d5-121">You then test the setting of the switch object in various **Trace** (or **Debug**) tracing methods.</span></span>  
  
## <a name="trace-levels"></a><span data-ttu-id="742d5-122">跟踪级别</span><span class="sxs-lookup"><span data-stu-id="742d5-122">Trace Levels</span></span>  
 <span data-ttu-id="742d5-123">使用 TraceSwitch **T:System.Diagnostics.Switch**时，存在其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="742d5-123">When you use **TraceSwitch**, there are additional considerations.</span></span> <span data-ttu-id="742d5-124">TraceSwitch **T:System.Diagnostics.Switch** 对象具有四个属性，这四个属性返回指示开关是否设置为至少一个特殊级别的 **Boolean** 值：</span><span class="sxs-lookup"><span data-stu-id="742d5-124">A **TraceSwitch** object has four properties that return **Boolean** values indicating whether the switch is set to at least a particular level:</span></span>  
  
-   <xref:System.Diagnostics.TraceSwitch.TraceError%2A?displayProperty=nameWithType>  
  
-   <xref:System.Diagnostics.TraceSwitch.TraceWarning%2A?displayProperty=nameWithType>  
  
-   <xref:System.Diagnostics.TraceSwitch.TraceInfo%2A?displayProperty=nameWithType>  
  
-   <xref:System.Diagnostics.TraceSwitch.TraceVerbose%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="742d5-125">通过设置级别，可以将接收的跟踪信息数量限制为仅解决问题所需的信息。</span><span class="sxs-lookup"><span data-stu-id="742d5-125">Levels allow you to limit the amount of tracing information you receive to only that information needed to solve a problem.</span></span> <span data-ttu-id="742d5-126">通过将跟踪开关设置和配置为相应的跟踪级别，可以指定跟踪输出的详细级别。</span><span class="sxs-lookup"><span data-stu-id="742d5-126">You specify the level of detail you want in your tracing output by setting and configuring trace switches to the appropriate trace level.</span></span> <span data-ttu-id="742d5-127">可以选择接收错误消息、警告消息、信息性消息、详细跟踪消息，也可以选择不接收任何消息。</span><span class="sxs-lookup"><span data-stu-id="742d5-127">You can receive error messages, warning messages, informational messages, verbose tracing messages, or no message at all.</span></span>  
  
 <span data-ttu-id="742d5-128">这完全取决于你自身确定与每个级别关联的消息类型。</span><span class="sxs-lookup"><span data-stu-id="742d5-128">It is entirely up to you to decide what kind of message to associate with each level.</span></span> <span data-ttu-id="742d5-129">通常，跟踪消息的内容取决于每个级别关联的内容，但你可以确定级别之间的差异。</span><span class="sxs-lookup"><span data-stu-id="742d5-129">Typically, the content of tracing messages depends on what you associate with each level, but you determine the differences between levels.</span></span> <span data-ttu-id="742d5-130">例如，你可能希望在第 3 级别 (Info**T:System.Diagnostics.Switch**) 提供问题的详细说明，但在第 1 级别 (**Error**) 仅提供错误参考号。</span><span class="sxs-lookup"><span data-stu-id="742d5-130">You might want to provide detailed descriptions of a problem at level 3 (**Info**), for example, but provide only an error reference number at level 1 (**Error**).</span></span> <span data-ttu-id="742d5-131">这完全取决于你自身确定的最适合应用程序的方案。</span><span class="sxs-lookup"><span data-stu-id="742d5-131">It is entirely up to you to decide what scheme works best in your application.</span></span>  
  
 <span data-ttu-id="742d5-132">这些属性与 TraceLevel **T:System.Diagnostics.Switch** 枚举的值 1-4 相对应。</span><span class="sxs-lookup"><span data-stu-id="742d5-132">These properties correspond to the values 1 through 4 of the **TraceLevel** enumeration.</span></span> <span data-ttu-id="742d5-133">下表列出 TraceLevel **T:System.Diagnostics.Switch** 枚举的级别与对应的值。</span><span class="sxs-lookup"><span data-stu-id="742d5-133">The following table lists the levels of the **TraceLevel** enumeration and their values.</span></span>  
  
|<span data-ttu-id="742d5-134">枚举值</span><span class="sxs-lookup"><span data-stu-id="742d5-134">Enumerated value</span></span>|<span data-ttu-id="742d5-135">整数值</span><span class="sxs-lookup"><span data-stu-id="742d5-135">Integer value</span></span>|<span data-ttu-id="742d5-136">所显示的（或写入指定输出目标）的消息类型</span><span class="sxs-lookup"><span data-stu-id="742d5-136">Type of message displayed (or written to a specified output target)</span></span>|  
|----------------------|-------------------|---------------------------------------------------------------------------|  
|<span data-ttu-id="742d5-137">Off</span><span class="sxs-lookup"><span data-stu-id="742d5-137">Off</span></span>|<span data-ttu-id="742d5-138">0</span><span class="sxs-lookup"><span data-stu-id="742d5-138">0</span></span>|<span data-ttu-id="742d5-139">无</span><span class="sxs-lookup"><span data-stu-id="742d5-139">None</span></span>|  
|<span data-ttu-id="742d5-140">Error</span><span class="sxs-lookup"><span data-stu-id="742d5-140">Error</span></span>|<span data-ttu-id="742d5-141">1</span><span class="sxs-lookup"><span data-stu-id="742d5-141">1</span></span>|<span data-ttu-id="742d5-142">仅错误消息</span><span class="sxs-lookup"><span data-stu-id="742d5-142">Only error messages</span></span>|  
|<span data-ttu-id="742d5-143">警告</span><span class="sxs-lookup"><span data-stu-id="742d5-143">Warning</span></span>|<span data-ttu-id="742d5-144">2</span><span class="sxs-lookup"><span data-stu-id="742d5-144">2</span></span>|<span data-ttu-id="742d5-145">警告消息和错误消息</span><span class="sxs-lookup"><span data-stu-id="742d5-145">Warning messages and error messages</span></span>|  
|<span data-ttu-id="742d5-146">T:System.Diagnostics.Switch</span><span class="sxs-lookup"><span data-stu-id="742d5-146">Info</span></span>|<span data-ttu-id="742d5-147">3</span><span class="sxs-lookup"><span data-stu-id="742d5-147">3</span></span>|<span data-ttu-id="742d5-148">信息性消息、警告消息和错误消息</span><span class="sxs-lookup"><span data-stu-id="742d5-148">Informational messages, warning messages, and error messages</span></span>|  
|<span data-ttu-id="742d5-149">详细</span><span class="sxs-lookup"><span data-stu-id="742d5-149">Verbose</span></span>|<span data-ttu-id="742d5-150">4</span><span class="sxs-lookup"><span data-stu-id="742d5-150">4</span></span>|<span data-ttu-id="742d5-151">详细消息、信息性消息、警告消息和错误消息</span><span class="sxs-lookup"><span data-stu-id="742d5-151">Verbose messages, informational messages, warning messages, and error messages</span></span>|  
  
 <span data-ttu-id="742d5-152">TraceSwitch **T:System.Diagnostics.Switch** 属性指示开关的最大跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="742d5-152">The **TraceSwitch** properties indicate the maximum trace level for the switch.</span></span> <span data-ttu-id="742d5-153">也就是说，将在指定的级别以及其下的所有级别写入跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="742d5-153">That is, tracing information is written for the level specified as well as for all lower levels.</span></span> <span data-ttu-id="742d5-154">例如，如果 TraceInfo **T:System.Diagnostics.Switch** 为 **true**，则 **TraceError** 和 **TraceWarning** 也为 **true** ，但 **TraceVerbose** 可能为 **false**。</span><span class="sxs-lookup"><span data-stu-id="742d5-154">For example, if **TraceInfo** is **true**, then **TraceError** and **TraceWarning** are also **true** but **TraceVerbose** might well be **false**.</span></span>  
  
 <span data-ttu-id="742d5-155">这些属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="742d5-155">These properties are read-only.</span></span> <span data-ttu-id="742d5-156">当设置了 **TraceLevel** 属性时，TraceSwitch **T:System.Diagnostics.Switch** 对象会自动对这些属性进行设置。</span><span class="sxs-lookup"><span data-stu-id="742d5-156">The **TraceSwitch** object automatically sets them when the **TraceLevel** property is set.</span></span> <span data-ttu-id="742d5-157">例如：</span><span class="sxs-lookup"><span data-stu-id="742d5-157">For example:</span></span>  
  
```vb  
Dim myTraceSwitch As New TraceSwitch("SwitchOne", "The first switch")  
myTraceSwitch.Level = TraceLevel.Info  
' This message box displays true, because setting the level to  
' TraceLevel.Info sets all lower levels to true as well.  
MessageBox.Show(myTraceSwitch.TraceWarning.ToString())  
' This messagebox displays false.  
MessageBox.Show(myTraceSwitch.TraceVerbose.ToString())  
```  
  
```csharp  
System.Diagnostics.TraceSwitch myTraceSwitch =   
   new System.Diagnostics.TraceSwitch("SwitchOne", "The first switch");  
myTraceSwitch.Level = System.Diagnostics.TraceLevel.Info;  
// This message box displays true, because setting the level to   
// TraceLevel.Info sets all lower levels to true as well.  
MessageBox.Show(myTraceSwitch.TraceWarning.ToString());  
// This message box displays false.  
MessageBox.Show(myTraceSwitch.TraceVerbose.ToString());  
```  
  
## <a name="developer-defined-switches"></a><span data-ttu-id="742d5-158">开发人员定义的开关</span><span class="sxs-lookup"><span data-stu-id="742d5-158">Developer-Defined Switches</span></span>  
 <span data-ttu-id="742d5-159">除了提供 BooleanSwitch **T:System.Diagnostics.Switch** 和 **TraceSwitch**之外，可以通过从 **Switch** 类继承以及将基类方法重写为自定义的方法定义自己的开关。</span><span class="sxs-lookup"><span data-stu-id="742d5-159">In addition to providing **BooleanSwitch** and **TraceSwitch**, you can define your own switches by inheriting from the **Switch** class and overriding the base class methods with customized methods.</span></span> <span data-ttu-id="742d5-160">有关创建开发人员定义的开关的详细信息，请参阅 .NET Framework 引用中的 <xref:System.Diagnostics.Switch> 类。</span><span class="sxs-lookup"><span data-stu-id="742d5-160">For more information about creating developer-defined switches, see the <xref:System.Diagnostics.Switch> class in the .NET Framework reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="742d5-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="742d5-161">See Also</span></span>  
 [<span data-ttu-id="742d5-162">跟踪侦听器</span><span class="sxs-lookup"><span data-stu-id="742d5-162">Trace Listeners</span></span>](../../../docs/framework/debug-trace-profile/trace-listeners.md)  
 [<span data-ttu-id="742d5-163">如何：向应用程序代码添加跟踪语句</span><span class="sxs-lookup"><span data-stu-id="742d5-163">How to: Add Trace Statements to Application Code</span></span>](../../../docs/framework/debug-trace-profile/how-to-add-trace-statements-to-application-code.md)  
 [<span data-ttu-id="742d5-164">跟踪应用程序和在应用程序中插入检测点</span><span class="sxs-lookup"><span data-stu-id="742d5-164">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
