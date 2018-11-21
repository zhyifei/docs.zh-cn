---
title: 构造函数设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- default constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ad920c8028b102a13fdfe928d21768538e25b0f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44180444"
---
# <a name="constructor-design"></a>构造函数设计
有两种类型的构造函数：类型构造函数和实例构造函数。
  
类型构造函数是静态的，在使用类型之前由 CLR 运行。实例构造函数在创建类型的实例时运行。
类型构造函数不能接受任何参数。实例构造函数可以。不接受任何参数的实例构造函数通常称为默认构造函数。
构造函数是创建类型实例的最自然方式。大多数开发人员在考虑创建实例的替代方法（例如工厂方法）之前会搜索并尝试使构造函数。

**✓ 考虑** 提供简单的，理想情况下是默认的构造函数。  
简单的构造函数具有极少的参数，并且所有参数都是基元或枚举。这种简单的构造函数增加了框架的可用性。

**✓ 考虑** 如果所需操作的语义不直接映射到新实例的构造过程，或感觉遵循构造函数设计指南不合理，则使用静态工厂法而不是构造函数。

**✓ 务必** 使用构造函数参数作为设置主要属性的快捷方式。
 使用空构造函数后跟一些属性设置集和使用带有多个参数的构造函数之间的语义应该没有区别。

**✓ 务必** 如果构造函数参数用于简单地设置属性，则对构造函数的参数和属性使用相同的名称。

这些参数和属性之间的唯一区别应该是大小写不同。  

**✓ 务必** 在构造函数中执行最少的工作。  

除了捕获构造函数参数之外，构造函数不应该做很多工作。任何其他处理的开销应该延迟到需要的时候。

**✓ 务必** 如果合适，从实例构造函数中引发异常。  

**✓ 务必** 在类中显式声明公共默认构造函数，如果这样的构造函数是必需的。

如果不显式类型上声明任何构造函数，许多语言 （如 C# 中) 将自动添加公共默认构造函数。 （抽象类获取受保护的构造数。）  如果不在类型上显式声明任何构造函数，则许多语言（例如 C# ）将自动添加公共默认构造函数。（抽象类会设置个受保护的构造函数。）

将参数化构造函数添加到类可防止编译器添加默认构造函数。这通常会导致意外的破坏性变化。

**X 避免** 在结构上显式定义默认构造函数。  
  
这使得数组创建速度更快，因为如果未定义默认构造函数，则不必在数组中的每个槽上运行它。请注意，由于这个原因，许多编译器，包括 C#，不允许结构具有无参数构造函数。
  
**X 避免** 调用其构造函数内的对象上的虚拟成员。  
  
调用虚拟成员将导致调用派生程度最高的重写，即使派生程度最高的类型的构造函数尚未完全运行。
  
### <a name="type-constructor-guidelines"></a>类型构造函数准则
**✓ 务必** 将静态构造函数设为私有。  

静态构造函数（也称为类构造函数）用于初始化类型。 CLR 在创建类型的第一个实例或调用该类型的任何静态成员之前调用静态构造函数。用户无法控制何时调用静态构造函数。如果静态构造函数不是私有的，则可以通过 CLR 以外的代码调用它。根据构造函数中执行的操作，这可能会导致意外行为。C# 编译器强制静态构造函数是私有的。
  
**X 切忌** 从静态构造函数中引发异常。  

如果从类型构造函数中引发异常，则该类型在当前应用程序域中不可用。
  
 **✓ 考虑** 初始化内联静态字段，而不是显式使用静态构造函数，因为运行时能够优化没有显示定义静态构造函数的类型的性能。
  
*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*
*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*
  
## <a name="see-also"></a>请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
