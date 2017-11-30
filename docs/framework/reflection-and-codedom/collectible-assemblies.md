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
# <a name="collectible-assemblies-for-dynamic-type-generation"></a>动态类型生成可回收程序集

*可回收程序集*可以无需卸载在其中创建它们的应用程序域中卸载的动态程序集。 可以回收可回收程序集和其包含的类型使用的所有托管和非托管内存。 从内部表中删除信息，如程序集名称。

若要启用卸载功能，使用<xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndCollect?displayProperty=nameWithType>标志时创建的动态程序集。 该程序集是暂时性 （即，不能保存），并受到中所述限制[可回收程序集的限制](#restrictions-on-collectible-assemblies)部分。 当你释放与程序集关联的所有对象，公共语言运行时 (CLR) 将自动卸载可回收程序集。 在所有其他方面，可回收程序集创建和使用其他动态程序集的方式相同。

## <a name="lifetime-of-collectible-assemblies"></a>可回收程序集的生存期

由其包含的类型和从这些类型创建的对象引用存在控制可回收程序集的生存期。 只要存在的一个或多个以下，公共语言运行时不会卸载程序集 (`T`是在程序集中定义的任何类型): 

- `T` 的一个实例。

- 数组的实例`T`。
 
- 具有泛型类型的实例`T`作为其类型自变量之一。 这包括的泛型集合`T`，即使该集合为空。

- 实例<xref:System.Type>或<xref:System.Reflection.Emit.TypeBuilder>表示`T`。 

   > [!IMPORTANT]
   > 表示程序集的部分的所有对象，你必须将其都释放。 <xref:System.Reflection.Emit.ModuleBuilder>定义`T`都会保留对引用<xref:System.Reflection.Emit.TypeBuilder>，和<xref:System.Reflection.Emit.AssemblyBuilder>对象保留对引用<xref:System.Reflection.Emit.ModuleBuilder>，因此必须释放对这些对象的引用。 甚至，如果存在<xref:System.Reflection.Emit.LocalBuilder>或<xref:System.Reflection.Emit.ILGenerator>在构造使用`T`会阻止卸载。

- 对的静态引用`T`通过另一种动态定义类型`T1`，通过执行代码是否仍然可以访问。 例如，`T1`可能派生自`T`，或`T`可能的方法中的参数的类型`T1`。
 
- A **ByRef**所属的静态字段`T`。

- A <xref:System.RuntimeTypeHandle>， <xref:System.RuntimeFieldHandle>，或<xref:System.RuntimeMethodHandle>，是指`T`或的某个组件的`T`。

- 实例的可能间接使用任何反射对象或直接访问<xref:System.Type>对象，表示`T`。 例如，<xref:System.Type>对象`T`可从其元素类型是数组类型获取`T`，或从泛型类型具有`T`作为类型参数。 

- 一种方法`M`的任何线程调用堆栈上其中`M`是一种方法`T`或模块级方法在程序集中定义。

- 程序集的模块中定义静态方法的委托。

如果仅从该列表中的一个项存在的一种类型或程序集中的一个方法，则运行时无法卸载程序集。

> [!NOTE]
> 列表中的所有项运行终结器之后，运行时才会实际卸载程序集。

为了跟踪生存期，构造的泛型类型如`List<int>`（在 C# 中) 或`List(Of Integer)`（在 Visual Basic 中)，是创建并用于生成可回收程序集被视为已定义程序集中，包含泛型类型定义或包含的类型自变量之一定义的程序集中。 使用的确切程序集是实现详细信息和可能会发生变化。
 
## <a name="restrictions-on-collectible-assemblies"></a>针对可回收程序集的限制

以下限制适用于可回收程序集： 

- **静态引用**   
  普通的动态程序集中的类型不能具有对可回收程序集中定义的类型的静态引用。 例如，如果你定义继承自可回收程序集中，类型的普通类型<xref:System.NotSupportedException>引发异常。 可回收程序集中的类型中可以有对一种类型的静态引用另一个可回收程序集，但这将扩展引用的程序集引用的程序集的生存期的生存期。

- **COM 互操作**   
   任何 COM 接口可定义可回收程序集中，并且没有可回收程序集内的类型的实例可以转换为 COM 对象。 可回收程序集中的类型不能用作 COM 可调用包装 (CCW) 或运行时可调用包装 (RCW)。 但是，可回收程序集中的类型可以使用实现 COM 接口的对象。

- **平台调用**   
   具有方法<xref:System.Runtime.InteropServices.DllImportAttribute>可回收程序集中进行声明时，将不会编译属性。 <xref:System.Reflection.Emit.OpCodes.Calli?displayProperty=nameWithType>指令不能用在可回收程序集中，类型的实现中，此类类型不能封送到非托管代码。 但是，你可以调入本机代码通过使用声明中的非可回收程序集的入口点。
 
- **封送处理**   
   不能封送可回收程序集中定义的对象 （以特定，委托）。 这是对所有暂时性发出类型的限制。

- **程序集加载**   
   反射发出是用于加载可回收程序集支持的唯一机制。 通过使用任何其他形式的程序集加载加载的程序集不能卸载。
 
- **绑定上下文的对象**    
   不支持上下文静态变量。 可回收程序集中的类型不能扩展<xref:System.ContextBoundObject>。 但是，可回收程序集中的代码可以在其他位置使用定义的绑定上下文的对象。

- **线程静态数据**       
   不支持线程静态变量。

## <a name="see-also"></a>请参阅

[发出动态方法和程序集](emitting-dynamic-methods-and-assemblies.md)
