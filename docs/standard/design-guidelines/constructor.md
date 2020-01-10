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
ms.openlocfilehash: 823bc893c9384bb687e5f9a196abe497db14f4db
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709473"
---
# <a name="constructor-design"></a>构造函数设计

有两种类型的构造函数：类型构造函数和实例构造函数。

类型构造函数是静态的，在类型被使用前由 CLR 运行。 实例构造函数在创建类型的实例时运行。

类型构造函数不能接受任何参数。 实例构造函数可以。 不采用任何参数的实例构造函数通常称为无参数的构造函数。

构造函数是创建类型的实例的最自然方式。 构造函数是创建类型实例的最自然方式。大多数开发人员在考虑创建实例的替代方法（例如工厂方法）之前会搜索并尝试使用构造函数。

**✓ 考虑** 提供简单，理想情况下是默认值，构造函数。

简单的构造函数包含非常少的参数，所有参数均为基元或枚举。 此类简单构造函数会提高框架的可用性。

**✓ 考虑** 而不一个构造函数中使用的静态工厂方法，如果所需的操作的语义执行不直接映射到的新实例的构造，或遵循的构造函数设计准则是不合理。

**✓ 务必** 设置主属性构造函数参数用作快捷方式。

使用空的构造函数后跟某些属性集和使用具有多个参数的构造函数之间的语义不应存在任何差异。

**✓ 务必** 使用相同的名称用于构造函数参数和属性，如果使用构造函数参数只需设置属性。

此类参数和属性的唯一区别在于大小写形式。

**✓ DO** 构造函数中的最小工作。

除捕获构造函数参数外，构造函数不应执行太多工作。 任何其他处理的成本应延迟到必需的时间。

**✓ 务必** 根据引发从实例构造函数的异常。

如果需要此类构造函数， **✓**将在类中显式声明公共无参数的构造函数。

如果未显式声明类型上的任何构造函数，则许多语言（如C#）将自动添加一个公共的无参数构造函数。 （抽象类获取受保护的构造函数。）

向类添加参数化构造函数会阻止编译器添加无参数的构造函数。 这通常会导致意外的重大更改。

**X 避免**在结构上显式定义无参数的构造函数。

这样可以更快地创建数组，因为如果没有定义无参数的构造函数，则不必在数组中的每个槽上运行它。 请注意，许多编译器（ C#包括）不允许结构出于此原因而提供无参数的构造函数。

**X 避免** 调用其构造函数内的对象上的虚拟成员。

调用虚拟成员将导致调用最常派生的重写，即使派生程度最高的构造函数尚未完全运行也是如此。

## <a name="type-constructor-guidelines"></a>类型构造函数指南

**✓ DO** 将设为私有静态构造函数。

静态构造函数（也称为类构造函数）用于初始化类型。 CLR 在创建类型的第一个实例或调用该类型的任何静态成员之前调用静态构造函数。 用户无法控制何时调用静态构造函数。 如果静态构造函数不是私有的，则可以通过 CLR 以外的代码调用它。 根据构造函数中执行的操作，这可能会导致意外行为。 C# 编译器强制静态构造函数为私有。

**X DO NOT** 从静态构造函数引发异常。

如果从类型构造函数中引发异常，则该类型在当前应用程序域中不可用。

**✓ CONSIDER** 初始化以内的静态字段，而不用显式静态构造函数，由于运行时能够优化没有显式定义的静态构造函数的类型的性能。

*部分©2005，2009 Microsoft Corporation。保留所有权利。*

*在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。

## <a name="see-also"></a>另请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
