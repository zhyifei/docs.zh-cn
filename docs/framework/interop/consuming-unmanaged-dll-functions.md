---
title: 使用非托管 DLL 函数
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- platform invoke, about platform invoke
- DLL functions, consuming unmanaged
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke
- DLL functions
ms.assetid: eca7606e-ebfb-4f47-b8d9-289903fdc045
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2b2d5a935c2608b2315633538fc93dd62595558
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340030"
---
# <a name="consuming-unmanaged-dll-functions"></a><span data-ttu-id="4265d-102">使用非托管 DLL 函数</span><span class="sxs-lookup"><span data-stu-id="4265d-102">Consuming Unmanaged DLL Functions</span></span>
<span data-ttu-id="4265d-103">平台调用是一项服务，使托管代码能够调用动态链接库 (DLL) 中实现的非托管函数，例如 Windows API 中的非托管函数。</span><span class="sxs-lookup"><span data-stu-id="4265d-103">Platform invoke is a service that enables managed code to call unmanaged functions implemented in dynamic link libraries (DLLs), such as those in the Windows API.</span></span> <span data-ttu-id="4265d-104">此服务定位并调用导出的函数，并根据需要跨交互操作边界封送其自变量（整数、字符串、数组、结构等）。</span><span class="sxs-lookup"><span data-stu-id="4265d-104">It locates and invokes an exported function and marshals its arguments (integers, strings, arrays, structures, and so on) across the interoperation boundary as needed.</span></span>  
  
 <span data-ttu-id="4265d-105">本部分介绍了与使用非托管 DLL 函数相关的任务，并提供有关平台调用的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4265d-105">This section introduces tasks associated with consuming unmanaged DLL functions and provides more information about platform invoke.</span></span> <span data-ttu-id="4265d-106">除了以下任务，还提供了一般注意事项以及包含其他信息和示例的链接。</span><span class="sxs-lookup"><span data-stu-id="4265d-106">In addition to the following tasks, there are general considerations and a link providing additional information and examples.</span></span>  
  
#### <a name="to-consume-exported-dll-functions"></a><span data-ttu-id="4265d-107">若要使用导出的 DLL 函数</span><span class="sxs-lookup"><span data-stu-id="4265d-107">To consume exported DLL functions</span></span>  
  
1. <span data-ttu-id="4265d-108">[标识 DLL 中的函数](../../../docs/framework/interop/identifying-functions-in-dlls.md)。</span><span class="sxs-lookup"><span data-stu-id="4265d-108">[Identify functions in DLLs](../../../docs/framework/interop/identifying-functions-in-dlls.md).</span></span>  
  
     <span data-ttu-id="4265d-109">至少必须指定函数名称及其内含的 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="4265d-109">Minimally, you must specify the name of the function and name of the DLL that contains it.</span></span>  
  
2. <span data-ttu-id="4265d-110">[创建用于容纳 DLL 函数的类](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="4265d-110">[Create a class to hold DLL functions](../../../docs/framework/interop/creating-a-class-to-hold-dll-functions.md).</span></span>  
  
     <span data-ttu-id="4265d-111">可使用现有的类为每个非托管函数创建单独的类，或创建包含一组相关的非托管函数的类。</span><span class="sxs-lookup"><span data-stu-id="4265d-111">You can use an existing class, create an individual class for each unmanaged function, or create one class that contains a set of related unmanaged functions.</span></span>  
  
3. <span data-ttu-id="4265d-112">[在托管代码中创建原型](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)。</span><span class="sxs-lookup"><span data-stu-id="4265d-112">[Create prototypes in managed code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).</span></span>  
  
     <span data-ttu-id="4265d-113">[Visual Basic] 使用 Declare 语句以及 Function 和 Lib 关键字。</span><span class="sxs-lookup"><span data-stu-id="4265d-113">[Visual Basic] Use the **Declare** statement with the **Function** and **Lib** keywords.</span></span> <span data-ttu-id="4265d-114">在极少数情况下，可以使用 DllImportAttribute 和 Shared Function 关键字。</span><span class="sxs-lookup"><span data-stu-id="4265d-114">In some rare cases, you can use the **DllImportAttribute** with the **Shared Function** keywords.</span></span> <span data-ttu-id="4265d-115">本节稍后会对这些情况进行说明。</span><span class="sxs-lookup"><span data-stu-id="4265d-115">These cases are explained later in this section.</span></span>  
  
     <span data-ttu-id="4265d-116">[C#] 使用 DllImportAttribute 标识 DLL 和函数。</span><span class="sxs-lookup"><span data-stu-id="4265d-116">[C#] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="4265d-117">为此方法标记 static 和 extern 修饰符。</span><span class="sxs-lookup"><span data-stu-id="4265d-117">Mark the method with the **static** and **extern** modifiers.</span></span>  
  
     <span data-ttu-id="4265d-118">[C++] 使用 DllImportAttribute 标识 DLL 和函数。</span><span class="sxs-lookup"><span data-stu-id="4265d-118">[C++] Use the **DllImportAttribute** to identify the DLL and function.</span></span> <span data-ttu-id="4265d-119">用 extern "C" 标记此包装方法或函数。</span><span class="sxs-lookup"><span data-stu-id="4265d-119">Mark the wrapper method or function with **extern "C"**.</span></span>  
  
4. <span data-ttu-id="4265d-120">[调用 DLL 函数](../../../docs/framework/interop/calling-a-dll-function.md)。</span><span class="sxs-lookup"><span data-stu-id="4265d-120">[Call a DLL function](../../../docs/framework/interop/calling-a-dll-function.md).</span></span>  
  
     <span data-ttu-id="4265d-121">与调用任何其他托管方法一样，在托管类上调用方法。</span><span class="sxs-lookup"><span data-stu-id="4265d-121">Call the method on your managed class as you would any other managed method.</span></span> <span data-ttu-id="4265d-122">[传递结构](../../../docs/framework/interop/passing-structures.md)和[实现回调函数](../../../docs/framework/interop/callback-functions.md)属于特殊情况。</span><span class="sxs-lookup"><span data-stu-id="4265d-122">[Passing structures](../../../docs/framework/interop/passing-structures.md) and [implementing callback functions](../../../docs/framework/interop/callback-functions.md) are special cases.</span></span>  
  
 <span data-ttu-id="4265d-123">有关演示如何构造要用于平台调用、基于 .NET 的声明的示例，请参阅[用平台调用封送数据](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)。</span><span class="sxs-lookup"><span data-stu-id="4265d-123">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="a-closer-look-at-platform-invoke"></a><span data-ttu-id="4265d-124">平台调用详解</span><span class="sxs-lookup"><span data-stu-id="4265d-124">A closer look at platform invoke</span></span>  
 <span data-ttu-id="4265d-125">平台调用依赖元数据定位导出的函数并在运行时封送处理它的自变量。</span><span class="sxs-lookup"><span data-stu-id="4265d-125">Platform invoke relies on metadata to locate exported functions and marshal their arguments at run time.</span></span> <span data-ttu-id="4265d-126">下图显示了此过程。</span><span class="sxs-lookup"><span data-stu-id="4265d-126">The following illustration shows this process.</span></span>  
  
 ![显示平台调用的图表。](./media/consuming-unmanaged-dll-functions/platform-invoke-call.gif)  
  
 <span data-ttu-id="4265d-128">平台调用调用非托管函数时，将执行以下操作序列：</span><span class="sxs-lookup"><span data-stu-id="4265d-128">When platform invoke calls an unmanaged function, it performs the following sequence of actions:</span></span>  
  
1. <span data-ttu-id="4265d-129">定位包含函数的 DLL。</span><span class="sxs-lookup"><span data-stu-id="4265d-129">Locates the DLL containing the function.</span></span>  
  
2. <span data-ttu-id="4265d-130">将 DLL 加载到内存中。</span><span class="sxs-lookup"><span data-stu-id="4265d-130">Loads the DLL into memory.</span></span>  
  
3. <span data-ttu-id="4265d-131">在内存中定位函数的地址并将其参数推送到堆栈上，从而根据需要封送数据。</span><span class="sxs-lookup"><span data-stu-id="4265d-131">Locates the address of the function in memory and pushes its arguments onto the stack, marshaling data as required.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4265d-132">定位和加载 DLL，并定位仅在首次调用函数时内存中出现的函数地址。</span><span class="sxs-lookup"><span data-stu-id="4265d-132">Locating and loading the DLL, and locating the address of the function in memory occur only on the first call to the function.</span></span>  
  
4. <span data-ttu-id="4265d-133">将控件传输到非托管函数。</span><span class="sxs-lookup"><span data-stu-id="4265d-133">Transfers control to the unmanaged function.</span></span>  
  
 <span data-ttu-id="4265d-134">平台调用将向托管调用方引发非托管函数生成的异常。</span><span class="sxs-lookup"><span data-stu-id="4265d-134">Platform invoke throws exceptions generated by the unmanaged function to the managed caller.</span></span>

## <a name="see-also"></a><span data-ttu-id="4265d-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="4265d-135">See also</span></span>

- [<span data-ttu-id="4265d-136">与非托管代码交互操作</span><span class="sxs-lookup"><span data-stu-id="4265d-136">Interoperating with Unmanaged Code</span></span>](../../../docs/framework/interop/index.md)
- [<span data-ttu-id="4265d-137">平台调用示例</span><span class="sxs-lookup"><span data-stu-id="4265d-137">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="4265d-138">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="4265d-138">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
