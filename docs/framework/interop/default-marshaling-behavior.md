---
title: "默认封送处理行为"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, default
- interoperation with unmanaged code, marshaling
- marshaling behavior
ms.assetid: c0a9bcdf-3df8-4db3-b1b6-abbdb2af809a
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e66caf800fd49b4822ee22326b8a5cf712d99bb
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="default-marshaling-behavior"></a><span data-ttu-id="6aae1-102">默认封送处理行为</span><span class="sxs-lookup"><span data-stu-id="6aae1-102">Default Marshaling Behavior</span></span>
<span data-ttu-id="6aae1-103">互操作封送处理根据规则进行操作，该规则指定与方法参数相关联的数据在托管和非托管内存之间传递时的行为方式。</span><span class="sxs-lookup"><span data-stu-id="6aae1-103">Interop marshaling operates on rules that dictate how data associated with method parameters behaves as it passes between managed and unmanaged memory.</span></span> <span data-ttu-id="6aae1-104">这些内置规则控制诸如此类的封送处理活动：数据类型转换、被调用方是否可以更改传递给它的数据并将这些更改返回给调用方以及在何种情况下封送拆收器提供性能优化。</span><span class="sxs-lookup"><span data-stu-id="6aae1-104">These built-in rules control such marshaling activities as data type transformations, whether a callee can change data passed to it and return those changes to the caller, and under which circumstances the marshaler provides performance optimizations.</span></span>  
  
 <span data-ttu-id="6aae1-105">本部分确定互操作封送处理服务的默认行为特征。</span><span class="sxs-lookup"><span data-stu-id="6aae1-105">This section identifies the default behavioral characteristics of the interop marshaling service.</span></span> <span data-ttu-id="6aae1-106">它提供有关封送处理数组、布尔值类型、char 类型、委托、类、对象、字符串和结构的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6aae1-106">It presents detailed information on marshaling arrays, Boolean types, char types, delegates, classes, objects, strings, and structures.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6aae1-107">不支持泛型类型的封送处理。</span><span class="sxs-lookup"><span data-stu-id="6aae1-107">Marshaling of generic types is not supported.</span></span> <span data-ttu-id="6aae1-108">有关详细信息，请参阅[使用泛型类型进行交互操作](http://msdn.microsoft.com/library/26b88e03-085b-4b53-94ba-a5a9c709ce58)。</span><span class="sxs-lookup"><span data-stu-id="6aae1-108">For more information see, [Interoperating Using Generic Types](http://msdn.microsoft.com/library/26b88e03-085b-4b53-94ba-a5a9c709ce58).</span></span>  
  
## <a name="memory-management-with-the-interop-marshaler"></a><span data-ttu-id="6aae1-109">使用互操作封送拆收器进行内存管理</span><span class="sxs-lookup"><span data-stu-id="6aae1-109">Memory management with the interop marshaler</span></span>  
 <span data-ttu-id="6aae1-110">互操作封送拆收器始终尝试释放由非托管代码分配的内存。</span><span class="sxs-lookup"><span data-stu-id="6aae1-110">The interop marshaler always attempts to free memory allocated by unmanaged code.</span></span> <span data-ttu-id="6aae1-111">此行为符合 COM 内存管理规则，但不同于用于管理本机 C++ 的规则。</span><span class="sxs-lookup"><span data-stu-id="6aae1-111">This behavior complies with COM memory management rules, but differs from the rules that govern native C++.</span></span>  
  
 <span data-ttu-id="6aae1-112">使用为指针自动释放内存的平台调用时，如果你预期有本机 C++ 行为（无内存释放），则可能产生混淆。</span><span class="sxs-lookup"><span data-stu-id="6aae1-112">Confusion can arise if you anticipate native C++ behavior (no memory freeing) when using platform invoke, which automatically frees memory for pointers.</span></span> <span data-ttu-id="6aae1-113">例如，从 C++ DLL 调用以下非托管方法不会自动释放任何内存。</span><span class="sxs-lookup"><span data-stu-id="6aae1-113">For example, calling the following unmanaged method from a C++ DLL does not automatically free any memory.</span></span>  
  
### <a name="unmanaged-signature"></a><span data-ttu-id="6aae1-114">非托管的签名</span><span class="sxs-lookup"><span data-stu-id="6aae1-114">Unmanaged signature</span></span>  
  
```  
BSTR MethodOne (BSTR b) {  
     return b;  
}  
```  
  
 <span data-ttu-id="6aae1-115">但是，如果将方法定义为平台调用原型，将每个 BSTR 类型替换为 <xref:System.String> 类型并调用 `MethodOne`，则公共语言运行时会尝试释放 `b` 两次。</span><span class="sxs-lookup"><span data-stu-id="6aae1-115">However, if you define the method as a platform invoke prototype, replace each **BSTR** type with a <xref:System.String> type, and call `MethodOne`, the common language runtime attempts to free `b` twice.</span></span> <span data-ttu-id="6aae1-116">可使用 <xref:System.IntPtr> 类型而不是字符串类型来更改封送处理行为。</span><span class="sxs-lookup"><span data-stu-id="6aae1-116">You can change the marshaling behavior by using <xref:System.IntPtr> types rather than **String** types.</span></span>  
  
 <span data-ttu-id="6aae1-117">运行时始终使用 CoTaskMemFree 方法来释放内存。</span><span class="sxs-lookup"><span data-stu-id="6aae1-117">The runtime always uses the **CoTaskMemFree** method to free memory.</span></span> <span data-ttu-id="6aae1-118">如果正在使用的内存未通过 **CoTaskMemAlloc** 方法分配，则必须使用 **IntPtr** 并通过适当的方法手动释放内存。</span><span class="sxs-lookup"><span data-stu-id="6aae1-118">If the memory you are working with was not allocated with the **CoTaskMemAlloc** method, you must use an **IntPtr** and free the memory manually using the appropriate method.</span></span> <span data-ttu-id="6aae1-119">同样，可在永不应释放内存的情况下避免自动释放内存，例如，从 kernel32.dll（它将指针返回内核内存）使用 GetCommandLine 函数时。</span><span class="sxs-lookup"><span data-stu-id="6aae1-119">Similarly, you can avoid automatic memory freeing in situations where memory should never be freed, such as when using the **GetCommandLine** function from Kernel32.dll, which returns a pointer to kernel memory.</span></span> <span data-ttu-id="6aae1-120">有关手动释放内存的详细信息，请参阅[缓冲区示例](http://msdn.microsoft.com/library/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5)。</span><span class="sxs-lookup"><span data-stu-id="6aae1-120">For details on manually freeing memory, see the [Buffers Sample](http://msdn.microsoft.com/library/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5).</span></span>  
  
## <a name="default-marshaling-for-classes"></a><span data-ttu-id="6aae1-121">类的默认封送处理</span><span class="sxs-lookup"><span data-stu-id="6aae1-121">Default marshaling for classes</span></span>  
 <span data-ttu-id="6aae1-122">类仅能由 COM 互操作封送，并总是作为接口封送。</span><span class="sxs-lookup"><span data-stu-id="6aae1-122">Classes can be marshaled only by COM interop and are always marshaled as interfaces.</span></span> <span data-ttu-id="6aae1-123">在某些情况下用来将该类封送的接口称为类接口。</span><span class="sxs-lookup"><span data-stu-id="6aae1-123">In some cases the interface used to marshal the class is known as the class interface.</span></span> <span data-ttu-id="6aae1-124">有关使用所选接口重写类接口的信息，请参阅[类接口简介](http://msdn.microsoft.com/library/733c0dd2-12e5-46e6-8de1-39d5b25df024)。</span><span class="sxs-lookup"><span data-stu-id="6aae1-124">For information about overriding the class interface with an interface of your choice, see [Introducing the Class Interface](http://msdn.microsoft.com/library/733c0dd2-12e5-46e6-8de1-39d5b25df024).</span></span>  
  
### <a name="passing-classes-to-com"></a><span data-ttu-id="6aae1-125">向 COM 传递类</span><span class="sxs-lookup"><span data-stu-id="6aae1-125">Passing Classes to COM</span></span>  
 <span data-ttu-id="6aae1-126">当托管类传递给 COM 时，互操作封送拆收器自动使用 COM 代理包装类，并将由代理所生成的类接口传递到 COM 方法调用。</span><span class="sxs-lookup"><span data-stu-id="6aae1-126">When a managed class is passed to COM, the interop marshaler automatically wraps the class with a COM proxy and passes the class interface produced by the proxy to the COM method call.</span></span> <span data-ttu-id="6aae1-127">然后，代理委托对类接口的所有调用返回托管对象。</span><span class="sxs-lookup"><span data-stu-id="6aae1-127">The proxy then delegates all calls on the class interface back to the managed object.</span></span> <span data-ttu-id="6aae1-128">代理还公开其他不由类显式实现的接口。</span><span class="sxs-lookup"><span data-stu-id="6aae1-128">The proxy also exposes other interfaces that are not explicitly implemented by the class.</span></span> <span data-ttu-id="6aae1-129">代理代表类自动实现接口，如 IUnknown 和 IDispatch。</span><span class="sxs-lookup"><span data-stu-id="6aae1-129">The proxy automatically implements interfaces such as **IUnknown** and **IDispatch** on behalf of the class.</span></span>  
  
### <a name="passing-classes-to-net-code"></a><span data-ttu-id="6aae1-130">向 .NET 代码传递类</span><span class="sxs-lookup"><span data-stu-id="6aae1-130">Passing Classes to .NET Code</span></span>  
 <span data-ttu-id="6aae1-131">组件类通常不用作 COM 中的方法参数。</span><span class="sxs-lookup"><span data-stu-id="6aae1-131">Coclasses are not typically used as method arguments in COM.</span></span> <span data-ttu-id="6aae1-132">而是通常以默认界接口代替组件类进行传递。</span><span class="sxs-lookup"><span data-stu-id="6aae1-132">Instead, a default interface is usually passed in place of the coclass.</span></span>  
  
 <span data-ttu-id="6aae1-133">当接口传递到托管代码中时，互操作封送拆收器负责用适当的包装来包装接口，并将该包装传递给托管方法。</span><span class="sxs-lookup"><span data-stu-id="6aae1-133">When an interface is passed into managed code, the interop marshaler is responsible for wrapping the interface with the proper wrapper and passing the wrapper to the managed method.</span></span> <span data-ttu-id="6aae1-134">确定要使用的包装可能会很困难。</span><span class="sxs-lookup"><span data-stu-id="6aae1-134">Determining which wrapper to use can be difficult.</span></span> <span data-ttu-id="6aae1-135">COM 对象的每个实例都具有一个唯一的包装，无论该对象实现多少个接口。</span><span class="sxs-lookup"><span data-stu-id="6aae1-135">Every instance of a COM object has a single, unique wrapper, no matter how many interfaces the object implements.</span></span> <span data-ttu-id="6aae1-136">例如，实现五个不同接口的单个 COM 对象只有一个包装。</span><span class="sxs-lookup"><span data-stu-id="6aae1-136">For example, a single COM object that implements five distinct interfaces has only one wrapper.</span></span> <span data-ttu-id="6aae1-137">同一个包装公开所有五个接口。</span><span class="sxs-lookup"><span data-stu-id="6aae1-137">The same wrapper exposes all five interfaces.</span></span> <span data-ttu-id="6aae1-138">如果创建了两个 COM 对象的实例，则创建两个包装的实例。</span><span class="sxs-lookup"><span data-stu-id="6aae1-138">If two instances of the COM object are created, then two instances of the wrapper are created.</span></span>  
  
 <span data-ttu-id="6aae1-139">对于在生存期内保持相同类型的包装，在由对象公开的接口第一次通过封送拆收器时，互操作封送拆收器必须识别正确的包装。</span><span class="sxs-lookup"><span data-stu-id="6aae1-139">For the wrapper to maintain the same type throughout its lifetime, the interop marshaler must identify the correct wrapper the first time an interface exposed by the object is passed through the marshaler.</span></span> <span data-ttu-id="6aae1-140">封送拆收器通过查看该对象实现的一个接口来识别对象。</span><span class="sxs-lookup"><span data-stu-id="6aae1-140">The marshaler identifies the object by looking at one of the interfaces the object implements.</span></span>  
  
 <span data-ttu-id="6aae1-141">例如，封送拆收器确定应使用类包装来包装已传递到托管代码的接口。</span><span class="sxs-lookup"><span data-stu-id="6aae1-141">For example, the marshaler determines that the class wrapper should be used to wrap the interface that was passed into managed code.</span></span> <span data-ttu-id="6aae1-142">当接口第一次通过封送拆收器时，封送拆收器检查该接口是否来自已知的对象。</span><span class="sxs-lookup"><span data-stu-id="6aae1-142">When the interface is first passed through the marshaler, the marshaler checks whether the interface is coming from a known object.</span></span> <span data-ttu-id="6aae1-143">在两种情况中会发生此检查行为：</span><span class="sxs-lookup"><span data-stu-id="6aae1-143">This check occurs in two situations:</span></span>  
  
-   <span data-ttu-id="6aae1-144">一个接口正在由另一个传递到 COM 其他位置的托管对象实现。</span><span class="sxs-lookup"><span data-stu-id="6aae1-144">An interface is being implemented by another managed object that was passed to COM elsewhere.</span></span> <span data-ttu-id="6aae1-145">封送拆收器可轻易识别由托管对象公开的接口，并能够将接口与提供实现的托管对象相匹配。</span><span class="sxs-lookup"><span data-stu-id="6aae1-145">The marshaler can readily identify interfaces exposed by managed objects and is able to match the interface with the managed object that provides the implementation.</span></span> <span data-ttu-id="6aae1-146">接着托管对象被传递给该方法且不需要包装。</span><span class="sxs-lookup"><span data-stu-id="6aae1-146">The managed object is then passed to the method and no wrapper is needed.</span></span>  
  
-   <span data-ttu-id="6aae1-147">已包装的对象将实现该接口。</span><span class="sxs-lookup"><span data-stu-id="6aae1-147">An object that has already been wrapped is implementing the interface.</span></span> <span data-ttu-id="6aae1-148">要确定是否就是这种情况，封送拆收器向该对象查询其 IUnknown 接口，并将返回的接口与其他已包装对象的接口进行比较。</span><span class="sxs-lookup"><span data-stu-id="6aae1-148">To determine whether this is the case, the marshaler queries the object for its **IUnknown** interface and compares the returned interface to the interfaces of other objects that are already wrapped.</span></span> <span data-ttu-id="6aae1-149">如果该接口与另一包装的接口相同，则这些对象具有相同的标识，并且现有的包装会被传递给该方法。</span><span class="sxs-lookup"><span data-stu-id="6aae1-149">If the interface is the same as that of another wrapper, the objects have the same identity and the existing wrapper is passed to the method.</span></span>  
  
 <span data-ttu-id="6aae1-150">如果接口不是来自已知对象，则封送拆收器执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6aae1-150">If an interface is not from a known object, the marshaler does the following:</span></span>  
  
1.  <span data-ttu-id="6aae1-151">封送拆收器向对象查询 IProvideClassInfo2 接口。</span><span class="sxs-lookup"><span data-stu-id="6aae1-151">The marshaler queries the object for the **IProvideClassInfo2** interface.</span></span> <span data-ttu-id="6aae1-152">封送拆收器使用从 IProvideClassInfo2.GetGUID 返回的 CLSID（如果已提供）来识别提供接口的组件类。</span><span class="sxs-lookup"><span data-stu-id="6aae1-152">If provided, the marshaler uses the CLSID returned from **IProvideClassInfo2.GetGUID** to identify the coclass providing the interface.</span></span> <span data-ttu-id="6aae1-153">如果以前注册过程序集，通过 CLSID，封送拆收器可以从注册表定位包装。</span><span class="sxs-lookup"><span data-stu-id="6aae1-153">With the CLSID, the marshaler can locate the wrapper from the registry if the assembly has previously been registered.</span></span>  
  
2.  <span data-ttu-id="6aae1-154">封送拆收器向接口查询 IProvideClassInfo 接口。</span><span class="sxs-lookup"><span data-stu-id="6aae1-154">The marshaler queries the interface for the **IProvideClassInfo** interface.</span></span> <span data-ttu-id="6aae1-155">封送拆收器使用从 IProvideClassInfo.GetClassinfo 返回 的 ITypeInfo（如果已提供）来确定公开该接口的类的 CLSID。</span><span class="sxs-lookup"><span data-stu-id="6aae1-155">If provided, the marshaler uses the **ITypeInfo** returned from **IProvideClassInfo.GetClassinfo** to determine the CLSID of the class exposing the interface.</span></span> <span data-ttu-id="6aae1-156">封送拆收器可以使用 CLSID 定位包装的元数据。</span><span class="sxs-lookup"><span data-stu-id="6aae1-156">The marshaler can use the CLSID to locate the metadata for the wrapper.</span></span>  
  
3.  <span data-ttu-id="6aae1-157">如果封送拆收器仍不能识别类，则使用名为 System.__ComObject 的泛型包装类包装接口。</span><span class="sxs-lookup"><span data-stu-id="6aae1-157">If the marshaler still cannot identify the class, it wraps the interface with a generic wrapper class called **System.__ComObject**.</span></span>  
  
## <a name="default-marshaling-for-delegates"></a><span data-ttu-id="6aae1-158">委托的默认封送处理</span><span class="sxs-lookup"><span data-stu-id="6aae1-158">Default marshaling for delegates</span></span>  
 <span data-ttu-id="6aae1-159">托管委托基于后述调用机制封送为 COM 接口或函数指针：</span><span class="sxs-lookup"><span data-stu-id="6aae1-159">A managed delegate is marshaled as a COM interface or as a function pointer, based on the calling mechanism:</span></span>  
  
-   <span data-ttu-id="6aae1-160">对于平台调用，默认情况下，委托作为非托管函数指针进行封送。</span><span class="sxs-lookup"><span data-stu-id="6aae1-160">For platform invoke, a delegate is marshaled as an unmanaged function pointer by default.</span></span>  
  
-   <span data-ttu-id="6aae1-161">对于 COM 互操作，默认情况下，委托作为 _Delegate 类型的 COM 接口进行封送。</span><span class="sxs-lookup"><span data-stu-id="6aae1-161">For COM interop, a delegate is marshaled as a COM interface of type **_Delegate** by default.</span></span> <span data-ttu-id="6aae1-162">在 Mscorlib.tlb 类型库中定义 **_Delegate** 接口且该接口包含 <xref:System.Delegate.DynamicInvoke%2A?displayProperty=nameWithType> 方法，使你可以调用该委托引用的方法。</span><span class="sxs-lookup"><span data-stu-id="6aae1-162">The **_Delegate** interface is defined in the Mscorlib.tlb type library and contains the <xref:System.Delegate.DynamicInvoke%2A?displayProperty=nameWithType> method, which enables you to call the method that the delegate references.</span></span>  
  
 <span data-ttu-id="6aae1-163">下表显示托管委托数据类型的封送处理选项。</span><span class="sxs-lookup"><span data-stu-id="6aae1-163">The following table shows the marshaling options for the managed delegate data type.</span></span> <span data-ttu-id="6aae1-164"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性提供若干 <xref:System.Runtime.InteropServices.UnmanagedType> 枚举值来封送委托。</span><span class="sxs-lookup"><span data-stu-id="6aae1-164">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal delegates.</span></span>  
  
|<span data-ttu-id="6aae1-165">枚举类型</span><span class="sxs-lookup"><span data-stu-id="6aae1-165">Enumeration type</span></span>|<span data-ttu-id="6aae1-166">非托管格式说明</span><span class="sxs-lookup"><span data-stu-id="6aae1-166">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|<span data-ttu-id="6aae1-167">UnmanagedType.FunctionPtr</span><span class="sxs-lookup"><span data-stu-id="6aae1-167">**UnmanagedType.FunctionPtr**</span></span>|<span data-ttu-id="6aae1-168">非托管函数指针。</span><span class="sxs-lookup"><span data-stu-id="6aae1-168">An unmanaged function pointer.</span></span>|  
|<span data-ttu-id="6aae1-169">UnmanagedType.Interface</span><span class="sxs-lookup"><span data-stu-id="6aae1-169">**UnmanagedType.Interface**</span></span>|<span data-ttu-id="6aae1-170">在 Mscorlib.tlb 中定义的 _Delegate 类型的接口。</span><span class="sxs-lookup"><span data-stu-id="6aae1-170">An interface of type **_Delegate**, as defined in Mscorlib.tlb.</span></span>|  
  
 <span data-ttu-id="6aae1-171">请考虑下面的示例代码，其中将 `DelegateTestInterface` 的方法导出到 COM 类型库。</span><span class="sxs-lookup"><span data-stu-id="6aae1-171">Consider the following example code in which the methods of `DelegateTestInterface` are exported to a COM type library.</span></span> <span data-ttu-id="6aae1-172">请注意，只有标记为 ref（或 ByRef）关键字的委托作为 In/Out 参数传递。</span><span class="sxs-lookup"><span data-stu-id="6aae1-172">Notice that only delegates marked with the **ref** (or **ByRef**) keyword are passed as In/Out parameters.</span></span>  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
public interface DelegateTest {  
void m1(Delegate d);  
void m2([MarshalAs(UnmanagedType.Interface)] Delegate d);     
void m3([MarshalAs(UnmanagedType.Interface)] ref Delegate d);    
void m4([MarshalAs(UnmanagedType.FunctionPtr)] Delegate d);   
void m5([MarshalAs(UnmanagedType.FunctionPtr)] ref Delegate d);     
}  
```  
  
### <a name="type-library-representation"></a><span data-ttu-id="6aae1-173">类型库表示形式</span><span class="sxs-lookup"><span data-stu-id="6aae1-173">Type library representation</span></span>  
  
```  
importlib("mscorlib.tlb");  
interface DelegateTest : IDispatch {  
[id(…)] HRESULT m1([in] _Delegate* d);  
[id(…)] HRESULT m2([in] _Delegate* d);  
[id(…)] HRESULT m3([in, out] _Delegate** d);  
[id()] HRESULT m4([in] int d);  
[id()] HRESULT m5([in, out] int *d);  
   };  
```  
  
 <span data-ttu-id="6aae1-174">可以取消引用函数指针，就像可以取消引用任何其他非托管函数指针一样。</span><span class="sxs-lookup"><span data-stu-id="6aae1-174">A function pointer can be dereferenced, just as any other unmanaged function pointer can be dereferenced.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6aae1-175">对指向由非托管代码持有的托管委托的函数指针的引用不会阻止公共语言运行时对托管对象执行垃圾收集。</span><span class="sxs-lookup"><span data-stu-id="6aae1-175">A reference to the function pointer to a managed delegate held by unmanaged code does not prevent the common language runtime from performing garbage collection on the managed object.</span></span>  
  
 <span data-ttu-id="6aae1-176">例如，下面的代码是错误的，因为对传递给 `SetChangeHandler` 方法的 `cb` 对象的引用不会使 `cb` 在超出 `Test` 方法的生存期时仍保持活动。</span><span class="sxs-lookup"><span data-stu-id="6aae1-176">For example, the following code is incorrect because the reference to the `cb` object, passed to the `SetChangeHandler` method, does not keep `cb` alive beyond the life of the `Test` method.</span></span> <span data-ttu-id="6aae1-177">一旦对 `cb` 对象进行垃圾收集，传递给 `SetChangeHandler` 的函数指针将不再有效。</span><span class="sxs-lookup"><span data-stu-id="6aae1-177">Once the `cb` object is garbage collected, the function pointer passed to `SetChangeHandler` is no longer valid.</span></span>  
  
```csharp  
public class ExternalAPI {  
   [DllImport("External.dll")]  
   public static extern void SetChangeHandler(  
      [MarshalAs(UnmanagedType.FunctionPtr)]ChangeDelegate d);  
}  
public delegate bool ChangeDelegate([MarshalAs(UnmanagedType.LPWStr) string S);  
public class CallBackClass {  
   public bool OnChange(string S){ return true;}  
}  
internal class DelegateTest {  
   public static void Test() {  
      CallBackClass cb = new CallBackClass();  
      // Caution: The following reference on the cb object does not keep the   
      // object from being garbage collected after the Main method   
      // executes.  
      ExternalAPI.SetChangeHandler(new ChangeDelegate(cb.OnChange));     
   }  
}  
```  
  
 <span data-ttu-id="6aae1-178">若要补偿意外的垃圾回收，只要非托管的函数指针在使用中时，调用方必须确保 `cb` 对象保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="6aae1-178">To compensate for unexpected garbage collection, the caller must ensure that the `cb` object is kept alive as long as the unmanaged function pointer is in use.</span></span> <span data-ttu-id="6aae1-179">可以在不再需要函数指针时，按以下示例所示让非托管代码通知托管代码（可选）。</span><span class="sxs-lookup"><span data-stu-id="6aae1-179">Optionally, you can have the unmanaged code notify the managed code when the function pointer is no longer needed, as the following example shows.</span></span>  
  
```csharp  
internal class DelegateTest {  
   CallBackClass cb;  
   // Called before ever using the callback function.  
   public static void SetChangeHandler() {  
      cb = new CallBackClass();  
      ExternalAPI.SetChangeHandler(new ChangeDelegate(cb.OnChange));  
   }  
   // Called after using the callback function for the last time.  
   public static void RemoveChangeHandler() {  
      // The cb object can be collected now. The unmanaged code is   
      // finished with the callback function.  
      cb = null;  
   }  
}  
```  
  
## <a name="default-marshaling-for-value-types"></a><span data-ttu-id="6aae1-180">值类型的默认封送处理</span><span class="sxs-lookup"><span data-stu-id="6aae1-180">Default marshaling for value types</span></span>  
 <span data-ttu-id="6aae1-181">大多数值类型（如整数和浮点数）是 [blittable](../../../docs/framework/interop/blittable-and-non-blittable-types.md)类型，不需要封送处理。</span><span class="sxs-lookup"><span data-stu-id="6aae1-181">Most value types, such as integers and floating-point numbers, are [blittable](../../../docs/framework/interop/blittable-and-non-blittable-types.md) and do not require marshaling.</span></span> <span data-ttu-id="6aae1-182">其他[非 blittable](../../../docs/framework/interop/blittable-and-non-blittable-types.md) 类型在托管和非托管内存中具有不同的表示形式，且需要封送处理。</span><span class="sxs-lookup"><span data-stu-id="6aae1-182">Other [non-blittable](../../../docs/framework/interop/blittable-and-non-blittable-types.md) types have dissimilar representations in managed and unmanaged memory and do require marshaling.</span></span> <span data-ttu-id="6aae1-183">其他类型仍需要跨互操作边界的显式格式设置。</span><span class="sxs-lookup"><span data-stu-id="6aae1-183">Still other types require explicit formatting across the interoperation boundary.</span></span>  
  
 <span data-ttu-id="6aae1-184">本主题提供以下有关格式化的值类型的信息：</span><span class="sxs-lookup"><span data-stu-id="6aae1-184">This topic provides the follow information on formatted value types:</span></span>  
  
-   [<span data-ttu-id="6aae1-185">在平台调用中使用的值类型</span><span class="sxs-lookup"><span data-stu-id="6aae1-185">Value Types Used in Platform Invoke</span></span>](#cpcondefaultmarshalingforvaluetypesanchor2)  
  
-   [<span data-ttu-id="6aae1-186">在 COM 互操作中使用的值类型</span><span class="sxs-lookup"><span data-stu-id="6aae1-186">Value Types Used in COM Interop</span></span>](#cpcondefaultmarshalingforvaluetypesanchor3)  
  
 <span data-ttu-id="6aae1-187">除了介绍格式化的类型，本主题识别具有异常封送处理行为的[系统值类型](#cpcondefaultmarshalingforvaluetypesanchor1)。</span><span class="sxs-lookup"><span data-stu-id="6aae1-187">In addition to describing formatted types, this topic identifies [System Value Types](#cpcondefaultmarshalingforvaluetypesanchor1) that have unusual marshaling behavior.</span></span>  
  
 <span data-ttu-id="6aae1-188">格式化的类型是复杂类型，其中包含显式控制其成员在内存中的布局的信息。</span><span class="sxs-lookup"><span data-stu-id="6aae1-188">A formatted type is a complex type that contains information that explicitly controls the layout of its members in memory.</span></span> <span data-ttu-id="6aae1-189">使用 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 属性提供成员布局信息。</span><span class="sxs-lookup"><span data-stu-id="6aae1-189">The member layout information is provided using the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute.</span></span> <span data-ttu-id="6aae1-190">布局可以是以下 <xref:System.Runtime.InteropServices.LayoutKind> 枚举值之一：</span><span class="sxs-lookup"><span data-stu-id="6aae1-190">The layout can be one of the following <xref:System.Runtime.InteropServices.LayoutKind> enumeration values:</span></span>  
  
-   <span data-ttu-id="6aae1-191">LayoutKind.Automatic</span><span class="sxs-lookup"><span data-stu-id="6aae1-191">**LayoutKind.Automatic**</span></span>  
  
     <span data-ttu-id="6aae1-192">指示公共语言运行时可以自由重新排序类型的成员以提高效率。</span><span class="sxs-lookup"><span data-stu-id="6aae1-192">Indicates that the common language runtime is free to reorder the members of the type for efficiency.</span></span> <span data-ttu-id="6aae1-193">但是，当值类型传递到非托管代码中时，成员的布局是可预测的。</span><span class="sxs-lookup"><span data-stu-id="6aae1-193">However, when a value type is passed to unmanaged code, the layout of the members is predictable.</span></span> <span data-ttu-id="6aae1-194">尝试将这种结构进行自动封送处理会导致异常。</span><span class="sxs-lookup"><span data-stu-id="6aae1-194">An attempt to marshal such a structure automatically causes an exception.</span></span>  
  
-   <span data-ttu-id="6aae1-195">LayoutKind.Sequential</span><span class="sxs-lookup"><span data-stu-id="6aae1-195">**LayoutKind.Sequential**</span></span>  
  
     <span data-ttu-id="6aae1-196">指示在非托管内存内布局该类型的成员，其顺序与其在托管类型定义中出现的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="6aae1-196">Indicates that the members of the type are to be laid out in unmanaged memory in the same order in which they appear in the managed type definition.</span></span>  
  
-   <span data-ttu-id="6aae1-197">LayoutKind.Explicit</span><span class="sxs-lookup"><span data-stu-id="6aae1-197">**LayoutKind.Explicit**</span></span>  
  
     <span data-ttu-id="6aae1-198">指示根据随每个字段提供的 <xref:System.Runtime.InteropServices.FieldOffsetAttribute> 对成员进行布局。</span><span class="sxs-lookup"><span data-stu-id="6aae1-198">Indicates that the members are laid out according to the <xref:System.Runtime.InteropServices.FieldOffsetAttribute> supplied with each field.</span></span>  
  
<a name="cpcondefaultmarshalingforvaluetypesanchor2"></a>   
### <a name="value-types-used-in-platform-invoke"></a><span data-ttu-id="6aae1-199">在平台调用中使用的值类型</span><span class="sxs-lookup"><span data-stu-id="6aae1-199">Value Types Used in Platform Invoke</span></span>  
 <span data-ttu-id="6aae1-200">在以下示例中，`Point` 和 `Rect` 类型使用 StructLayoutAttribute 提供成员布局信息。</span><span class="sxs-lookup"><span data-stu-id="6aae1-200">In the following example the `Point` and `Rect` types provide member layout information using the **StructLayoutAttribute**.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
<StructLayout(LayoutKind.Sequential)> Public Structure Point  
   Public x As Integer  
   Public y As Integer  
End Structure  
<StructLayout(LayoutKind.Explicit)> Public Structure Rect  
   <FieldOffset(0)> Public left As Integer  
   <FieldOffset(4)> Public top As Integer  
   <FieldOffset(8)> Public right As Integer  
   <FieldOffset(12)> Public bottom As Integer  
End Structure  
```  
  
```csharp  
using System.Runtime.InteropServices;  
[StructLayout(LayoutKind.Sequential)]  
public struct Point {  
   public int x;  
   public int y;  
}     
  
[StructLayout(LayoutKind.Explicit)]  
public struct Rect {  
   [FieldOffset(0)] public int left;  
   [FieldOffset(4)] public int top;  
   [FieldOffset(8)] public int right;  
   [FieldOffset(12)] public int bottom;  
}  
```  
  
 <span data-ttu-id="6aae1-201">当封送到非托管代码时，这些格式化的类型作为 C 样式结构进行封送。</span><span class="sxs-lookup"><span data-stu-id="6aae1-201">When marshaled to unmanaged code, these formatted types are marshaled as C-style structures.</span></span> <span data-ttu-id="6aae1-202">这为调用具有结构自变量的非托管 API 提供一种简单的方法。</span><span class="sxs-lookup"><span data-stu-id="6aae1-202">This provides an easy way of calling an unmanaged API that has structure arguments.</span></span> <span data-ttu-id="6aae1-203">例如，`POINT` 和 `RECT` 结构可按下述方式传递到 Microsoft Win32 API PtInRect 函数：</span><span class="sxs-lookup"><span data-stu-id="6aae1-203">For example, the `POINT` and `RECT` structures can be passed to the Microsoft Win32 API **PtInRect** function as follows:</span></span>  
  
```  
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 <span data-ttu-id="6aae1-204">可以使用下面的平台调用定义传递结构：</span><span class="sxs-lookup"><span data-stu-id="6aae1-204">You can pass structures using the following platform invoke definition:</span></span>  
  
```vb  
Class Win32API      
   Declare Auto Function PtInRect Lib "User32.dll" _  
    (ByRef r As Rect, p As Point) As Boolean  
End Class  
```  
  
```csharp  
class Win32API {  
   [DllImport("User32.dll")]  
   public static extern Bool PtInRect(ref Rect r, Point p);  
}  
```  
  
 <span data-ttu-id="6aae1-205">必须由引用传递 `Rect` 值类型，因为非托管 API 预期有一个指向 `RECT` 的指针被传递给函数。</span><span class="sxs-lookup"><span data-stu-id="6aae1-205">The `Rect` value type must be passed by reference because the unmanaged API is expecting a pointer to a `RECT` to be passed to the function.</span></span> <span data-ttu-id="6aae1-206">由值传递 `Point` 值类型，因为非托管的 API 需要在堆栈上传递 `POINT`。</span><span class="sxs-lookup"><span data-stu-id="6aae1-206">The `Point` value type is passed by value because the unmanaged API expects the `POINT` to be passed on the stack.</span></span> <span data-ttu-id="6aae1-207">此细微差别非常重要。</span><span class="sxs-lookup"><span data-stu-id="6aae1-207">This subtle difference is very important.</span></span> <span data-ttu-id="6aae1-208">引用作为指针传递到非托管代码。</span><span class="sxs-lookup"><span data-stu-id="6aae1-208">References are passed to unmanaged code as pointers.</span></span> <span data-ttu-id="6aae1-209">值传递到堆栈上的非托管代码。</span><span class="sxs-lookup"><span data-stu-id="6aae1-209">Values are passed to unmanaged code on the stack.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6aae1-210">当格式化的类型作为结构进行封送处理时，仅可访问类型中的字段。</span><span class="sxs-lookup"><span data-stu-id="6aae1-210">When a formatted type is marshaled as a structure, only the fields within the type are accessible.</span></span> <span data-ttu-id="6aae1-211">如果该类型具有方法、属性或事件，无法从非托管代码对它们进行访问。</span><span class="sxs-lookup"><span data-stu-id="6aae1-211">If the type has methods, properties, or events, they are inaccessible from unmanaged code.</span></span>  
  
 <span data-ttu-id="6aae1-212">类也可以作为 C 样式结构封送到非托管代码，只要它们具有固定成员布局。</span><span class="sxs-lookup"><span data-stu-id="6aae1-212">Classes can also be marshaled to unmanaged code as C-style structures, provided they have fixed member layout.</span></span> <span data-ttu-id="6aae1-213">类的成员布局信息也通过 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 属性提供。</span><span class="sxs-lookup"><span data-stu-id="6aae1-213">The member layout information for a class is also provided with the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute.</span></span> <span data-ttu-id="6aae1-214">具有固定布局的值类型与具有固定布局的类之间的主要区别在于它们被封送到非托管代码的方式。</span><span class="sxs-lookup"><span data-stu-id="6aae1-214">The main difference between value types with fixed layout and classes with fixed layout is the way in which they are marshaled to unmanaged code.</span></span> <span data-ttu-id="6aae1-215">由值（在堆栈上）传递值类型，由此，调用方看不到任何由被调用方对该类型的成员所做的更改。</span><span class="sxs-lookup"><span data-stu-id="6aae1-215">Value types are passed by value (on the stack) and consequently any changes made to the members of the type by the callee are not seen by the caller.</span></span> <span data-ttu-id="6aae1-216">由引用（在堆栈上传递对该类型的引用）传递引用类型；由此，调用方将看到被调用方对该类型的可直接复制到本机结构中的类型成员所做的所有更改。</span><span class="sxs-lookup"><span data-stu-id="6aae1-216">Reference types are passed by reference (a reference to the type is passed on the stack); consequently, all changes made to blittable-type members of a type by the callee are seen by the caller.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6aae1-217">如果引用类型具有非直接复制到本机结构中的类型成员，则需要进行两次转换：第一次是当参数传递到非托管端时，第二次是从调用返回时。</span><span class="sxs-lookup"><span data-stu-id="6aae1-217">If a reference type has members of non-blittable types, conversion is required twice: the first time when an argument is passed to the unmanaged side and the second time on return from the call.</span></span> <span data-ttu-id="6aae1-218">由于此增加的开销，如果调用方想要查看被调用方所做的更改，必须将输入/输出参数显式应用到某个自变量。</span><span class="sxs-lookup"><span data-stu-id="6aae1-218">Due to this added overhead, In/Out parameters must be explicitly applied to an argument if the caller wants to see changes made by the callee.</span></span>  
  
 <span data-ttu-id="6aae1-219">在以下示例中，`SystemTime` 类具有顺序成员布局，并且可以被传递给 Win32 API GetSystemTime 函数。</span><span class="sxs-lookup"><span data-stu-id="6aae1-219">In the following example, the `SystemTime` class has sequential member layout and can be passed to the Win32 API **GetSystemTime** function.</span></span>  
  
```vb  
<StructLayout(LayoutKind.Sequential)> Public Class SystemTime  
   Public wYear As System.UInt16  
   Public wMonth As System.UInt16  
   Public wDayOfWeek As System.UInt16  
   Public wDay As System.UInt16  
   Public wHour As System.UInt16  
   Public wMinute As System.UInt16  
   Public wSecond As System.UInt16  
   Public wMilliseconds As System.UInt16  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
   public class SystemTime {  
   public ushort wYear;   
   public ushort wMonth;  
   public ushort wDayOfWeek;   
   public ushort wDay;   
   public ushort wHour;   
   public ushort wMinute;   
   public ushort wSecond;   
   public ushort wMilliseconds;   
}  
```  
  
 <span data-ttu-id="6aae1-220">GetSystemTime 函数定义如下：</span><span class="sxs-lookup"><span data-stu-id="6aae1-220">The **GetSystemTime** function is defined as follows:</span></span>  
  
```  
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 <span data-ttu-id="6aae1-221">GetSystemTime 的等效平台调用定义如下：</span><span class="sxs-lookup"><span data-stu-id="6aae1-221">The equivalent platform invoke definition for **GetSystemTime** is as follows:</span></span>  
  
```vb  
Public Class Win32  
   Declare Auto Sub GetSystemTime Lib "Kernel32.dll" (ByVal sysTime _  
   As SystemTime)  
End Class  
```  
  
```csharp  
class Win32API {  
   [DllImport("Kernel32.dll", CharSet=CharSet.Auto)]  
   public static extern void GetSystemTime(SystemTime st);  
}  
```  
  
 <span data-ttu-id="6aae1-222">请注意，`SystemTime` 参数并不类型化为引用参数，因为 `SystemTime` 是一个类，而不是值类型。</span><span class="sxs-lookup"><span data-stu-id="6aae1-222">Notice that the `SystemTime` argument is not typed as a reference argument because `SystemTime` is a class, not a value type.</span></span> <span data-ttu-id="6aae1-223">与值类型不同，类始终由引用传递。</span><span class="sxs-lookup"><span data-stu-id="6aae1-223">Unlike value types, classes are always passed by reference.</span></span>  
  
 <span data-ttu-id="6aae1-224">下面的代码示例显示一个不同的 `Point` 类，此类具有一个名为 `SetXY` 的方法。</span><span class="sxs-lookup"><span data-stu-id="6aae1-224">The following code example shows a different `Point` class that has a method called `SetXY`.</span></span> <span data-ttu-id="6aae1-225">因为该类型具有顺序布局，因此可以传递到非托管代码并作为一种结构封送。</span><span class="sxs-lookup"><span data-stu-id="6aae1-225">Because the type has sequential layout, it can be passed to unmanaged code and marshaled as a structure.</span></span> <span data-ttu-id="6aae1-226">但是，`SetXY` 成员不能从非托管代码中调用，即使由引用传递对象。</span><span class="sxs-lookup"><span data-stu-id="6aae1-226">However, the `SetXY` member is not callable from unmanaged code, even though the object is passed by reference.</span></span>  
  
```vb  
<StructLayout(LayoutKind.Sequential)> Public Class Point  
   Private x, y As Integer  
   Public Sub SetXY(x As Integer, y As Integer)  
      Me.x = x  
      Me.y = y  
   End Sub  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public class Point {  
   int x, y;  
   public void SetXY(int x, int y){   
      this.x = x;  
      this.y = y;  
   }  
}  
```  
  
<a name="cpcondefaultmarshalingforvaluetypesanchor3"></a>   
### <a name="value-types-used-in-com-interop"></a><span data-ttu-id="6aae1-227">在 COM 互操作中使用的值类型</span><span class="sxs-lookup"><span data-stu-id="6aae1-227">Value Types Used in COM Interop</span></span>  
 <span data-ttu-id="6aae1-228">格式化的类型也可传递给 COM 互操作方法调用。</span><span class="sxs-lookup"><span data-stu-id="6aae1-228">Formatted types can also be passed to COM interop method calls.</span></span> <span data-ttu-id="6aae1-229">实际上，当导出到类型库时，值类型就自动转换为结构。</span><span class="sxs-lookup"><span data-stu-id="6aae1-229">In fact, when exported to a type library, value types are automatically converted to structures.</span></span> <span data-ttu-id="6aae1-230">如下面的示例所示，`Point` 值类型变为类型定义 (typedef)，名称为 `Point`。</span><span class="sxs-lookup"><span data-stu-id="6aae1-230">As the following example shows, the `Point` value type becomes a type definition (typedef) with the name `Point`.</span></span> <span data-ttu-id="6aae1-231">在类型库中其他位置对 `Point` 值类型的所有引用都替换为 `Point` typedef。</span><span class="sxs-lookup"><span data-stu-id="6aae1-231">All references to the `Point` value type elsewhere in the type library are replaced with the `Point` typedef.</span></span>  
  
 <span data-ttu-id="6aae1-232">**类型库表示形式**</span><span class="sxs-lookup"><span data-stu-id="6aae1-232">**Type library representation**</span></span>  
  
```  
typedef struct tagPoint {  
   int x;  
   int y;  
} Point;  
interface _Graphics {  
   …  
   HRESULT SetPoint ([in] Point p)  
   HRESULT SetPointRef ([in,out] Point *p)  
   HRESULT GetPoint ([out,retval] Point *p)  
}  
```  
  
 <span data-ttu-id="6aae1-233">当通过 COM 接口进行封送处理时，使用用于封送值和封送对平台调用的调用的引用的规则。</span><span class="sxs-lookup"><span data-stu-id="6aae1-233">The same rules used to marshal values and references to platform invoke calls are used when marshaling through COM interfaces.</span></span> <span data-ttu-id="6aae1-234">例如，当 `Point` 值类型的实例从 .NET Framework 传递到 COM 时，则由值传递 `Point`。</span><span class="sxs-lookup"><span data-stu-id="6aae1-234">For example, when an instance of the `Point` value type is passed from the .NET Framework to COM, the `Point` is passed by value.</span></span> <span data-ttu-id="6aae1-235">如果 `Point` 值类型由引用传递，则在堆栈上传递指向 `Point` 的指针。</span><span class="sxs-lookup"><span data-stu-id="6aae1-235">If the `Point` value type is passed by reference, a pointer to a `Point` is passed on the stack.</span></span> <span data-ttu-id="6aae1-236">互操作封送拆收器不支持任一方向更高级别的间接寻址 (Point \*\*)。</span><span class="sxs-lookup"><span data-stu-id="6aae1-236">The interop marshaler does not support higher levels of indirection (**Point \*\***) in either direction.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6aae1-237">将 <xref:System.Runtime.InteropServices.LayoutKind> 枚举值设置为显式的结构无法用于 COM 互操作，因为导出的类型库不能表达显式布局。</span><span class="sxs-lookup"><span data-stu-id="6aae1-237">Structures having the <xref:System.Runtime.InteropServices.LayoutKind> enumeration value set to **Explicit** cannot be used in COM interop because the exported type library cannot express an explicit layout.</span></span>  
  
<a name="cpcondefaultmarshalingforvaluetypesanchor1"></a>   
### <a name="system-value-types"></a><span data-ttu-id="6aae1-238">系统值类型</span><span class="sxs-lookup"><span data-stu-id="6aae1-238">System Value Types</span></span>  
 <span data-ttu-id="6aae1-239"><xref:System> 命名空间具有多个表示运行时原始类型装箱形式的值类型。</span><span class="sxs-lookup"><span data-stu-id="6aae1-239">The <xref:System> namespace has several value types that represent the boxed form of the runtime primitive types.</span></span> <span data-ttu-id="6aae1-240">例如，值类型 <xref:System.Int32?displayProperty=nameWithType> 结构表示 ELEMENT_TYPE_I4 的装箱形式。</span><span class="sxs-lookup"><span data-stu-id="6aae1-240">For example, the value type <xref:System.Int32?displayProperty=nameWithType> structure represents the boxed form of **ELEMENT_TYPE_I4**.</span></span> <span data-ttu-id="6aae1-241">不像其他格式化类型将这些类型作为结构进行封送处理，而是以它们装箱的原始类型的相同方式将它们封送处理。</span><span class="sxs-lookup"><span data-stu-id="6aae1-241">Instead of marshaling these types as structures, as other formatted types are, you marshal them in the same way as the primitive types they box.</span></span> <span data-ttu-id="6aae1-242">因此，System.Int32 作为 ELEMENT_TYPE_I4 封送处理，而不是作为包含长类型的单个成员的结构封送处理。</span><span class="sxs-lookup"><span data-stu-id="6aae1-242">**System.Int32** is therefore marshaled as **ELEMENT_TYPE_I4** instead of as a structure containing a single member of type **long**.</span></span> <span data-ttu-id="6aae1-243">下表包含系统命名空间中的值类型列表，这些值类型是基元类型的装箱表示形式。</span><span class="sxs-lookup"><span data-stu-id="6aae1-243">The following table contains a list of the value types in the **System** namespace that are boxed representations of primitive types.</span></span>  
  
|<span data-ttu-id="6aae1-244">系统值类型</span><span class="sxs-lookup"><span data-stu-id="6aae1-244">System value type</span></span>|<span data-ttu-id="6aae1-245">元素类型</span><span class="sxs-lookup"><span data-stu-id="6aae1-245">Element type</span></span>|  
|-----------------------|------------------|  
|<xref:System.Boolean?displayProperty=nameWithType>|<span data-ttu-id="6aae1-246">ELEMENT_TYPE_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="6aae1-246">**ELEMENT_TYPE_BOOLEAN**</span></span>|  
|<xref:System.SByte?displayProperty=nameWithType>|<span data-ttu-id="6aae1-247">ELEMENT_TYPE_I1</span><span class="sxs-lookup"><span data-stu-id="6aae1-247">**ELEMENT_TYPE_I1**</span></span>|  
|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="6aae1-248">ELEMENT_TYPE_UI1</span><span class="sxs-lookup"><span data-stu-id="6aae1-248">**ELEMENT_TYPE_UI1**</span></span>|  
|<xref:System.Char?displayProperty=nameWithType>|<span data-ttu-id="6aae1-249">ELEMENT_TYPE_CHAR</span><span class="sxs-lookup"><span data-stu-id="6aae1-249">**ELEMENT_TYPE_CHAR**</span></span>|  
|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="6aae1-250">ELEMENT_TYPE_I2</span><span class="sxs-lookup"><span data-stu-id="6aae1-250">**ELEMENT_TYPE_I2**</span></span>|  
|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="6aae1-251">ELEMENT_TYPE_U2</span><span class="sxs-lookup"><span data-stu-id="6aae1-251">**ELEMENT_TYPE_U2**</span></span>|  
|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="6aae1-252">ELEMENT_TYPE_I4</span><span class="sxs-lookup"><span data-stu-id="6aae1-252">**ELEMENT_TYPE_I4**</span></span>|  
|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="6aae1-253">ELEMENT_TYPE_U4</span><span class="sxs-lookup"><span data-stu-id="6aae1-253">**ELEMENT_TYPE_U4**</span></span>|  
|<xref:System.Int64?displayProperty=nameWithType>|<span data-ttu-id="6aae1-254">ELEMENT_TYPE_I8</span><span class="sxs-lookup"><span data-stu-id="6aae1-254">**ELEMENT_TYPE_I8**</span></span>|  
|<xref:System.UInt64?displayProperty=nameWithType>|<span data-ttu-id="6aae1-255">ELEMENT_TYPE_U8</span><span class="sxs-lookup"><span data-stu-id="6aae1-255">**ELEMENT_TYPE_U8**</span></span>|  
|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="6aae1-256">ELEMENT_TYPE_R4</span><span class="sxs-lookup"><span data-stu-id="6aae1-256">**ELEMENT_TYPE_R4**</span></span>|  
|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="6aae1-257">ELEMENT_TYPE_R8</span><span class="sxs-lookup"><span data-stu-id="6aae1-257">**ELEMENT_TYPE_R8**</span></span>|  
|<xref:System.String?displayProperty=nameWithType>|<span data-ttu-id="6aae1-258">ELEMENT_TYPE_STRING</span><span class="sxs-lookup"><span data-stu-id="6aae1-258">**ELEMENT_TYPE_STRING**</span></span>|  
|<xref:System.IntPtr?displayProperty=nameWithType>|<span data-ttu-id="6aae1-259">ELEMENT_TYPE_I</span><span class="sxs-lookup"><span data-stu-id="6aae1-259">**ELEMENT_TYPE_I**</span></span>|  
|<xref:System.UIntPtr?displayProperty=nameWithType>|<span data-ttu-id="6aae1-260">ELEMENT_TYPE_U</span><span class="sxs-lookup"><span data-stu-id="6aae1-260">**ELEMENT_TYPE_U**</span></span>|  
  
 <span data-ttu-id="6aae1-261">系统命名空间中一些其他值类型的处理方式则不同。</span><span class="sxs-lookup"><span data-stu-id="6aae1-261">Some other value types in the **System** namespace are handled differently.</span></span> <span data-ttu-id="6aae1-262">由于非托管代码已具备这些类型的完善格式，因此封送拆收器具有用于将其封送的特殊规则。</span><span class="sxs-lookup"><span data-stu-id="6aae1-262">Because the unmanaged code already has well-established formats for these types, the marshaler has special rules for marshaling them.</span></span> <span data-ttu-id="6aae1-263">下表列出系统命名空间中的特殊值类型，以及其封送到的非托管类型。</span><span class="sxs-lookup"><span data-stu-id="6aae1-263">The following table lists the special value types in the **System** namespace, as well as the unmanaged type they are marshaled to.</span></span>  
  
|<span data-ttu-id="6aae1-264">系统值类型</span><span class="sxs-lookup"><span data-stu-id="6aae1-264">System value type</span></span>|<span data-ttu-id="6aae1-265">IDL 类型</span><span class="sxs-lookup"><span data-stu-id="6aae1-265">IDL type</span></span>|  
|-----------------------|--------------|  
|<xref:System.DateTime?displayProperty=nameWithType>|<span data-ttu-id="6aae1-266">DATE</span><span class="sxs-lookup"><span data-stu-id="6aae1-266">**DATE**</span></span>|  
|<xref:System.Decimal?displayProperty=nameWithType>|<span data-ttu-id="6aae1-267">DECIMAL</span><span class="sxs-lookup"><span data-stu-id="6aae1-267">**DECIMAL**</span></span>|  
|<xref:System.Guid?displayProperty=nameWithType>|<span data-ttu-id="6aae1-268">**GUID**</span><span class="sxs-lookup"><span data-stu-id="6aae1-268">**GUID**</span></span>|  
|<xref:System.Drawing.Color?displayProperty=nameWithType>|<span data-ttu-id="6aae1-269">OLE_COLOR</span><span class="sxs-lookup"><span data-stu-id="6aae1-269">**OLE_COLOR**</span></span>|  
  
 <span data-ttu-id="6aae1-270">下面的代码显示 Stdole2 类型库中非托管类型 DATE、GUID、DECIMAL 和 OLE_COLOR 的定义。</span><span class="sxs-lookup"><span data-stu-id="6aae1-270">The following code shows the definition of the unmanaged types **DATE**, **GUID**, **DECIMAL**, and **OLE_COLOR** in the Stdole2 type library.</span></span>  
  
#### <a name="type-library-representation"></a><span data-ttu-id="6aae1-271">类型库表示形式</span><span class="sxs-lookup"><span data-stu-id="6aae1-271">Type library representation</span></span>  
  
```  
typedef double DATE;  
typedef DWORD OLE_COLOR;  
  
typedef struct tagDEC {  
    USHORT    wReserved;  
    BYTE      scale;  
    BYTE      sign;  
    ULONG     Hi32;  
    ULONGLONG Lo64;  
} DECIMAL;  
  
typedef struct tagGUID {  
    DWORD Data1;  
    WORD  Data2;  
    WORD  Data3;  
    BYTE  Data4[ 8 ];  
} GUID;  
```  
  
 <span data-ttu-id="6aae1-272">下面的代码显示托管 `IValueTypes` 接口中的相应定义。</span><span class="sxs-lookup"><span data-stu-id="6aae1-272">The following code shows the corresponding definitions in the managed `IValueTypes` interface.</span></span>  
  
```vb  
Public Interface IValueTypes  
   Sub M1(d As System.DateTime)  
   Sub M2(d As System.Guid)  
   Sub M3(d As System.Decimal)  
   Sub M4(d As System.Drawing.Color)  
End Interface  
```  
  
```csharp  
public interface IValueTypes {  
   void M1(System.DateTime d);  
   void M2(System.Guid d);  
   void M3(System.Decimal d);  
   void M4(System.Drawing.Color d);  
}  
```  
  
#### <a name="type-library-representation"></a><span data-ttu-id="6aae1-273">类型库表示形式</span><span class="sxs-lookup"><span data-stu-id="6aae1-273">Type library representation</span></span>  
  
```  
[…]  
interface IValueTypes : IDispatch {  
   HRESULT M1([in] DATE d);  
   HRESULT M2([in] GUID d);  
   HRESULT M3([in] DECIMAL d);  
   HRESULT M4([in] OLE_COLOR d);  
};  
```  
  
## <a name="see-also"></a><span data-ttu-id="6aae1-274">请参阅</span><span class="sxs-lookup"><span data-stu-id="6aae1-274">See Also</span></span>  
 [<span data-ttu-id="6aae1-275">可直接复制到本机结构中的类型和非直接复制到本机结构中的类型</span><span class="sxs-lookup"><span data-stu-id="6aae1-275">Blittable and Non-Blittable Types</span></span>](../../../docs/framework/interop/blittable-and-non-blittable-types.md)  
 [<span data-ttu-id="6aae1-276">复制和锁定</span><span class="sxs-lookup"><span data-stu-id="6aae1-276">Copying and Pinning</span></span>](../../../docs/framework/interop/copying-and-pinning.md)  
 [<span data-ttu-id="6aae1-277">数组的默认封送处理</span><span class="sxs-lookup"><span data-stu-id="6aae1-277">Default Marshaling for Arrays</span></span>](../../../docs/framework/interop/default-marshaling-for-arrays.md)  
 [<span data-ttu-id="6aae1-278">对象的默认封送处理</span><span class="sxs-lookup"><span data-stu-id="6aae1-278">Default Marshaling for Objects</span></span>](../../../docs/framework/interop/default-marshaling-for-objects.md)  
 [<span data-ttu-id="6aae1-279">字符串的默认封送处理</span><span class="sxs-lookup"><span data-stu-id="6aae1-279">Default Marshaling for Strings</span></span>](../../../docs/framework/interop/default-marshaling-for-strings.md)
