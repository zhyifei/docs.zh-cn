---
title: 构造函数设计
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- parameterless constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
ms.openlocfilehash: 7ab795cd4c6e0ff5e1451c05987848c41bd69577
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401243"
---
# <a name="constructor-design"></a>构造函数设计

有两种构造函数：类型构造函数和实例构造函数。

类型构造函数是静态的，在使用类型之前由 CLR 运行。 实例构造函数在创建类型的实例时运行。

类型构造函数不能采用任何参数。 实例构造函数可以。 不采用任何参数的实例构造函数通常称为无参数构造函数。

构造函数是创建类型实例的最自然方法。 大多数开发人员在考虑创建实例（如工厂方法）的替代方法之前，将搜索并尝试使用构造函数。

✔️ 考虑提供简单、理想的默认构造函数。

简单的构造函数具有非常少量的参数，并且所有参数都是基元或枚举。 这种简单的构造函数提高了框架的可用性。

✔️如果所需操作的语义不直接映射到新实例的构造，或者遵循构造函数设计准则感觉不自然，则考虑使用静态工厂方法而不是构造函数。

✔️ DO 使用构造函数参数作为设置主属性的快捷方式。

在语义上，使用空构造函数后跟某些属性集和使用具有多个参数的构造函数之间应该没有区别。

如果构造函数参数用于简单地设置属性，则✔️ DO 对构造函数参数使用相同的名称和属性。

此类参数和属性之间的唯一区别应该是套管。

✔️在构造函数中执行最小工作。

除了捕获构造函数参数之外，构造函数不应执行太多工作。 任何其他处理的成本应延迟到需要。

✔️如果适用，从实例构造函数引发异常。

✔️如果需要这样的构造函数，则在类中显式声明公共无参数构造函数。

如果不显式声明类型上的任何构造函数，则许多语言（如 C#）将自动添加公共无参数构造函数。 （抽象类获取受保护的构造函数。

向类添加参数化构造函数可防止编译器添加无参数构造函数。 这通常会导致意外的中断更改。

❌AVOID 在结构上显式定义无参数构造函数。

这使得数组创建速度更快，因为如果未定义无参数构造函数，则不必在数组中的每个插槽上运行。 请注意，许多编译器（包括 C#）不允许结构具有无参数构造函数。因此。

❌AVOID 在其构造函数内的对象上调用虚拟成员。

调用虚拟成员将导致调用最派生的重写，即使最派生类型的构造函数尚未完全运行。

## <a name="type-constructor-guidelines"></a>类型构造函数指南

✔️将静态构造函数作为私有。

静态构造函数（也称为类构造函数）用于初始化类型。 CLR 在创建类型的第一个实例或调用该类型上的任何静态成员之前调用静态构造函数。 用户无法控制何时调用静态构造函数。 如果静态构造函数不是私有的，则可以由 CLR 以外的代码调用它。 根据构造函数中执行的操作，这可能导致意外行为。 C# 编译器强制静态构造函数为私有。

❌不要从静态构造函数引发异常。

如果从类型构造函数引发异常，则该类型在当前应用程序域中不可用。

✔️考虑内联初始化静态字段，而不是显式使用静态构造函数，因为运行时能够优化没有显式定义的静态构造函数的类型的性能。

*部分© 2005， 2009 微软公司.保留所有权利。*

*经 Pearson 教育公司许可，从[框架设计指南：可重用的约定、习语和模式 .NET 库重新打印，第二版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)由 Krzysztof Cwalina 和 Brad Abrams 出版，由艾迪森-韦斯利专业公司作为微软 Windows 开发系列的一部分于 2008 年 10 月 22 日出版。*

## <a name="see-also"></a>另请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)
- [框架设计准则](../../../docs/standard/design-guidelines/index.md)
