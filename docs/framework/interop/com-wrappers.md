---
title: "COM 包装"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wrapper classes
- COM interop, COM wrappers
- COM wrappers
- COM, wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b899ed162fa626f8c378923907f275cebf9a7db4
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="com-wrappers"></a><span data-ttu-id="bea0e-102">COM 包装</span><span class="sxs-lookup"><span data-stu-id="bea0e-102">COM Wrappers</span></span>
<span data-ttu-id="bea0e-103">COM 在以下几个重要方面与 .NET Framework 对象模型存在差别：</span><span class="sxs-lookup"><span data-stu-id="bea0e-103">COM differs from the .NET Framework object model in several important ways:</span></span>  
  
-   <span data-ttu-id="bea0e-104">COM 对象的客户端必需管理这些对象的生存期；公共语言运行时管理其环境中对象的生存期。</span><span class="sxs-lookup"><span data-stu-id="bea0e-104">Clients of COM objects must manage the lifetime of those objects; the common language runtime manages the lifetime of objects in its environment.</span></span>  
  
-   <span data-ttu-id="bea0e-105">COM 对象的客户端通过对提供服务的接口发出请求并取回接口指针来发现服务是否可用。</span><span class="sxs-lookup"><span data-stu-id="bea0e-105">Clients of COM objects discover whether a service is available by requesting an interface that provides that service and getting back an interface pointer, or not.</span></span> <span data-ttu-id="bea0e-106">.NET 对象的客户端可以使用反射来获取对象功能的说明。</span><span class="sxs-lookup"><span data-stu-id="bea0e-106">Clients of .NET objects can obtain a description of an object's functionality using reflection.</span></span>  
  
-   <span data-ttu-id="bea0e-107">NET 对象驻留在由 .NET Framework 执行环境管理的内存中。</span><span class="sxs-lookup"><span data-stu-id="bea0e-107">NET objects reside in memory managed by the .NET Framework execution environment.</span></span> <span data-ttu-id="bea0e-108">出于性能原因，执行环境可以在内存中来回移动对象，并更新所移动对象的所有引用。</span><span class="sxs-lookup"><span data-stu-id="bea0e-108">The execution environment can move objects around in memory for performance reasons and update all references to the objects it moves.</span></span> <span data-ttu-id="bea0e-109">非管理的客户端在获取指向对象的指针后，依赖于该对象以保留在相同位置。</span><span class="sxs-lookup"><span data-stu-id="bea0e-109">Unmanaged clients, having obtained a pointer to an object, rely on the object to remain at the same location.</span></span> <span data-ttu-id="bea0e-110">这些客户端没有机制来处理位置不固定的对象。</span><span class="sxs-lookup"><span data-stu-id="bea0e-110">These clients have no mechanism for dealing with an object whose location is not fixed.</span></span>  
  
 <span data-ttu-id="bea0e-111">为了克服这些差异，运行时提供了包装类，使托管和非管理的客户端认为它们在各自的环境中调用对象。</span><span class="sxs-lookup"><span data-stu-id="bea0e-111">To overcome these differences, the runtime provides wrapper classes to make both managed and unmanaged clients think they are calling objects within their respective environment.</span></span> <span data-ttu-id="bea0e-112">每当托管客户端对某个 COM 对象调用方法时，运行时就会创建一个[运行时可调用包装器](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW)。</span><span class="sxs-lookup"><span data-stu-id="bea0e-112">Whenever your managed client calls a method on a COM object, the runtime creates a [runtime callable wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW).</span></span> <span data-ttu-id="bea0e-113">除此之外，RCW 还会提取托管和非托管引用机制之间的差异。</span><span class="sxs-lookup"><span data-stu-id="bea0e-113">RCWs abstract the differences between managed and unmanaged reference mechanisms, among other things.</span></span> <span data-ttu-id="bea0e-114">该运行时还创建了一个 [COM 可调用包装器](../../../docs/framework/interop/com-callable-wrapper.md) (CCW) 来逆转此过程，使 COM 客户端能够对 .NET 对象无缝地调用方法。</span><span class="sxs-lookup"><span data-stu-id="bea0e-114">The runtime also creates a [COM callable wrapper](../../../docs/framework/interop/com-callable-wrapper.md) (CCW) to reverse the process, enabling a COM client to seamlessly call a method on a .NET object.</span></span> <span data-ttu-id="bea0e-115">如下图所示，调用代码的性质确定运行时创建的包装类。</span><span class="sxs-lookup"><span data-stu-id="bea0e-115">As the following illustration shows, the perspective of the calling code determines which wrapper class the runtime creates.</span></span>  
  
 <span data-ttu-id="bea0e-116">![COM 包装器概述](../../../docs/framework/interop/media/bidirectional.gif "双向")</span><span class="sxs-lookup"><span data-stu-id="bea0e-116">![COM wrapper overview](../../../docs/framework/interop/media/bidirectional.gif "bidirectional")</span></span>  
<span data-ttu-id="bea0e-117">COM 包装器概述</span><span class="sxs-lookup"><span data-stu-id="bea0e-117">COM wrapper overview</span></span>  
  
 <span data-ttu-id="bea0e-118">大多数情况下，运行时生成的标准 RCW 或 CCW 都可为跨 COM 和.NET Framework 之间边界的调用提供充分的封送处理。</span><span class="sxs-lookup"><span data-stu-id="bea0e-118">In most cases, the standard RCW or CCW generated by the runtime provides adequate marshaling for calls that cross the boundary between COM and the .NET Framework.</span></span> <span data-ttu-id="bea0e-119">使用自定义属性，可以选择性地调整运行时表示托管和非托管代码的方式。</span><span class="sxs-lookup"><span data-stu-id="bea0e-119">Using custom attributes, you can optionally adjust the way the runtime represents managed and unmanaged code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea0e-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="bea0e-120">See Also</span></span>  
 [<span data-ttu-id="bea0e-121">高级 COM 互操作性</span><span class="sxs-lookup"><span data-stu-id="bea0e-121">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/library/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [<span data-ttu-id="bea0e-122">运行时可调用包装器</span><span class="sxs-lookup"><span data-stu-id="bea0e-122">Runtime Callable Wrapper</span></span>](../../../docs/framework/interop/runtime-callable-wrapper.md)  
 [<span data-ttu-id="bea0e-123">COM 可调用包装器</span><span class="sxs-lookup"><span data-stu-id="bea0e-123">COM Callable Wrapper</span></span>](../../../docs/framework/interop/com-callable-wrapper.md)  
 [<span data-ttu-id="bea0e-124">自定义标准包装器</span><span class="sxs-lookup"><span data-stu-id="bea0e-124">Customizing Standard Wrappers</span></span>](http://msdn.microsoft.com/library/c40d089b-6a3c-41b5-a20d-d760c215e49d)  
 [<span data-ttu-id="bea0e-125">如何：自定义运行时可调用包装器</span><span class="sxs-lookup"><span data-stu-id="bea0e-125">How to: Customize Runtime Callable Wrappers</span></span>](http://msdn.microsoft.com/library/4a4bb3da-4d60-4517-99f2-78d46a681732)
