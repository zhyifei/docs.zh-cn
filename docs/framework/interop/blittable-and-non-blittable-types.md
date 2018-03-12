---
title: "可直接复制到本机结构中的类型和非直接复制到本机结构中的类型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interop marshaling, blittable types
- blittable types, interop marshaling
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c61fe689a2a708b10fdf21e3638b1fc6ff117d25
ms.sourcegitcommit: d95a91d685565f4d95c8773b558752864a6a3d7e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2018
---
# <a name="blittable-and-non-blittable-types"></a><span data-ttu-id="1acd2-102">可直接复制到本机结构中的类型和非直接复制到本机结构中的类型</span><span class="sxs-lookup"><span data-stu-id="1acd2-102">Blittable and Non-Blittable Types</span></span>
<span data-ttu-id="1acd2-103">大多数数据类型在托管和非托管内存中具有共同的表示形式，而且不需要互操作封送处理程序进行特殊处理。</span><span class="sxs-lookup"><span data-stu-id="1acd2-103">Most data types have a common representation in both managed and unmanaged memory and do not require special handling by the interop marshaler.</span></span> <span data-ttu-id="1acd2-104">这些类型称为 blittable 类型，因为它们在托管和非托管代码之间传递时不需要进行转换。</span><span class="sxs-lookup"><span data-stu-id="1acd2-104">These types are called *blittable types* because they do not require conversion when they are passed between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="1acd2-105">从平台调用返回的结构必须是 blittable 类型。</span><span class="sxs-lookup"><span data-stu-id="1acd2-105">Structures that are returned from platform invoke calls must be blittable types.</span></span> <span data-ttu-id="1acd2-106">平台调用不支持返回类型为 non-blittable 结构。</span><span class="sxs-lookup"><span data-stu-id="1acd2-106">Platform invoke does not support non-blittable structures as return types.</span></span>  
  
 <span data-ttu-id="1acd2-107">以下 <xref:System> 命名空间中的类型即是 blittable 类型：</span><span class="sxs-lookup"><span data-stu-id="1acd2-107">The following types from the <xref:System> namespace are blittable types:</span></span>  
  
-   <xref:System.Byte?displayProperty=nameWithType>  
  
-   <xref:System.SByte?displayProperty=nameWithType>  
  
-   <xref:System.Int16?displayProperty=nameWithType>  
  
-   <xref:System.UInt16?displayProperty=nameWithType>  
  
-   <xref:System.Int32?displayProperty=nameWithType>  
  
-   <xref:System.UInt32?displayProperty=nameWithType>  
  
-   <xref:System.Int64?displayProperty=nameWithType>  
  
-   <xref:System.UInt64?displayProperty=nameWithType>  
  
-   <xref:System.IntPtr?displayProperty=nameWithType>  
  
-   <xref:System.UIntPtr?displayProperty=nameWithType>  
  
-   <xref:System.Single?displayProperty=nameWithType>  
  
-   <xref:System.Double?displayProperty=nameWithType>  
  
 <span data-ttu-id="1acd2-108">下面的复杂类型也是 blittable 类型：</span><span class="sxs-lookup"><span data-stu-id="1acd2-108">The following complex types are also blittable types:</span></span>  
  
-   <span data-ttu-id="1acd2-109">所有 blittable 类型的一维数组，如整数数组。</span><span class="sxs-lookup"><span data-stu-id="1acd2-109">One-dimensional arrays of blittable types, such as an array of integers.</span></span> <span data-ttu-id="1acd2-110">但是，包含 blittable 类型变量数组的类型本身不是 blittable 类型。</span><span class="sxs-lookup"><span data-stu-id="1acd2-110">However, a type that contains a variable array of blittable types is not itself blittable.</span></span>  
  
-   <span data-ttu-id="1acd2-111">所有只包含 blittable 类型（和作为格式化类型进行封送的类）的格式化的值类型。</span><span class="sxs-lookup"><span data-stu-id="1acd2-111">Formatted value types that contain only blittable types (and classes if they are marshaled as formatted types).</span></span> <span data-ttu-id="1acd2-112">有关格式化的值类型的详细信息，请参阅[值类型的默认封送处理](https://msdn.microsoft.com/library/4d9a876c-e05a-40ba-bd85-bd22877f984a(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="1acd2-112">For more information about formatted value types, see [Default Marshaling for Value Types](https://msdn.microsoft.com/library/4d9a876c-e05a-40ba-bd85-bd22877f984a(v=vs.100)).</span></span>  
  
 <span data-ttu-id="1acd2-113">对象引用不是 blittable 类型。</span><span class="sxs-lookup"><span data-stu-id="1acd2-113">Object references are not blittable.</span></span> <span data-ttu-id="1acd2-114">这包括本身是 blittable 的对象的引用数组。</span><span class="sxs-lookup"><span data-stu-id="1acd2-114">This includes an array of references to objects that are blittable by themselves.</span></span> <span data-ttu-id="1acd2-115">例如，可以定义一个属于 blittable 类型的结构，但不能定义包含这些结构的引用数组的 blittable 类型。</span><span class="sxs-lookup"><span data-stu-id="1acd2-115">For example, you can define a structure that is blittable, but you cannot define a blittable type that contains an array of references to those structures.</span></span>  
  
 <span data-ttu-id="1acd2-116">作为一种优化方式，所有 blittable 类型数组和只包含 blittable 成员的类都是[固定的](../../../docs/framework/interop/copying-and-pinning.md)，因此无需在封送处理期间进行复制。</span><span class="sxs-lookup"><span data-stu-id="1acd2-116">As an optimization, arrays of blittable types and classes that contain only blittable members are [pinned](../../../docs/framework/interop/copying-and-pinning.md) instead of copied during marshaling.</span></span> <span data-ttu-id="1acd2-117">若调用方和被调用方位于同一单元中，这些类型会显示为作为 In/Out 参数被封送。</span><span class="sxs-lookup"><span data-stu-id="1acd2-117">These types can appear to be marshaled as In/Out parameters when the caller and callee are in the same apartment.</span></span> <span data-ttu-id="1acd2-118">但是，这些类型实际上是作为 In 形参进行封送的，而且，如果要将实参作为 In/Out 形参进行封送，则必须应用 <xref:System.Runtime.InteropServices.InAttribute> 和 <xref:System.Runtime.InteropServices.OutAttribute> 属性。</span><span class="sxs-lookup"><span data-stu-id="1acd2-118">However, these types are actually marshaled as In parameters, and you must apply the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes if you want to marshal the argument as an In/Out parameter.</span></span>  
  
 <span data-ttu-id="1acd2-119">在非托管环境中，某些托管数据类型要求具有不同的表示形式。</span><span class="sxs-lookup"><span data-stu-id="1acd2-119">Some managed data types require a different representation in an unmanaged environment.</span></span> <span data-ttu-id="1acd2-120">必须将这些 non-blittable 数据类型转换为可以封送的形式。</span><span class="sxs-lookup"><span data-stu-id="1acd2-120">These non-blittable data types must be converted into a form that can be marshaled.</span></span> <span data-ttu-id="1acd2-121">例如，托管字符串就是 non-blittable 类型，因为这些字符串必须转换为字符串对象后才能进行封送。</span><span class="sxs-lookup"><span data-stu-id="1acd2-121">For example, managed strings are non-blittable types because they must be converted into string objects before they can be marshaled.</span></span>  
  
 <span data-ttu-id="1acd2-122">下表列出了 <xref:System> 命名空间中的 non-blittable 类型。</span><span class="sxs-lookup"><span data-stu-id="1acd2-122">The following table lists non-blittable types from the <xref:System> namespace.</span></span> <span data-ttu-id="1acd2-123">[委托](https://msdn.microsoft.com/library/d176ee76-f982-494b-b03d-92e4118896e2(v=vs.100))是引用静态方法或类实例的数据结构，也是 non-blittable 类型。</span><span class="sxs-lookup"><span data-stu-id="1acd2-123">[Delegates](https://msdn.microsoft.com/library/d176ee76-f982-494b-b03d-92e4118896e2(v=vs.100)), which are data structures that refer to a static method or to a class instance, are also non-blittable.</span></span>  
  
|<span data-ttu-id="1acd2-124">Non-blittable 类型</span><span class="sxs-lookup"><span data-stu-id="1acd2-124">Non-blittable type</span></span>|<span data-ttu-id="1acd2-125">描述</span><span class="sxs-lookup"><span data-stu-id="1acd2-125">Description</span></span>|  
|-------------------------|-----------------|  
|[<span data-ttu-id="1acd2-126">System.Array</span><span class="sxs-lookup"><span data-stu-id="1acd2-126">System.Array</span></span>](../../../docs/framework/interop/default-marshaling-for-arrays.md)|<span data-ttu-id="1acd2-127">转换为 C 样式数组或 `SAFEARRAY`。</span><span class="sxs-lookup"><span data-stu-id="1acd2-127">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
|<span data-ttu-id="1acd2-128">[System.Boolean](https://msdn.microsoft.com/library/d4c00537-70f7-4ca6-8197-bfc1ec037ff9(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1acd2-128">[System.Boolean](https://msdn.microsoft.com/library/d4c00537-70f7-4ca6-8197-bfc1ec037ff9(v=vs.100))</span></span>|<span data-ttu-id="1acd2-129">转换为 1、2 或 4 字节的值，`true` 表示 1 或 -1。</span><span class="sxs-lookup"><span data-stu-id="1acd2-129">Converts to a 1, 2, or 4-byte value with `true` as 1 or -1.</span></span>|  
|<span data-ttu-id="1acd2-130">[System.Char](https://msdn.microsoft.com/library/cecc87c1-075e-4cde-aa56-33d189f66feb(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1acd2-130">[System.Char](https://msdn.microsoft.com/library/cecc87c1-075e-4cde-aa56-33d189f66feb(v=vs.100))</span></span>|<span data-ttu-id="1acd2-131">转换为 Unicode 或 ANSI 字符。</span><span class="sxs-lookup"><span data-stu-id="1acd2-131">Converts to a Unicode or ANSI character.</span></span>|  
|<span data-ttu-id="1acd2-132">[System.Class](https://msdn.microsoft.com/library/fe334af5-0123-43d8-be84-26f6f023ddb6(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1acd2-132">[System.Class](https://msdn.microsoft.com/library/fe334af5-0123-43d8-be84-26f6f023ddb6(v=vs.100))</span></span>|<span data-ttu-id="1acd2-133">转换为类接口。</span><span class="sxs-lookup"><span data-stu-id="1acd2-133">Converts to a class interface.</span></span>|  
|[<span data-ttu-id="1acd2-134">System.Object</span><span class="sxs-lookup"><span data-stu-id="1acd2-134">System.Object</span></span>](../../../docs/framework/interop/default-marshaling-for-objects.md)|<span data-ttu-id="1acd2-135">转换为变量或接口。</span><span class="sxs-lookup"><span data-stu-id="1acd2-135">Converts to a variant or an interface.</span></span>|  
|[<span data-ttu-id="1acd2-136">System.Mdarray</span><span class="sxs-lookup"><span data-stu-id="1acd2-136">System.Mdarray</span></span>](../../../docs/framework/interop/default-marshaling-for-arrays.md)|<span data-ttu-id="1acd2-137">转换为 C 样式数组或 `SAFEARRAY`。</span><span class="sxs-lookup"><span data-stu-id="1acd2-137">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
|[<span data-ttu-id="1acd2-138">System.String</span><span class="sxs-lookup"><span data-stu-id="1acd2-138">System.String</span></span>](../../../docs/framework/interop/default-marshaling-for-strings.md)|<span data-ttu-id="1acd2-139">转换为空引用中的终止字符串或转换为 BSTR。</span><span class="sxs-lookup"><span data-stu-id="1acd2-139">Converts to a string terminating in a null reference or to a BSTR.</span></span>|  
|<span data-ttu-id="1acd2-140">[System.Valuetype](https://msdn.microsoft.com/library/4d9a876c-e05a-40ba-bd85-bd22877f984a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1acd2-140">[System.Valuetype](https://msdn.microsoft.com/library/4d9a876c-e05a-40ba-bd85-bd22877f984a(v=vs.100))</span></span>|<span data-ttu-id="1acd2-141">转换为具有固定内存布局的结构。</span><span class="sxs-lookup"><span data-stu-id="1acd2-141">Converts to a structure with a fixed memory layout.</span></span>|  
|[<span data-ttu-id="1acd2-142">System.Szarray</span><span class="sxs-lookup"><span data-stu-id="1acd2-142">System.Szarray</span></span>](../../../docs/framework/interop/default-marshaling-for-arrays.md)|<span data-ttu-id="1acd2-143">转换为 C 样式数组或 `SAFEARRAY`。</span><span class="sxs-lookup"><span data-stu-id="1acd2-143">Converts to a C-style array or a `SAFEARRAY`.</span></span>|  
  
 <span data-ttu-id="1acd2-144">类和对象类型仅受 COM 互操作支持。</span><span class="sxs-lookup"><span data-stu-id="1acd2-144">Class and object types are supported only by COM interop.</span></span> <span data-ttu-id="1acd2-145">有关 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]、C# 和 C++ 中的相应类型的信息，请参阅[类库概述](../../../docs/standard/class-library-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1acd2-145">For corresponding types in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C#, and C++, see the [Class Library Overview](../../../docs/standard/class-library-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1acd2-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="1acd2-146">See Also</span></span>  
 [<span data-ttu-id="1acd2-147">默认封送处理行为</span><span class="sxs-lookup"><span data-stu-id="1acd2-147">Default Marshaling Behavior</span></span>](../../../docs/framework/interop/default-marshaling-behavior.md)
