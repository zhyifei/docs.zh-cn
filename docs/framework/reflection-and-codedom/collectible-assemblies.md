---
title: "动态类型生成可回收程序集"
description: 
ms.date: 08/29/2017
ms.prod: .net
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- reflection, dynamic assembly
- assemblies, collectible
- collectible assemblies, retrieving
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2c9a613f4cc13c3e4189a59ace2e05d01d1bcb4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="collectible-assemblies-for-dynamic-type-generation"></a><span data-ttu-id="db640-102">动态类型生成可回收程序集</span><span class="sxs-lookup"><span data-stu-id="db640-102">Collectible assemblies for dynamic type generation</span></span>

<span data-ttu-id="db640-103">*可回收程序集*可以无需卸载在其中创建它们的应用程序域中卸载的动态程序集。</span><span class="sxs-lookup"><span data-stu-id="db640-103">*Collectible assemblies* are dynamic assemblies that can be unloaded without unloading the application domain in which they were created.</span></span> <span data-ttu-id="db640-104">可以回收可回收程序集和其包含的类型使用的所有托管和非托管内存。</span><span class="sxs-lookup"><span data-stu-id="db640-104">All managed and unmanaged memory used by a collectible assembly and the types it contains can be reclaimed.</span></span> <span data-ttu-id="db640-105">从内部表中删除信息，如程序集名称。</span><span class="sxs-lookup"><span data-stu-id="db640-105">Information such as the assembly name is removed from internal tables.</span></span>

<span data-ttu-id="db640-106">若要启用卸载功能，使用<xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndCollect?displayProperty=nameWithType>标志时创建的动态程序集。</span><span class="sxs-lookup"><span data-stu-id="db640-106">To enable unloading, use the <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndCollect?displayProperty=nameWithType> flag when you create a dynamic assembly.</span></span> <span data-ttu-id="db640-107">该程序集是暂时性 （即，不能保存），并受到中所述限制[可回收程序集的限制](#restrictions-on-collectible-assemblies)部分。</span><span class="sxs-lookup"><span data-stu-id="db640-107">The assembly is transient (that is, it cannot be saved) and is subject to limitations described in the [Restrictions on Collectible Assemblies](#restrictions-on-collectible-assemblies) section.</span></span> <span data-ttu-id="db640-108">当你释放与程序集关联的所有对象，公共语言运行时 (CLR) 将自动卸载可回收程序集。</span><span class="sxs-lookup"><span data-stu-id="db640-108">The common language runtime (CLR) unloads a collectible assembly automatically when you release all objects associated with the assembly.</span></span> <span data-ttu-id="db640-109">在所有其他方面，可回收程序集创建和使用其他动态程序集的方式相同。</span><span class="sxs-lookup"><span data-stu-id="db640-109">In all other respects, collectible assemblies are created and used in the same way as other dynamic assemblies.</span></span>

## <a name="lifetime-of-collectible-assemblies"></a><span data-ttu-id="db640-110">可回收程序集的生存期</span><span class="sxs-lookup"><span data-stu-id="db640-110">Lifetime of collectible assemblies</span></span>

<span data-ttu-id="db640-111">由其包含的类型和从这些类型创建的对象引用存在控制可回收程序集的生存期。</span><span class="sxs-lookup"><span data-stu-id="db640-111">The lifetime of a collectible assembly is controlled by the existence of references to the types it contains and the objects that are created from those types.</span></span> <span data-ttu-id="db640-112">只要存在的一个或多个以下，公共语言运行时不会卸载程序集 (`T`是在程序集中定义的任何类型):</span><span class="sxs-lookup"><span data-stu-id="db640-112">The common language runtime does not unload an assembly as long as one or more of the following exist (`T` is any type that is defined in the assembly):</span></span> 

- <span data-ttu-id="db640-113">`T` 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="db640-113">An instance of `T`.</span></span>

- <span data-ttu-id="db640-114">数组的实例`T`。</span><span class="sxs-lookup"><span data-stu-id="db640-114">An instance of an array of `T`.</span></span>
 
- <span data-ttu-id="db640-115">具有泛型类型的实例`T`作为其类型自变量之一。</span><span class="sxs-lookup"><span data-stu-id="db640-115">An instance of a generic type that has `T` as one of its type arguments.</span></span> <span data-ttu-id="db640-116">这包括的泛型集合`T`，即使该集合为空。</span><span class="sxs-lookup"><span data-stu-id="db640-116">This includes generic collections of `T`, even if that collection is empty.</span></span>

- <span data-ttu-id="db640-117">实例<xref:System.Type>或<xref:System.Reflection.Emit.TypeBuilder>表示`T`。</span><span class="sxs-lookup"><span data-stu-id="db640-117">An instance of <xref:System.Type> or <xref:System.Reflection.Emit.TypeBuilder> that represents `T`.</span></span> 

   > [!IMPORTANT]
   > <span data-ttu-id="db640-118">表示程序集的部分的所有对象，你必须将其都释放。</span><span class="sxs-lookup"><span data-stu-id="db640-118">You must release all objects that represent parts of the assembly.</span></span> <span data-ttu-id="db640-119"><xref:System.Reflection.Emit.ModuleBuilder>定义`T`都会保留对引用<xref:System.Reflection.Emit.TypeBuilder>，和<xref:System.Reflection.Emit.AssemblyBuilder>对象保留对引用<xref:System.Reflection.Emit.ModuleBuilder>，因此必须释放对这些对象的引用。</span><span class="sxs-lookup"><span data-stu-id="db640-119">The <xref:System.Reflection.Emit.ModuleBuilder> that defines `T` keeps a reference to the <xref:System.Reflection.Emit.TypeBuilder>, and the <xref:System.Reflection.Emit.AssemblyBuilder> object keeps a reference to the <xref:System.Reflection.Emit.ModuleBuilder>, so references to these objects must be released.</span></span> <span data-ttu-id="db640-120">甚至，如果存在<xref:System.Reflection.Emit.LocalBuilder>或<xref:System.Reflection.Emit.ILGenerator>在构造使用`T`会阻止卸载。</span><span class="sxs-lookup"><span data-stu-id="db640-120">Even the existence of a <xref:System.Reflection.Emit.LocalBuilder> or an <xref:System.Reflection.Emit.ILGenerator> used in the construction of `T` prevents unloading.</span></span>

- <span data-ttu-id="db640-121">对的静态引用`T`通过另一种动态定义类型`T1`，通过执行代码是否仍然可以访问。</span><span class="sxs-lookup"><span data-stu-id="db640-121">A static reference to `T` by another dynamically defined type `T1` that is still reachable by executing code.</span></span> <span data-ttu-id="db640-122">例如，`T1`可能派生自`T`，或`T`可能的方法中的参数的类型`T1`。</span><span class="sxs-lookup"><span data-stu-id="db640-122">For example, `T1` might derive from `T`, or `T` might be the type of a parameter in a method of `T1`.</span></span>
 
- <span data-ttu-id="db640-123">A **ByRef**所属的静态字段`T`。</span><span class="sxs-lookup"><span data-stu-id="db640-123">A **ByRef** to a static field that belongs to `T`.</span></span>

- <span data-ttu-id="db640-124">A <xref:System.RuntimeTypeHandle>， <xref:System.RuntimeFieldHandle>，或<xref:System.RuntimeMethodHandle>，是指`T`或的某个组件的`T`。</span><span class="sxs-lookup"><span data-stu-id="db640-124">A <xref:System.RuntimeTypeHandle>, <xref:System.RuntimeFieldHandle>, or <xref:System.RuntimeMethodHandle> that refers to `T` or to a component of `T`.</span></span>

- <span data-ttu-id="db640-125">实例的可能间接使用任何反射对象或直接访问<xref:System.Type>对象，表示`T`。</span><span class="sxs-lookup"><span data-stu-id="db640-125">An instance of any reflection object that could be used indirectly or directly to access the <xref:System.Type> object that represents `T`.</span></span> <span data-ttu-id="db640-126">例如，<xref:System.Type>对象`T`可从其元素类型是数组类型获取`T`，或从泛型类型具有`T`作为类型参数。</span><span class="sxs-lookup"><span data-stu-id="db640-126">For example, the <xref:System.Type> object for `T` can be obtained from an array type whose element type is `T`, or from a generic type that has `T` as a type argument.</span></span> 

- <span data-ttu-id="db640-127">一种方法`M`的任何线程调用堆栈上其中`M`是一种方法`T`或模块级方法在程序集中定义。</span><span class="sxs-lookup"><span data-stu-id="db640-127">A method `M` on the call stack of any thread, where `M` is a method of `T` or a module-level method that is defined in the assembly.</span></span>

- <span data-ttu-id="db640-128">程序集的模块中定义静态方法的委托。</span><span class="sxs-lookup"><span data-stu-id="db640-128">A delegate to a static method that is defined in a module of the assembly.</span></span>

<span data-ttu-id="db640-129">如果仅从该列表中的一个项存在的一种类型或程序集中的一个方法，则运行时无法卸载程序集。</span><span class="sxs-lookup"><span data-stu-id="db640-129">If only one item from this list exists for only one type or one method in the assembly, the runtime cannot unload the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="db640-130">列表中的所有项运行终结器之后，运行时才会实际卸载程序集。</span><span class="sxs-lookup"><span data-stu-id="db640-130">The runtime does not actually unload the assembly until finalizers have run for all items in the list.</span></span>

<span data-ttu-id="db640-131">为了跟踪生存期，构造的泛型类型如`List<int>`（在 C# 中) 或`List(Of Integer)`（在 Visual Basic 中)，是创建并用于生成可回收程序集被视为已定义程序集中，包含泛型类型定义或包含的类型自变量之一定义的程序集中。</span><span class="sxs-lookup"><span data-stu-id="db640-131">For purposes of tracking lifetime, a constructed generic type such as `List<int>` (in C#) or `List(Of Integer)` (in Visual Basic) that is created and used in the generation of a collectible assembly is considered to have been defined either in the assembly that contains the generic type definition or in an assembly that contains the definition of one of its type arguments.</span></span> <span data-ttu-id="db640-132">使用的确切程序集是实现详细信息和可能会发生变化。</span><span class="sxs-lookup"><span data-stu-id="db640-132">The exact assembly that is used is an implementation detail and subject to change.</span></span>
 
## <a name="restrictions-on-collectible-assemblies"></a><span data-ttu-id="db640-133">针对可回收程序集的限制</span><span class="sxs-lookup"><span data-stu-id="db640-133">Restrictions on collectible assemblies</span></span>

<span data-ttu-id="db640-134">以下限制适用于可回收程序集：</span><span class="sxs-lookup"><span data-stu-id="db640-134">The following restrictions apply to collectible assemblies:</span></span> 

- <span data-ttu-id="db640-135">**静态引用** </span><span class="sxs-lookup"><span data-stu-id="db640-135">**Static references** </span></span>  
  <span data-ttu-id="db640-136">普通的动态程序集中的类型不能具有对可回收程序集中定义的类型的静态引用。</span><span class="sxs-lookup"><span data-stu-id="db640-136">Types in an ordinary dynamic assembly cannot have static references to types that are defined in a collectible assembly.</span></span> <span data-ttu-id="db640-137">例如，如果你定义继承自可回收程序集中，类型的普通类型<xref:System.NotSupportedException>引发异常。</span><span class="sxs-lookup"><span data-stu-id="db640-137">For example, if you define an ordinary type that inherits from a type in a collectible assembly, a <xref:System.NotSupportedException> exception is thrown.</span></span> <span data-ttu-id="db640-138">可回收程序集中的类型中可以有对一种类型的静态引用另一个可回收程序集，但这将扩展引用的程序集引用的程序集的生存期的生存期。</span><span class="sxs-lookup"><span data-stu-id="db640-138">A type in a collectible assembly can have static references to a type in another collectible assembly, but this extends the lifetime of the referenced assembly to the lifetime of the referencing assembly.</span></span>

- <span data-ttu-id="db640-139">**COM 互操作** </span><span class="sxs-lookup"><span data-stu-id="db640-139">**COM interop** </span></span>  
   <span data-ttu-id="db640-140">任何 COM 接口可定义可回收程序集中，并且没有可回收程序集内的类型的实例可以转换为 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="db640-140">No COM interfaces can be defined within a collectible assembly, and no instances of types within a collectible assembly can be converted into COM objects.</span></span> <span data-ttu-id="db640-141">可回收程序集中的类型不能用作 COM 可调用包装 (CCW) 或运行时可调用包装 (RCW)。</span><span class="sxs-lookup"><span data-stu-id="db640-141">A type in a collectible assembly cannot serve as a COM callable wrapper (CCW) or runtime callable wrapper (RCW).</span></span> <span data-ttu-id="db640-142">但是，可回收程序集中的类型可以使用实现 COM 接口的对象。</span><span class="sxs-lookup"><span data-stu-id="db640-142">However, types in collectible assemblies can use objects that implement COM interfaces.</span></span>

- <span data-ttu-id="db640-143">**平台调用** </span><span class="sxs-lookup"><span data-stu-id="db640-143">**Platform invoke** </span></span>  
   <span data-ttu-id="db640-144">具有方法<xref:System.Runtime.InteropServices.DllImportAttribute>可回收程序集中进行声明时，将不会编译属性。</span><span class="sxs-lookup"><span data-stu-id="db640-144">Methods that have the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute will not compile when they are declared in a collectible assembly.</span></span> <span data-ttu-id="db640-145"><xref:System.Reflection.Emit.OpCodes.Calli?displayProperty=nameWithType>指令不能用在可回收程序集中，类型的实现中，此类类型不能封送到非托管代码。</span><span class="sxs-lookup"><span data-stu-id="db640-145">The <xref:System.Reflection.Emit.OpCodes.Calli?displayProperty=nameWithType> instruction cannot be used in the implementation of a type in a collectible assembly, and such types cannot be marshaled to unmanaged code.</span></span> <span data-ttu-id="db640-146">但是，你可以调入本机代码通过使用声明中的非可回收程序集的入口点。</span><span class="sxs-lookup"><span data-stu-id="db640-146">However, you can call into native code by using an entry point that is declared in a non-collectible assembly.</span></span>
 
- <span data-ttu-id="db640-147">**封送处理** </span><span class="sxs-lookup"><span data-stu-id="db640-147">**Marshaling** </span></span>  
   <span data-ttu-id="db640-148">不能封送可回收程序集中定义的对象 （以特定，委托）。</span><span class="sxs-lookup"><span data-stu-id="db640-148">Objects (in particular, delegates) that are defined in collectible assemblies cannot be marshaled.</span></span> <span data-ttu-id="db640-149">这是对所有暂时性发出类型的限制。</span><span class="sxs-lookup"><span data-stu-id="db640-149">This is a restriction on all transient emitted types.</span></span>

- <span data-ttu-id="db640-150">**程序集加载** </span><span class="sxs-lookup"><span data-stu-id="db640-150">**Assembly loading** </span></span>  
   <span data-ttu-id="db640-151">反射发出是用于加载可回收程序集支持的唯一机制。</span><span class="sxs-lookup"><span data-stu-id="db640-151">Reflection emit is the only mechanism that is supported for loading collectible assemblies.</span></span> <span data-ttu-id="db640-152">通过使用任何其他形式的程序集加载加载的程序集不能卸载。</span><span class="sxs-lookup"><span data-stu-id="db640-152">Assemblies that are loaded by using any other form of assembly loading cannot be unloaded.</span></span>
 
- <span data-ttu-id="db640-153">**绑定上下文的对象**  </span><span class="sxs-lookup"><span data-stu-id="db640-153">**Context-bound objects**  </span></span>  
   <span data-ttu-id="db640-154">不支持上下文静态变量。</span><span class="sxs-lookup"><span data-stu-id="db640-154">Context-static variables are not supported.</span></span> <span data-ttu-id="db640-155">可回收程序集中的类型不能扩展<xref:System.ContextBoundObject>。</span><span class="sxs-lookup"><span data-stu-id="db640-155">Types in a collectible assembly cannot extend <xref:System.ContextBoundObject>.</span></span> <span data-ttu-id="db640-156">但是，可回收程序集中的代码可以在其他位置使用定义的绑定上下文的对象。</span><span class="sxs-lookup"><span data-stu-id="db640-156">However, code in collectible assemblies can use context-bound objects that are defined elsewhere.</span></span>

- <span data-ttu-id="db640-157">**线程静态数据**     </span><span class="sxs-lookup"><span data-stu-id="db640-157">**Thread-static data**     </span></span>  
   <span data-ttu-id="db640-158">不支持线程静态变量。</span><span class="sxs-lookup"><span data-stu-id="db640-158">Thread-static variables are not supported.</span></span>

## <a name="see-also"></a><span data-ttu-id="db640-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="db640-159">See also</span></span>

[<span data-ttu-id="db640-160">发出动态方法和程序集</span><span class="sxs-lookup"><span data-stu-id="db640-160">Emitting Dynamic Methods and Assemblies</span></span>](emitting-dynamic-methods-and-assemblies.md)
