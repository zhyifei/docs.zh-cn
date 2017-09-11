---
title: "运行时可调用包装"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- COM interop, COM wrappers
- RCW
- COM wrappers
- runtime callable wrappers
- interoperation with unmanaged code, COM wrappers
ms.assetid: 7e542583-1e31-4e10-b523-8cf2f29cb4a4
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 607f5689e9b2221a916c80732bb54d64cd21bf4d
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="runtime-callable-wrapper"></a><span data-ttu-id="76679-102">运行时可调用包装</span><span class="sxs-lookup"><span data-stu-id="76679-102">Runtime Callable Wrapper</span></span>
<span data-ttu-id="76679-103">公共语言运行时通过名为运行时可调用包装 (RCW) 的代理公开 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="76679-103">The common language runtime exposes COM objects through a proxy called the runtime callable wrapper (RCW).</span></span> <span data-ttu-id="76679-104">尽管 RCW 似乎是 .NET 客户端的普通对象，但它的主要功能是封送处理 .NET 客户端和 COM 对象之间的调用。</span><span class="sxs-lookup"><span data-stu-id="76679-104">Although the RCW appears to be an ordinary object to .NET clients, its primary function is to marshal calls between a .NET client and a COM object.</span></span>  
  
 <span data-ttu-id="76679-105">无论 COM 对象上有多少引用数目，运行时都只为每个 COM 对象创建一个 RCW。</span><span class="sxs-lookup"><span data-stu-id="76679-105">The runtime creates exactly one RCW for each COM object, regardless of the number of references that exist on that object.</span></span> <span data-ttu-id="76679-106">运行时针对每个对象的每个进程维护一个 RCW。</span><span class="sxs-lookup"><span data-stu-id="76679-106">The runtime maintains a single RCW per process for each object.</span></span>  <span data-ttu-id="76679-107">如果在某个应用程序域或单元创建一个 RCW，然后传递一个其他应用程序域或单元的引用，则将使用第一个对象的代理。</span><span class="sxs-lookup"><span data-stu-id="76679-107">If you create an RCW in one application domain or apartment, and then pass a reference to another application domain or apartment, a proxy to the first object will be used.</span></span>  <span data-ttu-id="76679-108">如下图所示，任意数量的托管客户端都可拥有一个对公开 INew 和 INewer 接口的 COM 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="76679-108">As the following illustration shows, any number of managed clients can hold a reference to the COM objects that expose INew and INewer interfaces.</span></span>  
  
 <span data-ttu-id="76679-109">![RCW](../../../docs/framework/interop/media/rcw.gif "rcw")</span><span class="sxs-lookup"><span data-stu-id="76679-109">![RCW](../../../docs/framework/interop/media/rcw.gif "rcw")</span></span>  
<span data-ttu-id="76679-110">通过运行时可调用包装访问 COM 对象</span><span class="sxs-lookup"><span data-stu-id="76679-110">Accessing COM objects through the runtime callable wrapper</span></span>  
  
 <span data-ttu-id="76679-111">借助从类型库派生而来的元数据，运行时创建正在调用的 COM 对象及其包装。</span><span class="sxs-lookup"><span data-stu-id="76679-111">Using metadata derived from a type library, the runtime creates both the COM object being called and a wrapper for that object.</span></span> <span data-ttu-id="76679-112">每个 RCW 都在其包装的 COM 对象上维护一个接口指针的缓存，并且当不再需要 RCW 时释放 COM 对象上的引用。</span><span class="sxs-lookup"><span data-stu-id="76679-112">Each RCW maintains a cache of interface pointers on the COM object it wraps and releases its reference on the COM object when the RCW is no longer needed.</span></span> <span data-ttu-id="76679-113">运行时在 RCW 上执行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="76679-113">The runtime performs garbage collection on the RCW.</span></span>  
  
 <span data-ttu-id="76679-114">在其他活动中，RCW 代表包装的对象封送托管代码和非托管代码间的数据。</span><span class="sxs-lookup"><span data-stu-id="76679-114">Among other activities, the RCW marshals data between managed and unmanaged code, on behalf of the wrapped object.</span></span> <span data-ttu-id="76679-115">具体而言，每当在客户端和服务器之间传递数据的不同表示形式时，RCW 都向方法参数和方法返回值提供封送处理。</span><span class="sxs-lookup"><span data-stu-id="76679-115">Specifically, the RCW provides marshaling for method arguments and method return values whenever the client and server have different representations of the data passed between them.</span></span>  
  
 <span data-ttu-id="76679-116">标准包装强制执行内置的封送处理规则。</span><span class="sxs-lookup"><span data-stu-id="76679-116">The standard wrapper enforces built-in marshaling rules.</span></span> <span data-ttu-id="76679-117">例如，当 .NET 客户端将 String 类型作为参数的一部分传递到非托管对象时，包装会将字符串转换为 BSTR 类型。</span><span class="sxs-lookup"><span data-stu-id="76679-117">For example, when a .NET client passes a String type as part of an argument to an unmanaged object, the wrapper converts the string to a BSTR type.</span></span> <span data-ttu-id="76679-118">如果 COM 对象向它托管的调用方返回 BSTR，则调用方会收到 String。</span><span class="sxs-lookup"><span data-stu-id="76679-118">Should the COM object return a BSTR to its managed caller, the caller receives a String.</span></span> <span data-ttu-id="76679-119">客户端和服务器都会发送和接收所熟悉的数据。</span><span class="sxs-lookup"><span data-stu-id="76679-119">Both the client and the server send and receive data that is familiar to them.</span></span> <span data-ttu-id="76679-120">其他类型不需要转换。</span><span class="sxs-lookup"><span data-stu-id="76679-120">Other types require no conversion.</span></span> <span data-ttu-id="76679-121">例如，标准包装始终无需转换类型即可在托管代码和非托管代码间传递 4 字节整数。</span><span class="sxs-lookup"><span data-stu-id="76679-121">For instance, a standard wrapper will always pass a 4-byte integer between managed and unmanaged code without converting the type.</span></span>  
  
## <a name="marshaling-selected-interfaces"></a><span data-ttu-id="76679-122">封送处理所选接口</span><span class="sxs-lookup"><span data-stu-id="76679-122">Marshaling selected interfaces</span></span>  
 <span data-ttu-id="76679-123">[运行时可调用包装器](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) 的主要目的是隐藏托管和非托管编程模型之间的差异。</span><span class="sxs-lookup"><span data-stu-id="76679-123">The primary goal of the [runtime callable wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) is to hide the differences between the managed and unmanaged programming models.</span></span> <span data-ttu-id="76679-124">若要创建无缝转换，RCW 需使用选定的 COM 接口且不将其公开到 .NET 客户端，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="76679-124">To create a seamless transition, the RCW consumes selected COM interfaces without exposing them to the .NET client, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="76679-125">![带接口的 RCW](../../../docs/framework/interop/media/rcwwithinterfaces.gif "rcwwithinterfaces")</span><span class="sxs-lookup"><span data-stu-id="76679-125">![RCW With Interfaces](../../../docs/framework/interop/media/rcwwithinterfaces.gif "rcwwithinterfaces")</span></span>  
<span data-ttu-id="76679-126">COM 接口和运行时可调用包装</span><span class="sxs-lookup"><span data-stu-id="76679-126">COM interfaces and the runtime callable wrapper</span></span>  
  
 <span data-ttu-id="76679-127">当创建为早期绑定对象时，RCW 为特定类型。</span><span class="sxs-lookup"><span data-stu-id="76679-127">When created as an early-bound object, the RCW is a specific type.</span></span> <span data-ttu-id="76679-128">它可实现 COM 对象实现的接口，并可公开对象接口中的方法、属性和事件。</span><span class="sxs-lookup"><span data-stu-id="76679-128">It implements the interfaces that the COM object implements and exposes the methods, properties, and events from the object's interfaces.</span></span> <span data-ttu-id="76679-129">图示中，RCW 公开 INew 接口，但使用“IUnknown”和“IDispatch”接口。</span><span class="sxs-lookup"><span data-stu-id="76679-129">In the illustration, the RCW exposes the INew interface but consumes the **IUnknown** and **IDispatch** interfaces.</span></span> <span data-ttu-id="76679-130">此外，RCW 向 .NET 客户端公开 INew 接口的所有成员。</span><span class="sxs-lookup"><span data-stu-id="76679-130">Further, the RCW exposes all members of the INew interface to the .NET client.</span></span>  
  
 <span data-ttu-id="76679-131">RCW 使用下表列出的接口，这些接口由其包装的对象公开。</span><span class="sxs-lookup"><span data-stu-id="76679-131">The RCW consumes the interfaces listed in the following table, which are exposed by the object it wraps.</span></span>  
  
|<span data-ttu-id="76679-132">接口</span><span class="sxs-lookup"><span data-stu-id="76679-132">Interface</span></span>|<span data-ttu-id="76679-133">描述</span><span class="sxs-lookup"><span data-stu-id="76679-133">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76679-134">**IDispatch**</span><span class="sxs-lookup"><span data-stu-id="76679-134">**IDispatch**</span></span>|<span data-ttu-id="76679-135">用于通过反射后期绑定到 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="76679-135">For late binding to COM objects through reflection.</span></span>|  
|<span data-ttu-id="76679-136">**IErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="76679-136">**IErrorInfo**</span></span>|<span data-ttu-id="76679-137">提供以下内容的文字描述：错误、错误源、帮助文件，帮助上下文以及定义错误的接口的 GUID（.NET 类始终为 GUID_NULL）。</span><span class="sxs-lookup"><span data-stu-id="76679-137">Provides a textual description of the error, its source, a Help file, Help context, and the GUID of the interface that defined the error (always **GUID_NULL** for .NET classes).</span></span>|  
|<span data-ttu-id="76679-138">**IProvideClassInfo**</span><span class="sxs-lookup"><span data-stu-id="76679-138">**IProvideClassInfo**</span></span>|<span data-ttu-id="76679-139">如果正在包装的 COM 对象实现 IProvideClassInfo，RCW 会提取此接口中的类型信息以提供更佳的类型标识。</span><span class="sxs-lookup"><span data-stu-id="76679-139">If the COM object being wrapped implements **IProvideClassInfo**, the RCW extracts the type information from this interface to provide better type identity.</span></span>|  
|<span data-ttu-id="76679-140">**IUnknown**</span><span class="sxs-lookup"><span data-stu-id="76679-140">**IUnknown**</span></span>|<span data-ttu-id="76679-141">针对对象标识、类型强制和生存期管理：</span><span class="sxs-lookup"><span data-stu-id="76679-141">For object identity, type coercion, and lifetime management:</span></span><br /><br /> <span data-ttu-id="76679-142">-   对象标识</span><span class="sxs-lookup"><span data-stu-id="76679-142">-   Object identity</span></span><br />     <span data-ttu-id="76679-143">运行时通过比较每个对象的 IUnknown 接口的值来区分 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="76679-143">The runtime distinguishes between COM objects by comparing the value of the **IUnknown** interface for each object.</span></span><br /><span data-ttu-id="76679-144">-   类型强制</span><span class="sxs-lookup"><span data-stu-id="76679-144">-   Type coercion</span></span><br />     <span data-ttu-id="76679-145">RCW 识别由 QueryInterface 方法执行的动态类型发现。</span><span class="sxs-lookup"><span data-stu-id="76679-145">The RCW recognizes the dynamic type discovery performed by the **QueryInterface** method.</span></span><br /><span data-ttu-id="76679-146">-   生存期管理</span><span class="sxs-lookup"><span data-stu-id="76679-146">-   Lifetime management</span></span><br />     <span data-ttu-id="76679-147">借助 QueryInterface 方法，RCW 获取并保存对非托管对象的引用，直到运行时在包装器上执行会释放非托管对象的垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="76679-147">Using the **QueryInterface** method, the RCW gets and holds a reference to an unmanaged object until the runtime performs garbage collection on the wrapper, which releases the unmanaged object.</span></span>|  
  
 <span data-ttu-id="76679-148">RCW 选择性地使用下表中列出的接口，这些接口由其包装的对象公开。</span><span class="sxs-lookup"><span data-stu-id="76679-148">The RCW optionally consumes the interfaces listed in the following table, which are exposed by the object it wraps.</span></span>  
  
|<span data-ttu-id="76679-149">接口</span><span class="sxs-lookup"><span data-stu-id="76679-149">Interface</span></span>|<span data-ttu-id="76679-150">描述</span><span class="sxs-lookup"><span data-stu-id="76679-150">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76679-151">**IConnectionPoint** 和 **IConnectionPointContainer**</span><span class="sxs-lookup"><span data-stu-id="76679-151">**IConnectionPoint** and **IConnectionPointContainer**</span></span>|<span data-ttu-id="76679-152">RCW 对向基于委托的事件公开连接点事件样式的对象执行转换。</span><span class="sxs-lookup"><span data-stu-id="76679-152">The RCW converts objects that expose the connection-point event style to delegate-based events.</span></span>|  
|<span data-ttu-id="76679-153">**IDispatchEx**</span><span class="sxs-lookup"><span data-stu-id="76679-153">**IDispatchEx**</span></span>|<span data-ttu-id="76679-154">如果类实现 IDispatchEx，则 RCW 实现 IExpando。</span><span class="sxs-lookup"><span data-stu-id="76679-154">If the class implements **IDispatchEx**, the RCW implements **IExpando**.</span></span> <span data-ttu-id="76679-155">IDispatchEx 接口是 IDispatch 接口的扩展，与 IDispatch 不同，它可枚举、添加、删除和以区分大小的方式调用成员。</span><span class="sxs-lookup"><span data-stu-id="76679-155">The **IDispatchEx** interface is an extension of the **IDispatch** interface that, unlike **IDispatch**, enables enumeration, addition, deletion, and case-sensitive calling of members.</span></span>|  
|<span data-ttu-id="76679-156">**IEnumVARIANT**</span><span class="sxs-lookup"><span data-stu-id="76679-156">**IEnumVARIANT**</span></span>|<span data-ttu-id="76679-157">使支持枚举的 COM 类型可被视为集合。</span><span class="sxs-lookup"><span data-stu-id="76679-157">Enables COM types that support enumerations to be treated as collections.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="76679-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76679-158">See Also</span></span>  
 <span data-ttu-id="76679-159">[COM 包装器](../../../docs/framework/interop/com-wrappers.md) </span><span class="sxs-lookup"><span data-stu-id="76679-159">[COM Wrappers](../../../docs/framework/interop/com-wrappers.md) </span></span>  
 <span data-ttu-id="76679-160">[封送处理所选接口](http://msdn.microsoft.com/en-us/fdb97fd0-f694-4832-bf15-a4e7cf413840) </span><span class="sxs-lookup"><span data-stu-id="76679-160">[Marshaling Selected Interfaces](http://msdn.microsoft.com/en-us/fdb97fd0-f694-4832-bf15-a4e7cf413840) </span></span>  
 <span data-ttu-id="76679-161">[COM 可调用包装器](../../../docs/framework/interop/com-callable-wrapper.md) </span><span class="sxs-lookup"><span data-stu-id="76679-161">[COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md) </span></span>  
 <span data-ttu-id="76679-162">[有关从类型库转换到程序集的摘要](http://msdn.microsoft.com/en-us/bf3f90c5-4770-4ab8-895c-3ba1055cc958) </span><span class="sxs-lookup"><span data-stu-id="76679-162">[Type Library to Assembly Conversion Summary](http://msdn.microsoft.com/en-us/bf3f90c5-4770-4ab8-895c-3ba1055cc958) </span></span>  
 [<span data-ttu-id="76679-163">将类型库作为程序集导入</span><span class="sxs-lookup"><span data-stu-id="76679-163">Importing a Type Library as an Assembly</span></span>](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)

