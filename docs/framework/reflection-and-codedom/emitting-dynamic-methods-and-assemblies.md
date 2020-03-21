---
title: 发出动态方法和程序集
ms.date: 08/30/2017
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
ms.openlocfilehash: fda5a20eb7798086ec10415889454b4a8beba5f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180530"
---
# <a name="emitting-dynamic-methods-and-assemblies"></a>发出动态方法和程序集

本节介绍 <xref:System.Reflection.Emit> 命名空间中的一组托管类型，它们允许编译器或工具在运行时发出元数据和 Microsoft 中间语言 (MSIL)，并在磁盘上生成可移植可执行 (PE) 文件（可选）。 脚本引擎和编译器是此命名空间的主要使用者。 在本节中，<xref:System.Reflection.Emit> 命名空间提供的功能被称为反射发出。  
  
反射发出具有以下功能：  
  
- 在运行时定义轻量全局方法（使用 <xref:System.Reflection.Emit.DynamicMethod> 类）并通过委托执行这些方法。  
  
- 在运行时定义程序集，然后运行程序集以及/或者将程序集保存到磁盘。  
  
- 在运行时定义程序集，运行程序集，然后卸载程序集并允许垃圾回收回收其资源。  
  
- 在运行时在新的程序集中定义模块，然后运行模块以及/或者将模块保存到磁盘。  
  
- 在运行时在模块中定义类型，创建这些类型的实例并调用其方法。  
  
- 为已定义模块定义可供工具（如调试器和代码探查器）使用的符号化信息。  
  
除了 <xref:System.Reflection.Emit> 命名空间中的托管类型，还有非托管元数据接口，非托管元数据接口在[元数据接口](../unmanaged-api/metadata/metadata-interfaces.md)参考文档中介绍。 托管的反射发出提供比非托管元数据接口更强的语义错误检查和更高级别的元数据抽象。  
  
元数据和 MSIL 的另一个有用资源是《公共语言基础结构 (CLI)》文档，尤其是“第二部分：元数据定义和语义”和“第三部分: CIL 指令集”。 这些文件可在[Ecma网站上](https://www.ecma-international.org/publications/standards/Ecma-335.htm)在线查阅。  
  
## <a name="in-this-section"></a>本节内容
  
[反射中的安全问题发出](security-issues-in-reflection-emit.md)  
介绍与使用反射发出创建动态程序集相关的安全问题。  

[如何：定义和执行动态方法](how-to-define-and-execute-dynamic-methods.md)演示如何执行一个简单的动态方法和绑定到类实例的动态方法。

[如何：定义具有反射发出的泛型类型](how-to-define-a-generic-type-with-reflection-emit.md)演示如何使用两个类型参数创建简单的泛型类型，如何对类型参数应用类、接口和特殊约束，以及如何创建使用类的类型参数作为参数类型和返回类型的成员。

[如何：定义具有反射发出的泛型方法](how-to-define-a-generic-method-with-reflection-emit.md)演示如何创建、发出和调用简单的泛型方法。

[动态类型生成可收集程序集](collectible-assemblies.md)引入可收集程序集，它们是动态程序集，无需卸载创建它们的应用程序域即可卸载。
  
## <a name="reference"></a>参考  

<xref:System.Reflection.Emit.OpCodes>  
编录可用于生成方法体的 MSIL 指令代码。  
  
<xref:System.Reflection.Emit>  
包含用于发出动态方法、程序集和类型的托管类。  
  
<xref:System.Type>  
介绍 <xref:System.Type> 类，该类代表托管反射和反射发出中的类型，它是使用这些技术的关键。  
  
<xref:System.Reflection>  
包含用于浏览元数据和托管代码的托管类。  
  
## <a name="related-sections"></a>相关章节  

[反射](reflection.md)  
说明如何浏览元数据和托管代码。  
  
[.NET 中的程序集](../../standard/assembly/index.md)  
概述 .NET 实现中的程序集。
