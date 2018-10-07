---
title: WCF 性能计数器
ms.date: 03/30/2017
helpviewer_keywords:
- performance counters [WCF]
ms.assetid: f559b2bd-ed83-4988-97a1-e88f06646609
ms.openlocfilehash: d0ad7ee0bc3ea1d15197e6b8d9888d60b21a2f15
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2018
ms.locfileid: "48846209"
---
# <a name="wcf-performance-counters"></a><span data-ttu-id="c1265-102">WCF 性能计数器</span><span class="sxs-lookup"><span data-stu-id="c1265-102">WCF Performance Counters</span></span>
<span data-ttu-id="c1265-103">Windows Communication Foundation (WCF) 包括大量的性能计数器，可帮助您衡量应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="c1265-103">Windows Communication Foundation (WCF) includes a large set of performance counters to help you gauge your application's performance.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="c1265-104">启用性能计数器</span><span class="sxs-lookup"><span data-stu-id="c1265-104">Enabling Performance Counters</span></span>  
 <span data-ttu-id="c1265-105">您可以启用 WCF 服务的性能计数器通过 WCF 服务的 app.config 配置文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c1265-105">You can enable performance counters for a WCF service through the app.config configuration file of the WCF service as follows:</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <diagnostics performanceCounters="All" />  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="c1265-106">可以将 `performanceCounters` 属性设置为启用特定类型的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c1265-106">The `performanceCounters` attribute can be set to enable a specific type of performance counters.</span></span> <span data-ttu-id="c1265-107">有效值为</span><span class="sxs-lookup"><span data-stu-id="c1265-107">Valid values are</span></span>  
  
-   <span data-ttu-id="c1265-108">All：启用所有类别计数器（ServiceModelService、ServiceModelEndpoint 和 ServiceModelOperation）。</span><span class="sxs-lookup"><span data-stu-id="c1265-108">All: All category counters (ServiceModelService, ServiceModelEndpoint and ServiceModelOperation) are enabled.</span></span>  
  
-   <span data-ttu-id="c1265-109">ServiceOnly：仅启用 ServiceModelService 类别计数器。</span><span class="sxs-lookup"><span data-stu-id="c1265-109">ServiceOnly: Only ServiceModelService category counters are enabled.</span></span> <span data-ttu-id="c1265-110">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="c1265-110">This is the default value.</span></span>  
  
-   <span data-ttu-id="c1265-111">Off：禁用 ServiceModel\* 性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c1265-111">Off: ServiceModel\* performance counters are disabled.</span></span>  
  
 <span data-ttu-id="c1265-112">如果你想要启用的所有 WCF 应用程序的性能计数器，您可以在 Machine.config 文件中放置配置设置。</span><span class="sxs-lookup"><span data-stu-id="c1265-112">If you want to enable performance counters for all WCF applications, you can place the configuration settings in the Machine.config file.</span></span>  <span data-ttu-id="c1265-113">请参阅**增加性能计数器内存大小**节在计算机上配置足够的内存性能计数器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c1265-113">Please see the **Increasing Memory Size for Performance Counters** section below for more information on configuring sufficient memory for performance counters on your machine.</span></span>  
  
 <span data-ttu-id="c1265-114">如果使用 WCF 扩展点，如自定义操作调用程序，则还应发出自己的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c1265-114">If you use WCF extensibility points such as custom operation invokers, you should also emit your own performance counters.</span></span> <span data-ttu-id="c1265-115">这是因为如果实现了扩展点，WCF 可以不再发出的默认路径中的标准性能计数器数据。</span><span class="sxs-lookup"><span data-stu-id="c1265-115">This is because if you implement an extensibility point, WCF may no longer emit the standard performance counter data in the default path.</span></span> <span data-ttu-id="c1265-116">如果未实现手动性能计数器支持，则可能看不到预期的性能计数器数据。</span><span class="sxs-lookup"><span data-stu-id="c1265-116">If you do not implement manual performance counter support, you may not see the performance counter data you expect.</span></span>  
  
 <span data-ttu-id="c1265-117">还可以在代码中启用性能计数器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c1265-117">You can also enable performance counters in your code as follows,</span></span>  
  
```  
using System.Configuration;  
using System.ServiceModel.Configuration;  
using System.ServiceModel.Diagnostics;  
Configuration config = ConfigurationManager.OpenExeConfiguration(  
    ConfigurationUserLevel.None);  
ServiceModelSectionGroup sg = ServiceModelSectionGroup.GetSectionGroup(config);  
sg.Diagnostic.PerformanceCounters = PerformanceCounterScope.All;  
config.Save();  
```  
  
## <a name="viewing-performance-data"></a><span data-ttu-id="c1265-118">查看性能数据</span><span class="sxs-lookup"><span data-stu-id="c1265-118">Viewing Performance Data</span></span>  
 <span data-ttu-id="c1265-119">若要查看性能计数器捕获的数据，则可以使用 Windows 附带的性能监视器 (Perfmon.exe)。</span><span class="sxs-lookup"><span data-stu-id="c1265-119">To view data captured by the performance counters, you can use the Performance Monitor (Perfmon.exe) that comes with Windows.</span></span> <span data-ttu-id="c1265-120">通过转到启动该工具**启动**，然后单击**运行**并键入`perfmon.exe`在对话框中。</span><span class="sxs-lookup"><span data-stu-id="c1265-120">You can launch this tool by going to **Start**, and click **Run** and type `perfmon.exe` in the dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1265-121">性能计数器实例可能会在终结点调度程序处理最后一条消息之前被释放。</span><span class="sxs-lookup"><span data-stu-id="c1265-121">Performance counter instances may be released before the last messages have been processed by the endpoint dispatcher.</span></span> <span data-ttu-id="c1265-122">这可能导致不能为某些消息捕获性能数据。</span><span class="sxs-lookup"><span data-stu-id="c1265-122">This can result in performance data not being captured for a few messages.</span></span>  
  
## <a name="increasing-memory-size-for-performance-counters"></a><span data-ttu-id="c1265-123">增加性能计数器的内存大小</span><span class="sxs-lookup"><span data-stu-id="c1265-123">Increasing Memory Size for Performance Counters</span></span>  
 <span data-ttu-id="c1265-124">WCF 性能计数器类别使用单独的共享的内存。</span><span class="sxs-lookup"><span data-stu-id="c1265-124">WCF uses separate shared memory for its performance counter categories.</span></span>  
  
 <span data-ttu-id="c1265-125">默认情况下，单独的共享内存被设置为全局性能计数器内存大小的四分之一。</span><span class="sxs-lookup"><span data-stu-id="c1265-125">By default, separate shared memory is set to a quarter the size of global performance counter memory.</span></span> <span data-ttu-id="c1265-126">默认的全局性能计数器内存大小为 524,288 字节。</span><span class="sxs-lookup"><span data-stu-id="c1265-126">The default global performance counter memory is 524,288 bytes.</span></span> <span data-ttu-id="c1265-127">因此，三种 WCF 性能计数器类别具有约 128KB 的每个默认大小。</span><span class="sxs-lookup"><span data-stu-id="c1265-127">Therefore, the three WCF performance counter categories have a default size of approximately 128KB each.</span></span> <span data-ttu-id="c1265-128">根据计算机上的 WCF 应用程序的运行时特性，性能计数器内存可能会耗尽。</span><span class="sxs-lookup"><span data-stu-id="c1265-128">Depending upon the runtime characteristics of the WCF applications on a machine, performance counter memory may be exhausted.</span></span> <span data-ttu-id="c1265-129">在此情况下，WCF 将错误写入到应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="c1265-129">When this happens, WCF writes an error to the application event log.</span></span> <span data-ttu-id="c1265-130">该错误的内容声明未加载性能计数器，并声明一个包含异常“System.InvalidOperationException：可用于自定义计数器文件视图的内存不足。”的项。</span><span class="sxs-lookup"><span data-stu-id="c1265-130">The content of the error states that a performance counter was not loaded, and the entry contains the exception "System.InvalidOperationException: Custom counters file view is out of memory."</span></span> <span data-ttu-id="c1265-131">如果在错误级别启用了跟踪，此故障也将被跟踪。</span><span class="sxs-lookup"><span data-stu-id="c1265-131">If tracing is enabled at the error level, this failure is also traced.</span></span> <span data-ttu-id="c1265-132">如果性能计数器内存已用尽，则继续使用已启用的性能计数器运行 WCF 应用程序可能导致性能下降。</span><span class="sxs-lookup"><span data-stu-id="c1265-132">If performance counter memory is exhausted, continuing to run your WCF applications with performance counters enabled could result in performance degradation.</span></span> <span data-ttu-id="c1265-133">如果您是计算机管理员，则应对计算机进行配置，以便分配足够的内存来支持随时可能存在的最大数量的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c1265-133">If you are an administrator of the machine, you should configure it to allocate enough memory to support the maximum number of performance counters that can exist at any time.</span></span>  
  
 <span data-ttu-id="c1265-134">你可以在注册表中的 WCF 类别的性能计数器内存量。</span><span class="sxs-lookup"><span data-stu-id="c1265-134">You can change the amount of performance counter memory for WCF categories in the registry.</span></span> <span data-ttu-id="c1265-135">为此，需要向以下三个位置添加名为 `FileMappingSize` 的新 DWORD 值，并将它设为所需的值（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="c1265-135">To do so, you need to add a new DWORD value named `FileMappingSize` to the three following locations, and set it to the desired value in bytes.</span></span> <span data-ttu-id="c1265-136">重新启动您的计算机以使这些更改生效。</span><span class="sxs-lookup"><span data-stu-id="c1265-136">Reboot your machine so that these changes are taken into effect.</span></span>  
  
-   <span data-ttu-id="c1265-137">HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="c1265-137">HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance</span></span>  
  
-   <span data-ttu-id="c1265-138">HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="c1265-138">HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance</span></span>  
  
-   <span data-ttu-id="c1265-139">HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="c1265-139">HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance</span></span>  
  
 <span data-ttu-id="c1265-140">当释放的大量对象（例如 ServiceHost）等待进行垃圾回收时，`PrivateBytes` 性能计数器将登记一个非常大的数字。</span><span class="sxs-lookup"><span data-stu-id="c1265-140">When a large number of objects (for example, ServiceHost) are disposed of but waiting to be garbage-collected, the `PrivateBytes` performance counter will register an unusually high number.</span></span> <span data-ttu-id="c1265-141">若要解决此问题，可以添加特定于自己的应用程序的计数器，或使用 `performanceCounters` 属性仅启用服务级别计数器。</span><span class="sxs-lookup"><span data-stu-id="c1265-141">To resolve this problem, you can either add your own application-specific counters, or use the `performanceCounters` attribute to enable only service-level counters.</span></span>  
  
## <a name="types-of-performance-counters"></a><span data-ttu-id="c1265-142">性能计数器的类型</span><span class="sxs-lookup"><span data-stu-id="c1265-142">Types of Performance Counters</span></span>  
 <span data-ttu-id="c1265-143">性能计数器可分为三个不同级别：服务、终结点和操作。</span><span class="sxs-lookup"><span data-stu-id="c1265-143">Performance counters are scoped to three different levels: Service, Endpoint and Operation.</span></span>  
  
 <span data-ttu-id="c1265-144">可以使用 WMI 检索性能计数器实例的名称。</span><span class="sxs-lookup"><span data-stu-id="c1265-144">You can use WMI to retrieve the name of a performance counter instance.</span></span> <span data-ttu-id="c1265-145">例如，应用于对象的</span><span class="sxs-lookup"><span data-stu-id="c1265-145">For example,</span></span>  
  
-   <span data-ttu-id="c1265-146">可以通过 WMI 获得服务计数器实例名称[服务](../../../../../docs/framework/wcf/diagnostics/wmi/service.md)实例的"CounterInstanceName"属性。</span><span class="sxs-lookup"><span data-stu-id="c1265-146">Service counter instance name can be obtained through WMI [Service](../../../../../docs/framework/wcf/diagnostics/wmi/service.md) instance's "CounterInstanceName" property.</span></span>  
  
-   <span data-ttu-id="c1265-147">可以通过 WMI 获取终结点计数器实例名称[终结点](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md)实例的"CounterInstanceName"属性。</span><span class="sxs-lookup"><span data-stu-id="c1265-147">Endpoint counter instance name can be obtained through WMI [Endpoint](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) instance's "CounterInstanceName" property.</span></span>  
  
-   <span data-ttu-id="c1265-148">可以通过 WMI 获得操作计数器实例名称[终结点](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md)实例的"GetOperationCounterInstanceName"方法。</span><span class="sxs-lookup"><span data-stu-id="c1265-148">Operation counter instance name can be obtained through WMI [Endpoint](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) instance's "GetOperationCounterInstanceName" method.</span></span>  
  
 <span data-ttu-id="c1265-149">有关 WMI 的详细信息，请参阅[使用 Windows Management Instrumentation 进行诊断](../../../../../docs/framework/wcf/diagnostics/wmi/index.md)。</span><span class="sxs-lookup"><span data-stu-id="c1265-149">For more information on WMI, see [Using Windows Management Instrumentation for Diagnostics](../../../../../docs/framework/wcf/diagnostics/wmi/index.md).</span></span>  
  
### <a name="service-performance-counters"></a><span data-ttu-id="c1265-150">服务性能计数器</span><span class="sxs-lookup"><span data-stu-id="c1265-150">Service performance counters</span></span>  
 <span data-ttu-id="c1265-151">服务性能计数器将服务行为作为整体来进行衡量，可用于诊断服务整体性能。</span><span class="sxs-lookup"><span data-stu-id="c1265-151">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="c1265-152">如果使用性能监视器查看，可以在 `ServiceModelService 4.0.0.0` 性能对象下找到服务性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c1265-152">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="c1265-153">使用以下模式命名计数器实例：</span><span class="sxs-lookup"><span data-stu-id="c1265-153">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
 <span data-ttu-id="c1265-154">服务范围内的计数器是从终结点集合中的计数器聚合来的。</span><span class="sxs-lookup"><span data-stu-id="c1265-154">A counter in a service scope is aggregated from counter in a collection of endpoints.</span></span>  
  
 <span data-ttu-id="c1265-155">创建新的 InstanceContext 时，用于创建服务实例的性能计数器将递增。</span><span class="sxs-lookup"><span data-stu-id="c1265-155">Performance counters for service instance creation are incremented when a new InstanceContext is created.</span></span> <span data-ttu-id="c1265-156">请注意，即使在（通过现有服务）收到非激活消息时，或在从一个会话连接到实例、结束会话然后从其他会话重新进行连接时，也将创建新的 InstanceContext。</span><span class="sxs-lookup"><span data-stu-id="c1265-156">Note that a new InstanceContext is created even when you receive a non-activating message (with an existing service), or when you connect to an instance from one session, end the session, and then reconnect from another session.</span></span>  
  
### <a name="endpoint-performance-counters"></a><span data-ttu-id="c1265-157">终结点性能计数器</span><span class="sxs-lookup"><span data-stu-id="c1265-157">Endpoint performance counters</span></span>  
 <span data-ttu-id="c1265-158">使用终结点性能计数器可以查看反映终结点如何接受消息的数据。</span><span class="sxs-lookup"><span data-stu-id="c1265-158">Endpoint performance counters enable you to look at data reflecting how an endpoint is accepting messages.</span></span> <span data-ttu-id="c1265-159">使用性能监视器查看时，可在 `ServiceModelEndpoint 4.0.0.0` 性能对象下找到终结点性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c1265-159">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing using the Performance Monitor.</span></span> <span data-ttu-id="c1265-160">使用以下模式命名计数器实例：</span><span class="sxs-lookup"><span data-stu-id="c1265-160">The instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 <span data-ttu-id="c1265-161">数据与为单个操作收集的数据类似，但它只在终结点之间聚合。</span><span class="sxs-lookup"><span data-stu-id="c1265-161">The data is similar to what is collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
 <span data-ttu-id="c1265-162">终结点范围内的计数器是从操作集合中的计数器聚合来的。</span><span class="sxs-lookup"><span data-stu-id="c1265-162">A counter in an endpoint scope is aggregated from counters in a collection of operations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1265-163">如果两个终结点具有相同的协定名称和地址，它们将映射到同一个计数器实例中。</span><span class="sxs-lookup"><span data-stu-id="c1265-163">If two endpoints have identical contract names and addresses, they are mapped to the same counter instance.</span></span>  
  
### <a name="operation-performance-counters"></a><span data-ttu-id="c1265-164">操作性能计数器</span><span class="sxs-lookup"><span data-stu-id="c1265-164">Operation performance counters</span></span>  
 <span data-ttu-id="c1265-165">如果使用性能监视器查看，可以在 `ServiceModelOperation 4.0.0.0` 性能对象下找到操作性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c1265-165">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="c1265-166">每个操作都有一个单独的实例。</span><span class="sxs-lookup"><span data-stu-id="c1265-166">Each operation has an individual instance.</span></span> <span data-ttu-id="c1265-167">也就是说，如果给定的协定具有 10 个操作，则有 10 个操作计数器实例与该协定相关联。</span><span class="sxs-lookup"><span data-stu-id="c1265-167">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="c1265-168">对象实例按下面的模式命名：</span><span class="sxs-lookup"><span data-stu-id="c1265-168">The object instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 <span data-ttu-id="c1265-169">使用此计数器可以衡量调用的使用方式以及操作的执行情况。</span><span class="sxs-lookup"><span data-stu-id="c1265-169">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
 <span data-ttu-id="c1265-170">当计数器在多个范围内可见时，从范围的较高一级收集到的数据会与从范围的较低一级收集到的数据相聚合。</span><span class="sxs-lookup"><span data-stu-id="c1265-170">When counters are visible at multiple scopes, data gathered from a higher scope are aggregated with data from lower scopes.</span></span> <span data-ttu-id="c1265-171">例如，终结点处的 `Calls` 表示终结点内所有操作调用的总和；服务处的 `Calls` 表示对服务内所有终结点的所有调用的总和。</span><span class="sxs-lookup"><span data-stu-id="c1265-171">For example, `Calls` at an endpoint represents the sum of all operation calls within the endpoint; `Calls` at a service represents the sum of all calls to all endpoints within the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1265-172">如果一个协定上有两个操作名称，则只能为这两个操作获取一个计数器实例。</span><span class="sxs-lookup"><span data-stu-id="c1265-172">If you have duplicate operation names on a contract, you only get one counter instances for both operations.</span></span>  
  
## <a name="programming-the-wcf-performance-counters"></a><span data-ttu-id="c1265-173">对 WCF 性能计数器进行编程</span><span class="sxs-lookup"><span data-stu-id="c1265-173">Programming the WCF Performance Counters</span></span>  
 <span data-ttu-id="c1265-174">多个文件安装在 SDK 安装文件夹，以便可以以编程方式访问 WCF 性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c1265-174">Several files are installed in the SDK install folder so that you can access the WCF performance counters programmatically.</span></span> <span data-ttu-id="c1265-175">下面列出了这些文件。</span><span class="sxs-lookup"><span data-stu-id="c1265-175">These files are listed as follows.</span></span>  
  
-   <span data-ttu-id="c1265-176">_ServiceModelEndpointPerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="c1265-176">_ServiceModelEndpointPerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="c1265-177">_ServiceModelOperationPerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="c1265-177">_ServiceModelOperationPerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="c1265-178">_ServiceModelServicePerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="c1265-178">_ServiceModelServicePerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="c1265-179">_SMSvcHostPerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="c1265-179">_SMSvcHostPerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="c1265-180">_TransactionBridgePerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="c1265-180">_TransactionBridgePerfCounters.vrg</span></span>  
  
 <span data-ttu-id="c1265-181">有关如何以编程方式访问计数器的详细信息，请参阅[性能计数器编程体系结构](https://go.microsoft.com/fwlink/?LinkId=95179)。</span><span class="sxs-lookup"><span data-stu-id="c1265-181">For more information on how to access the counters programmatically, see [Performance Counter Programming Architecture](https://go.microsoft.com/fwlink/?LinkId=95179).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1265-182">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1265-182">See Also</span></span>  
 [<span data-ttu-id="c1265-183">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="c1265-183">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
