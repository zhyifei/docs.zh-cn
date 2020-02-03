---
title: 结构设计
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
ms.openlocfilehash: b6d06bc8a1e8535f1452af0726138abaebfd4951
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743613"
---
# <a name="struct-design"></a>结构设计
一般用途值类型最常称为结构，即其C#关键字。 本部分提供常规结构设计的准则。

 ❌ 不为结构提供无参数的构造函数。

 遵循此原则将允许创建结构数组，而无需对数组的每个项运行构造函数。 请注意C# ，不允许结构具有无参数的构造函数。

 ❌ 不要定义可变值类型。

 可变值类型有几个问题。 例如，当属性 getter 返回值类型时，调用者会收到一个副本。 由于该副本是隐式创建的，因此开发人员可能不会意识到他们正在改变副本，而不是原始值。 此外，某些语言（尤其是动态语言）在使用可变值类型时会遇到问题，因为即使局部变量在解除引用时也会导致生成副本。

 ✔️确保将所有实例数据设置为零、false 或 null （适当时）的状态有效。

 这可以防止在创建结构数组时意外创建无效实例。

 ✔️在值类型上实现 <xref:System.IEquatable%601>。

 值类型上的 <xref:System.Object.Equals%2A?displayProperty=nameWithType> 方法会导致装箱，其默认实现不太有效，因为它使用反射。 <xref:System.IEquatable%601.Equals%2A> 可以具有更好的性能，并且可以实现，以便它不会导致装箱。

 ❌ 不会显式扩展 <xref:System.ValueType>。 实际上，大多数语言禁止此行为。

 一般情况下，结构可能非常有用，但应仅用于不经常装箱的单个不可变的小值。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。

## <a name="see-also"></a>另请参阅

- [类型设计准则](../../../docs/standard/design-guidelines/type.md)
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
- [在类和结构之间选择](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
