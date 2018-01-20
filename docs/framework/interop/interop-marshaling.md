---
title: "互操作封送处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- marshaling, COM interop
- interop marshaling
- interop marshaling, about interop marshaling
ms.assetid: 115f7a2f-d422-4605-ab36-13a8dd28142a
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 17638390a07f752a7101209e5635752bc0511d1d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="interop-marshaling"></a><span data-ttu-id="48bf4-102">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="48bf4-102">Interop Marshaling</span></span>
<a name="top"></a> <span data-ttu-id="48bf4-103">互操作封送处理控制调用期间，通过方法自变量和返回值在托管内存和非托管内存之间传递数据的方式。</span><span class="sxs-lookup"><span data-stu-id="48bf4-103">Interop marshaling governs how data is passed in method arguments and return values between managed and unmanaged memory during calls.</span></span> <span data-ttu-id="48bf4-104">互操作封送处理是由公共语言运行时的封送处理服务执行的运行时活动。</span><span class="sxs-lookup"><span data-stu-id="48bf4-104">Interop marshaling is a run-time activity performed by the common language runtime's marshaling service.</span></span>  
  
 <span data-ttu-id="48bf4-105">大多数数据类型在托管和非托管内存中都具有公共的表示形式。</span><span class="sxs-lookup"><span data-stu-id="48bf4-105">Most data types have common representations in both managed and unmanaged memory.</span></span> <span data-ttu-id="48bf4-106">互操作封送拆收器为你处理这些类型。</span><span class="sxs-lookup"><span data-stu-id="48bf4-106">The interop marshaler handles these types for you.</span></span> <span data-ttu-id="48bf4-107">其他类型可能是不明确的，或根本不在托管内存中表示。</span><span class="sxs-lookup"><span data-stu-id="48bf4-107">Other types can be ambiguous or not represented at all in managed memory.</span></span>  
  
 <span data-ttu-id="48bf4-108">不明确的类型可能具有多种映射到单个托管类型的非托管表示形式，或者可能缺少类型信息（如数组的大小）。</span><span class="sxs-lookup"><span data-stu-id="48bf4-108">An ambiguous type can have either multiple unmanaged representations that map to a single managed type, or missing type information, such as the size of an array.</span></span> <span data-ttu-id="48bf4-109">对于不明确的类型，封送拆收器提供默认表示形式和替换表示形式（如果存在多种表示形式）。</span><span class="sxs-lookup"><span data-stu-id="48bf4-109">For ambiguous types, the marshaler provides a default representation and alternative representations where multiple representations exist.</span></span> <span data-ttu-id="48bf4-110">可以向封送拆收器提供有关它如何封送不明确类型的显式指令。</span><span class="sxs-lookup"><span data-stu-id="48bf4-110">You can supply explicit instructions to the marshaler on how it is to marshal an ambiguous type.</span></span>  
  
 <span data-ttu-id="48bf4-111">本概述包含以下几节：</span><span class="sxs-lookup"><span data-stu-id="48bf4-111">This overview contains the following sections:</span></span>  
  
-   [<span data-ttu-id="48bf4-112">平台调用和 COM 互操作模型</span><span class="sxs-lookup"><span data-stu-id="48bf4-112">Platform Invoke and COM Interop Models</span></span>](#platform_invoke_and_com_interop_models)  
  
-   [<span data-ttu-id="48bf4-113">封送和 COM 单元</span><span class="sxs-lookup"><span data-stu-id="48bf4-113">Marshaling and COM Apartments</span></span>](#marshaling_and_com_apartments)  
  
-   [<span data-ttu-id="48bf4-114">封送远程调用</span><span class="sxs-lookup"><span data-stu-id="48bf4-114">Marshaling Remote Calls</span></span>](#marshaling_remote_calls)  
  
-   [<span data-ttu-id="48bf4-115">相关主题</span><span class="sxs-lookup"><span data-stu-id="48bf4-115">Related Topics</span></span>](#related_topics)  
  
-   [<span data-ttu-id="48bf4-116">引用</span><span class="sxs-lookup"><span data-stu-id="48bf4-116">Reference</span></span>](#reference)  
  
<a name="platform_invoke_and_com_interop_models"></a>   
## <a name="platform-invoke-and-com-interop-models"></a><span data-ttu-id="48bf4-117">平台调用和 COM 互操作模型</span><span class="sxs-lookup"><span data-stu-id="48bf4-117">Platform Invoke and COM Interop Models</span></span>  
 <span data-ttu-id="48bf4-118">公共语言运行时提供两种用于与非托管代码进行交互的机制：</span><span class="sxs-lookup"><span data-stu-id="48bf4-118">The common language runtime provides two mechanisms for interoperating with unmanaged code:</span></span>  
  
-   <span data-ttu-id="48bf4-119">平台调用，它使托管代码能够调用从非托管库中导出的函数。</span><span class="sxs-lookup"><span data-stu-id="48bf4-119">Platform invoke, which enables managed code to call functions exported from an unmanaged library.</span></span>  
  
-   <span data-ttu-id="48bf4-120">COM 互操作，它使托管代码能够通过接口与组件对象模型 (COM) 对象交互。</span><span class="sxs-lookup"><span data-stu-id="48bf4-120">COM interop, which enables managed code to interact with Component Object Model (COM) objects through interfaces.</span></span>  
  
 <span data-ttu-id="48bf4-121">平台调用和 COM 互操作都使用互操作封送处理在调用方和被调用方之间准确地移动方法自变量，并且如果需要，也可以将数据从被调用方移回调用方。</span><span class="sxs-lookup"><span data-stu-id="48bf4-121">Both platform invoke and COM interop use interop marshaling to accurately move method arguments between caller and callee and back, if required.</span></span> <span data-ttu-id="48bf4-122">正如下图所示，除涉及 [回调函数](../../../docs/framework/interop/callback-functions.md) 以外，平台调用方法调用从托管代码流向非托管代码，而绝不会以相反方向流动。</span><span class="sxs-lookup"><span data-stu-id="48bf4-122">As the following illustration shows, a platform invoke method call flows from managed to unmanaged code and never the other way, except when [callback functions](../../../docs/framework/interop/callback-functions.md) are involved.</span></span> <span data-ttu-id="48bf4-123">虽然平台调用的调用只能从托管代码流向非托管代码，但是数据仍然可以作为输入参数或输出参数在两个方向流动。</span><span class="sxs-lookup"><span data-stu-id="48bf4-123">Even though platform invoke calls can flow only from managed to unmanaged code, data can flow in both directions as input or output parameters.</span></span> <span data-ttu-id="48bf4-124">COM 互操作方法调用可以在任一方向流动。</span><span class="sxs-lookup"><span data-stu-id="48bf4-124">COM interop method calls can flow in either direction.</span></span>  
  
 <span data-ttu-id="48bf4-125">![平台调用](../../../docs/framework/interop/media/interopmarshaling.png "interopmarshaling")</span><span class="sxs-lookup"><span data-stu-id="48bf4-125">![Platform invoke](../../../docs/framework/interop/media/interopmarshaling.png "interopmarshaling")</span></span>  
<span data-ttu-id="48bf4-126">平台调用和 COM 互操作调用流</span><span class="sxs-lookup"><span data-stu-id="48bf4-126">Platform invoke and COM interop call flow</span></span>  
  
 <span data-ttu-id="48bf4-127">在最低级别，这两种机制都使用同一种互操作封送处理服务；不过，某些数据类型则仅受 COM 互操作或平台调用支持。</span><span class="sxs-lookup"><span data-stu-id="48bf4-127">At the lowest level, both mechanisms use the same interop marshaling service; however, certain data types are supported exclusively by COM interop or platform invoke.</span></span> <span data-ttu-id="48bf4-128">有关详细信息，请参阅 [默认封送行为](../../../docs/framework/interop/default-marshaling-behavior.md)。</span><span class="sxs-lookup"><span data-stu-id="48bf4-128">For details, see [Default Marshaling Behavior](../../../docs/framework/interop/default-marshaling-behavior.md).</span></span>  
  
 [<span data-ttu-id="48bf4-129">返回页首</span><span class="sxs-lookup"><span data-stu-id="48bf4-129">Back to top</span></span>](#top)  
  
<a name="marshaling_and_com_apartments"></a>   
## <a name="marshaling-and-com-apartments"></a><span data-ttu-id="48bf4-130">封送和 COM 单元</span><span class="sxs-lookup"><span data-stu-id="48bf4-130">Marshaling and COM Apartments</span></span>  
 <span data-ttu-id="48bf4-131">互操作封送拆收器在公共语言运行时堆和非托管堆之间封送数据。</span><span class="sxs-lookup"><span data-stu-id="48bf4-131">The interop marshaler marshals data between the common language runtime heap and the unmanaged heap.</span></span> <span data-ttu-id="48bf4-132">每当调用方和被调用方无法操作数据的同一个实例时就发生封送。</span><span class="sxs-lookup"><span data-stu-id="48bf4-132">Marshaling occurs whenever the caller and callee cannot operate on the same instance of data.</span></span> <span data-ttu-id="48bf4-133">互操作封送拆收器使调用方和被调用方都能够看上去像是在操作同一数据，即使它们都有自己的数据副本。</span><span class="sxs-lookup"><span data-stu-id="48bf4-133">The interop marshaler makes it possible for the caller and callee to appear to be operating on the same data even if they have their own copy of the data.</span></span>  
  
 <span data-ttu-id="48bf4-134">COM 也有一个在 COM 单元或不同的 COM 进程之间封送数据的封送拆收器。</span><span class="sxs-lookup"><span data-stu-id="48bf4-134">COM also has a marshaler that marshals data between COM apartments or different COM processes.</span></span> <span data-ttu-id="48bf4-135">当在同一个 COM 单元内的托管和非托管代码之间进行调用时，互操作封送拆收器是涉及到的唯一一个封送拆收器。</span><span class="sxs-lookup"><span data-stu-id="48bf4-135">When calling between managed and unmanaged code within the same COM apartment, the interop marshaler is the only marshaler involved.</span></span> <span data-ttu-id="48bf4-136">当在另一个 COM 单元或另一个进程中的托管代码和非托管代码之间进行调用时，则同时涉及互操作封送拆收器和 COM 封送拆收器。</span><span class="sxs-lookup"><span data-stu-id="48bf4-136">When calling between managed code and unmanaged code in a different COM apartment or a different process, both the interop marshaler and the COM marshaler are involved.</span></span>  
  
### <a name="com-clients-and-managed-servers"></a><span data-ttu-id="48bf4-137">COM 客户端和托管服务器</span><span class="sxs-lookup"><span data-stu-id="48bf4-137">COM Clients and Managed Servers</span></span>  
 <span data-ttu-id="48bf4-138">具有由 [Regasm.exe（程序集注册工具）](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) 注册的类型库的导出的托管服务器有一个设置为 `Both` 的 `ThreadingModel` 注册表项。</span><span class="sxs-lookup"><span data-stu-id="48bf4-138">An exported managed server with a type library registered by the [Regasm.exe (Assembly Registration Tool)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) has a `ThreadingModel` registry entry set to `Both`.</span></span> <span data-ttu-id="48bf4-139">此值指示服务器可以在单线程单元 (STA) 或多线程单元 (MTA) 中激活。</span><span class="sxs-lookup"><span data-stu-id="48bf4-139">This value indicates that the server can be activated in a single-threaded apartment (STA) or a multithreaded apartment (MTA).</span></span> <span data-ttu-id="48bf4-140">服务器对象在与其调用方相同的单元中创建，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="48bf4-140">The server object is created in the same apartment as its caller, as shown in the following table.</span></span>  
  
|<span data-ttu-id="48bf4-141">COM 客户端</span><span class="sxs-lookup"><span data-stu-id="48bf4-141">COM client</span></span>|<span data-ttu-id="48bf4-142">.NET 服务器</span><span class="sxs-lookup"><span data-stu-id="48bf4-142">.NET server</span></span>|<span data-ttu-id="48bf4-143">封送要求</span><span class="sxs-lookup"><span data-stu-id="48bf4-143">Marshaling requirements</span></span>|  
|----------------|-----------------|-----------------------------|  
|<span data-ttu-id="48bf4-144">STA</span><span class="sxs-lookup"><span data-stu-id="48bf4-144">STA</span></span>|<span data-ttu-id="48bf4-145">`Both` 将变成 STA。</span><span class="sxs-lookup"><span data-stu-id="48bf4-145">`Both` becomes STA.</span></span>|<span data-ttu-id="48bf4-146">相同单元封送。</span><span class="sxs-lookup"><span data-stu-id="48bf4-146">Same-apartment marshaling.</span></span>|  
|<span data-ttu-id="48bf4-147">MTA</span><span class="sxs-lookup"><span data-stu-id="48bf4-147">MTA</span></span>|<span data-ttu-id="48bf4-148">`Both` 将变成 MTA。</span><span class="sxs-lookup"><span data-stu-id="48bf4-148">`Both` becomes MTA.</span></span>|<span data-ttu-id="48bf4-149">相同单元封送。</span><span class="sxs-lookup"><span data-stu-id="48bf4-149">Same-apartment marshaling.</span></span>|  
  
 <span data-ttu-id="48bf4-150">由于客户端和服务器位于同一单元中，因此互操作封送处理服务将自动处理所有数据封送。</span><span class="sxs-lookup"><span data-stu-id="48bf4-150">Because the client and server are in the same apartment, the interop marshaling service automatically handles all data marshaling.</span></span> <span data-ttu-id="48bf4-151">下图显示了在同一个 COM 样式的单元内的托管和非托管堆之间进行的互操作封送处理服务。</span><span class="sxs-lookup"><span data-stu-id="48bf4-151">The following illustration shows the interop marshaling service operating between managed and unmanaged heaps within the same COM-style apartment.</span></span>  
  
 <span data-ttu-id="48bf4-152">![互操作封送处理](../../../docs/framework/interop/media/interopheap.gif "interopheap")</span><span class="sxs-lookup"><span data-stu-id="48bf4-152">![Interop marshaling](../../../docs/framework/interop/media/interopheap.gif "interopheap")</span></span>  
<span data-ttu-id="48bf4-153">相同单元封送进程</span><span class="sxs-lookup"><span data-stu-id="48bf4-153">Same-apartment marshaling process</span></span>  
  
 <span data-ttu-id="48bf4-154">如果计划导出托管服务器，请注意，COM 客户端确定服务器的单元。</span><span class="sxs-lookup"><span data-stu-id="48bf4-154">If you plan to export a managed server, be aware that the COM client determines the apartment of the server.</span></span> <span data-ttu-id="48bf4-155">在 MTA 中初始化的 COM 客户端所调用的托管服务器必须确保线程安全。</span><span class="sxs-lookup"><span data-stu-id="48bf4-155">A managed server called by a COM client initialized in an MTA must ensure thread safety.</span></span>  
  
### <a name="managed-clients-and-com-servers"></a><span data-ttu-id="48bf4-156">托管客户端和 COM 服务器</span><span class="sxs-lookup"><span data-stu-id="48bf4-156">Managed Clients and COM Servers</span></span>  
 <span data-ttu-id="48bf4-157">托管客户端单元的默认设置为 MTA；但是，.NET 客户端的应用程序类型可以更改默认设置。</span><span class="sxs-lookup"><span data-stu-id="48bf4-157">The default setting for managed client apartments is MTA; however, the application type of the .NET client can change the default setting.</span></span> <span data-ttu-id="48bf4-158">例如，[!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] 客户端单元设置为 STA。</span><span class="sxs-lookup"><span data-stu-id="48bf4-158">For example, a [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] client apartment setting is STA.</span></span> <span data-ttu-id="48bf4-159">可以使用 <xref:System.STAThreadAttribute?displayProperty=nameWithType>、<xref:System.MTAThreadAttribute?displayProperty=nameWithType>、<xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> 属性或 <xref:System.Web.UI.Page.AspCompatMode%2A?displayProperty=nameWithType> 属性检查并更改托管客户端的单元设置。</span><span class="sxs-lookup"><span data-stu-id="48bf4-159">You can use the <xref:System.STAThreadAttribute?displayProperty=nameWithType>, the <xref:System.MTAThreadAttribute?displayProperty=nameWithType>, the <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> property, or the <xref:System.Web.UI.Page.AspCompatMode%2A?displayProperty=nameWithType> property to examine and change the apartment setting of a managed client.</span></span>  
  
 <span data-ttu-id="48bf4-160">组件的作者设置 COM 服务器的线程关联。</span><span class="sxs-lookup"><span data-stu-id="48bf4-160">The author of the component sets the thread affinity of a COM server.</span></span> <span data-ttu-id="48bf4-161">下表显示 .NET 客户端和 COM 服务器的单元设置的组合。</span><span class="sxs-lookup"><span data-stu-id="48bf4-161">The following table shows the combinations of apartment settings for .NET clients and COM servers.</span></span> <span data-ttu-id="48bf4-162">同时还显示得到的针对这些组合的封送要求。</span><span class="sxs-lookup"><span data-stu-id="48bf4-162">It also shows the resulting marshaling requirements for the combinations.</span></span>  
  
|<span data-ttu-id="48bf4-163">.NET 客户端</span><span class="sxs-lookup"><span data-stu-id="48bf4-163">.NET client</span></span>|<span data-ttu-id="48bf4-164">COM 服务器</span><span class="sxs-lookup"><span data-stu-id="48bf4-164">COM server</span></span>|<span data-ttu-id="48bf4-165">封送要求</span><span class="sxs-lookup"><span data-stu-id="48bf4-165">Marshaling requirements</span></span>|  
|-----------------|----------------|-----------------------------|  
|<span data-ttu-id="48bf4-166">MTA（默认值）</span><span class="sxs-lookup"><span data-stu-id="48bf4-166">MTA (default)</span></span>|<span data-ttu-id="48bf4-167">MTA</span><span class="sxs-lookup"><span data-stu-id="48bf4-167">MTA</span></span><br /><br /> <span data-ttu-id="48bf4-168">STA</span><span class="sxs-lookup"><span data-stu-id="48bf4-168">STA</span></span>|<span data-ttu-id="48bf4-169">互操作封送处理。</span><span class="sxs-lookup"><span data-stu-id="48bf4-169">Interop marshaling.</span></span><br /><br /> <span data-ttu-id="48bf4-170">互操作封送处理和 COM 封送处理。</span><span class="sxs-lookup"><span data-stu-id="48bf4-170">Interop and COM marshaling.</span></span>|  
|<span data-ttu-id="48bf4-171">STA</span><span class="sxs-lookup"><span data-stu-id="48bf4-171">STA</span></span>|<span data-ttu-id="48bf4-172">MTA</span><span class="sxs-lookup"><span data-stu-id="48bf4-172">MTA</span></span><br /><br /> <span data-ttu-id="48bf4-173">STA</span><span class="sxs-lookup"><span data-stu-id="48bf4-173">STA</span></span>|<span data-ttu-id="48bf4-174">互操作封送处理和 COM 封送处理。</span><span class="sxs-lookup"><span data-stu-id="48bf4-174">Interop and COM marshaling.</span></span><br /><br /> <span data-ttu-id="48bf4-175">互操作封送处理。</span><span class="sxs-lookup"><span data-stu-id="48bf4-175">Interop marshaling.</span></span>|  
  
 <span data-ttu-id="48bf4-176">当托管客户端和非托管服务器位于同一单元中时，互操作封送处理服务处理所有数据封送。</span><span class="sxs-lookup"><span data-stu-id="48bf4-176">When a managed client and unmanaged server are in the same apartment, the interop marshaling service handles all data marshaling.</span></span> <span data-ttu-id="48bf4-177">但是，当客户端和服务器在不同的单元中初始化时，还需要 COM 封送处理。</span><span class="sxs-lookup"><span data-stu-id="48bf4-177">However, when client and server are initialized in different apartments, COM marshaling is also required.</span></span> <span data-ttu-id="48bf4-178">下图显示跨单元调用的元素。</span><span class="sxs-lookup"><span data-stu-id="48bf4-178">The following illustration shows the elements of a cross-apartment call.</span></span>  
  
 <span data-ttu-id="48bf4-179">![COM 封送处理](../../../docs/framework/interop/media/singleprocessmultapt.gif "singleprocessmultapt")</span><span class="sxs-lookup"><span data-stu-id="48bf4-179">![COM marshaling](../../../docs/framework/interop/media/singleprocessmultapt.gif "singleprocessmultapt")</span></span>  
<span data-ttu-id="48bf4-180">.NET 客户端和 COM 对象之间的跨单元调用</span><span class="sxs-lookup"><span data-stu-id="48bf4-180">Cross-apartment call between a .NET client and COM object</span></span>  
  
 <span data-ttu-id="48bf4-181">对于跨单元封送，可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="48bf4-181">For cross-apartment marshaling, you can do the following:</span></span>  
  
-   <span data-ttu-id="48bf4-182">接受跨单元封送的系统开销，它只在存在许多跨边界调用时才值得注意。</span><span class="sxs-lookup"><span data-stu-id="48bf4-182">Accept the overhead of the cross-apartment marshaling, which is noticeable only when there are many calls across the boundary.</span></span> <span data-ttu-id="48bf4-183">若要使调用能够成功跨过单元边界，必须注册 COM 组件的类型库。</span><span class="sxs-lookup"><span data-stu-id="48bf4-183">You must register the type library of the COM component for calls to successfully cross the apartment boundary.</span></span>  
  
-   <span data-ttu-id="48bf4-184">通过将客户端线程设置为 STA 或 MTA 改变主线程。</span><span class="sxs-lookup"><span data-stu-id="48bf4-184">Alter the main thread by setting the client thread to STA or MTA.</span></span> <span data-ttu-id="48bf4-185">如，如果 C# 客户端调用许多 STA COM 组件，则可以通过将主线程设置为 STA 来避免跨单元封送。</span><span class="sxs-lookup"><span data-stu-id="48bf4-185">For example, if your C# client calls many STA COM components, you can avoid cross-apartment marshaling by setting the main thread to STA.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="48bf4-186">将 C# 客户端的线程设置为 STA 后，对 MTA COM 组件的调用将需要跨单元封送。</span><span class="sxs-lookup"><span data-stu-id="48bf4-186">Once the thread of a C# client is set to STA, calls to MTA COM components will require cross-apartment marshaling.</span></span>  
  
 <span data-ttu-id="48bf4-187">有关显式选择单元模型的说明， 请参阅 [托管和非托管线程处理](http://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5)。</span><span class="sxs-lookup"><span data-stu-id="48bf4-187">For instructions on explicitly selecting an apartment model, see [Managed and Unmanaged Threading](http://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5).</span></span>  
  
 [<span data-ttu-id="48bf4-188">返回页首</span><span class="sxs-lookup"><span data-stu-id="48bf4-188">Back to top</span></span>](#top)  
  
<a name="marshaling_remote_calls"></a>   
## <a name="marshaling-remote-calls"></a><span data-ttu-id="48bf4-189">封送远程调用</span><span class="sxs-lookup"><span data-stu-id="48bf4-189">Marshaling Remote Calls</span></span>  
 <span data-ttu-id="48bf4-190">与跨单元封送一样，只要对象驻留在不同的进程中，托管代码和非托管代码之间的每个调用就都涉及 COM 封送处理。</span><span class="sxs-lookup"><span data-stu-id="48bf4-190">As with cross-apartment marshaling, COM marshaling is involved in each call between managed and unmanaged code whenever the objects reside in separate processes.</span></span> <span data-ttu-id="48bf4-191">例如：</span><span class="sxs-lookup"><span data-stu-id="48bf4-191">For example:</span></span>  
  
-   <span data-ttu-id="48bf4-192">调用远程主机上的托管服务器的 COM 客户端使用分布式 COM (DCOM)。</span><span class="sxs-lookup"><span data-stu-id="48bf4-192">A COM client that invokes a managed server on a remote host uses distributed COM (DCOM).</span></span>  
  
-   <span data-ttu-id="48bf4-193">调用远程主机上的 COM 服务器的托管客户端使用 DCOM。</span><span class="sxs-lookup"><span data-stu-id="48bf4-193">A managed client that invokes a COM server on a remote host uses DCOM.</span></span>  
  
 <span data-ttu-id="48bf4-194">下图显示互操作封送处理和 COM 封送处理如何跨进程和主机边界提供通信信道。</span><span class="sxs-lookup"><span data-stu-id="48bf4-194">The following illustration shows how interop marshaling and COM marshaling provide communications channels across process and host boundaries.</span></span>  
  
 <span data-ttu-id="48bf4-195">![COM 封送处理](../../../docs/framework/interop/media/interophost.gif "interophost")</span><span class="sxs-lookup"><span data-stu-id="48bf4-195">![COM marshaling](../../../docs/framework/interop/media/interophost.gif "interophost")</span></span>  
<span data-ttu-id="48bf4-196">跨进程封送</span><span class="sxs-lookup"><span data-stu-id="48bf4-196">Cross-process marshaling</span></span>  
  
### <a name="preserving-identity"></a><span data-ttu-id="48bf4-197">保留标识</span><span class="sxs-lookup"><span data-stu-id="48bf4-197">Preserving Identity</span></span>  
 <span data-ttu-id="48bf4-198">公共语言运行时保留托管引用和非托管引用的标识。</span><span class="sxs-lookup"><span data-stu-id="48bf4-198">The common language runtime preserves the identity of managed and unmanaged references.</span></span> <span data-ttu-id="48bf4-199">下图显示跨进程和主机边界的直接非托管引用（顶部行）和直接托管引用（底部行）的流。</span><span class="sxs-lookup"><span data-stu-id="48bf4-199">The following illustration shows the flow of direct unmanaged references (top row) and direct managed references (bottom row) across process and host boundaries.</span></span>  
  
 <span data-ttu-id="48bf4-200">![COM 可调用包装器和运行时可调用包装器](../../../docs/framework/interop/media/interopdirectref.gif "interopdirectref")</span><span class="sxs-lookup"><span data-stu-id="48bf4-200">![COM callable wrapper and runtime callable wrapper](../../../docs/framework/interop/media/interopdirectref.gif "interopdirectref")</span></span>  
<span data-ttu-id="48bf4-201">跨进程和主机边界传递引用</span><span class="sxs-lookup"><span data-stu-id="48bf4-201">Reference passing across process and host boundaries</span></span>  
  
 <span data-ttu-id="48bf4-202">在此图中：</span><span class="sxs-lookup"><span data-stu-id="48bf4-202">In this illustration:</span></span>  
  
-   <span data-ttu-id="48bf4-203">非托管客户端从一个托管对象获取一个对 COM 对象的引用，而该托管对象是从一台远程主机获取该引用的。</span><span class="sxs-lookup"><span data-stu-id="48bf4-203">An unmanaged client gets a reference to a COM object from a managed object that gets this reference from a remote host.</span></span> <span data-ttu-id="48bf4-204">远程处理机制为 DCOM。</span><span class="sxs-lookup"><span data-stu-id="48bf4-204">The remoting mechanism is DCOM.</span></span>  
  
-   <span data-ttu-id="48bf4-205">托管客户端从一个 COM 对象获取一个对托管对象的引用，而该 COM 对象是从一台远程主机获取该引用的。</span><span class="sxs-lookup"><span data-stu-id="48bf4-205">A managed client gets a reference to a managed object from a COM object that gets this reference from a remote host.</span></span> <span data-ttu-id="48bf4-206">远程处理机制为 DCOM。</span><span class="sxs-lookup"><span data-stu-id="48bf4-206">The remoting mechanism is DCOM.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="48bf4-207">必须注册该托管服务器的导出类型库。</span><span class="sxs-lookup"><span data-stu-id="48bf4-207">The exported type library of the managed server must be registered.</span></span>  
  
 <span data-ttu-id="48bf4-208">调用方和被调用方之间的进程边界的数目并不相干；对于进程内和进程外调用都会发生相同的直接引用处理。</span><span class="sxs-lookup"><span data-stu-id="48bf4-208">The number of process boundaries between caller and callee is irrelevant; the same direct referencing occurs for in-process and out-of-process calls.</span></span>  
  
### <a name="managed-remoting"></a><span data-ttu-id="48bf4-209">托管远程处理</span><span class="sxs-lookup"><span data-stu-id="48bf4-209">Managed Remoting</span></span>  
 <span data-ttu-id="48bf4-210">运行时还提供了托管远程处理，可用于跨进程和主机边界建立托管对象之间的通信信道。</span><span class="sxs-lookup"><span data-stu-id="48bf4-210">The runtime also provides managed remoting, which you can use to establish a communications channel between managed objects across process and host boundaries.</span></span> <span data-ttu-id="48bf4-211">托管远程处理可以适应通信组件之间的防火墙，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="48bf4-211">Managed remoting can accommodate a firewall between the communicating components, as the following illustration shows.</span></span>  
  
 <span data-ttu-id="48bf4-212">![SOAP 或 TcpChannel](../../../docs/framework/interop/media/interopremotesoap.gif "interopremotesoap")</span><span class="sxs-lookup"><span data-stu-id="48bf4-212">![SOAP or TcpChannel](../../../docs/framework/interop/media/interopremotesoap.gif "interopremotesoap")</span></span>  
<span data-ttu-id="48bf4-213">跨使用 SOAP 或 TcpChannel 类的防火墙的远程调用</span><span class="sxs-lookup"><span data-stu-id="48bf4-213">Remote calls across firewalls using SOAP or the TcpChannel class</span></span>  
  
 <span data-ttu-id="48bf4-214">某些非托管调用可以通过 SOAP 传递， 如 [服务组件](http://msdn.microsoft.com/library/f109ee24-81ad-4d99-9892-51ac6f34978c) 和 COM 之间的调用。</span><span class="sxs-lookup"><span data-stu-id="48bf4-214">Some unmanaged calls can be channeled through SOAP, such as the calls between [serviced components](http://msdn.microsoft.com/library/f109ee24-81ad-4d99-9892-51ac6f34978c) and COM.</span></span>  
  
 [<span data-ttu-id="48bf4-215">返回页首</span><span class="sxs-lookup"><span data-stu-id="48bf4-215">Back to top</span></span>](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="48bf4-216">相关主题</span><span class="sxs-lookup"><span data-stu-id="48bf4-216">Related Topics</span></span>  
  
|<span data-ttu-id="48bf4-217">标题</span><span class="sxs-lookup"><span data-stu-id="48bf4-217">Title</span></span>|<span data-ttu-id="48bf4-218">描述</span><span class="sxs-lookup"><span data-stu-id="48bf4-218">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="48bf4-219">默认封送处理行为</span><span class="sxs-lookup"><span data-stu-id="48bf4-219">Default Marshaling Behavior</span></span>](../../../docs/framework/interop/default-marshaling-behavior.md)|<span data-ttu-id="48bf4-220">描述互操作封送处理服务用于封送数据的规则。</span><span class="sxs-lookup"><span data-stu-id="48bf4-220">Describes the rules that the interop marshaling service uses to marshal data.</span></span>|  
|[<span data-ttu-id="48bf4-221">用平台调用封送数据</span><span class="sxs-lookup"><span data-stu-id="48bf4-221">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)|<span data-ttu-id="48bf4-222">描述如何声明方法参数以及如何将自变量传递给由非托管库导出的函数。</span><span class="sxs-lookup"><span data-stu-id="48bf4-222">Describes how to declare method parameters and pass arguments to functions exported by unmanaged libraries.</span></span>|  
|[<span data-ttu-id="48bf4-223">用 COM 互操作对数据进行封送处理</span><span class="sxs-lookup"><span data-stu-id="48bf4-223">Marshaling Data with COM Interop</span></span>](../../../docs/framework/interop/marshaling-data-with-com-interop.md)|<span data-ttu-id="48bf4-224">描述如何自定义 COM 包装器以更改封送行为。</span><span class="sxs-lookup"><span data-stu-id="48bf4-224">Describes how to customize COM wrappers to alter marshaling behavior.</span></span>|  
|[<span data-ttu-id="48bf4-225">如何：将托管代码 DCOM 迁移到 WCF</span><span class="sxs-lookup"><span data-stu-id="48bf4-225">How to: Migrate Managed-Code DCOM to WCF</span></span>](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)|<span data-ttu-id="48bf4-226">描述如何从 DCOM 迁移到 WCF。</span><span class="sxs-lookup"><span data-stu-id="48bf4-226">Describes how to migrate from DCOM to WCF.</span></span>|  
|[<span data-ttu-id="48bf4-227">如何：映射 HRESULT 和异常</span><span class="sxs-lookup"><span data-stu-id="48bf4-227">How to: Map HRESULTs and Exceptions</span></span>](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)|<span data-ttu-id="48bf4-228">描述如何将自定义异常映射到 HRESULT，并提供从每个 HRESULT 到其在 .NET Framework 中的相似异常类的完整映射。</span><span class="sxs-lookup"><span data-stu-id="48bf4-228">Describes how to map custom exceptions to HRESULTs and provides the complete mapping from each HRESULT to its comparable exception class in the .NET Framework.</span></span>|  
|[<span data-ttu-id="48bf4-229">使用泛型类型进行交互操作</span><span class="sxs-lookup"><span data-stu-id="48bf4-229">Interoperating Using Generic Types</span></span>](http://msdn.microsoft.com/library/26b88e03-085b-4b53-94ba-a5a9c709ce58)|<span data-ttu-id="48bf4-230">描述在使用用于 COM 互操作性的泛型类型时，哪些操作受支持。</span><span class="sxs-lookup"><span data-stu-id="48bf4-230">Describes which actions are supported when using generic types for COM interoperability.</span></span>|  
|[<span data-ttu-id="48bf4-231">与非托管代码交互操作</span><span class="sxs-lookup"><span data-stu-id="48bf4-231">Interoperating with Unmanaged Code</span></span>](../../../docs/framework/interop/index.md)|<span data-ttu-id="48bf4-232">描述由公共语言运行时提供的互操作性服务。</span><span class="sxs-lookup"><span data-stu-id="48bf4-232">Describes interoperability services provided by the common language runtime.</span></span>|  
|[<span data-ttu-id="48bf4-233">高级 COM 互操作性</span><span class="sxs-lookup"><span data-stu-id="48bf4-233">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/library/3ada36e5-2390-4d70-b490-6ad8de92f2fb)|<span data-ttu-id="48bf4-234">提供一些链接，指向关于将 COM 组件并入 .NET Framework 应用程序中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="48bf4-234">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>|  
|[<span data-ttu-id="48bf4-235">互操作的设计注意事项</span><span class="sxs-lookup"><span data-stu-id="48bf4-235">Design Considerations for Interoperation</span></span>](http://msdn.microsoft.com/library/b59637f6-fe35-40d6-ae72-901e7a707689)|<span data-ttu-id="48bf4-236">提供有关编写集成 COM 组件的提示。</span><span class="sxs-lookup"><span data-stu-id="48bf4-236">Provides tips for writing integrated COM components.</span></span>|  
  
 [<span data-ttu-id="48bf4-237">返回页首</span><span class="sxs-lookup"><span data-stu-id="48bf4-237">Back to top</span></span>](#top)  
  
<a name="reference"></a>   
## <a name="reference"></a><span data-ttu-id="48bf4-238">参考</span><span class="sxs-lookup"><span data-stu-id="48bf4-238">Reference</span></span>  
 <xref:System.Runtime.InteropServices?displayProperty=nameWithType>  
  
 [<span data-ttu-id="48bf4-239">返回页首</span><span class="sxs-lookup"><span data-stu-id="48bf4-239">Back to top</span></span>](#top)
