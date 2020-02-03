---
title: 扩展方法
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
ms.openlocfilehash: 13f92470b23d138e0d30bed947ff1932f2605d28
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741619"
---
# <a name="extension-methods"></a>扩展方法
扩展方法是一种语言特性，允许使用实例方法调用语法来调用静态方法。 这些方法必须至少使用一个参数，该参数表示方法要操作的实例。

 定义此类扩展方法的类称“sponsor”类，必须将其声明为静态。 要使用扩展方法，必须导入定义 sponsor 类的命名空间。

 ❌ 避免 frivolously 定义扩展方法，特别是对于不属于您的类型。

 如果拥有某一类型的源代码，请考虑使用常规实例方法。 如果没有，并且想要添加方法，请务必小心。 随意使用扩展方法可能会使本来不具备这些方法的类型产生混乱的API。

 ✔️考虑在以下任何情况下使用扩展方法：

- 提供与接口的每个实现相关的辅助功能（如果上述功能可以根据核心接口编写）。 这是因为不能将具体实现分配给接口。 例如，`LINQ to Objects` 运算符作为所有 <xref:System.Collections.Generic.IEnumerable%601> 类型的扩展方法实现。 因此，任何 `IEnumerable<>` 实现都会自动启用 LINQ。

- 当实例方法在某种类型上引入依赖关系，但这样的依赖关系会破坏依赖关系管理规则的时候。 例如，从 <xref:System.String> 到 <xref:System.Uri?displayProperty=nameWithType> 的依赖关系可能并不理想，因此，从依赖关系管理的角度来看，返回 `System.Uri` 的 `String.ToUri()` 实例方法将是错误的设计。 静态扩展方法 `Uri.ToUri(this string str)` 返回 `System.Uri` 将是更好的设计。

 ❌ 避免在 <xref:System.Object?displayProperty=nameWithType>上定义扩展方法。

 Visual Basic 用户将无法使用扩展方法语法对对象引用调用此类方法。 Visual Basic 不支持调用此类方法，因为在 Visual Basic 中，将引用声明为对象将强制其上的所有方法调用都是后期绑定的（在运行时确定调用的实际成员），而扩展方法的绑定则在编译时（早期绑定）。

 请注意，该准则适用于存在相同绑定行为的其他语言，或者不支持扩展方法的其他语言。

 ❌ 不要将扩展方法放在与扩展类型相同的命名空间中，除非它用于向接口添加方法或用于依赖项管理。

 ❌ 避免定义具有相同签名的两个或多个扩展方法，即使它们驻留在不同的命名空间中。

 如果类型是一个接口，则✔️考虑在与扩展类型相同的命名空间中定义扩展方法，并且在大多数或所有情况下都使用扩展方法。

 ❌ 不会定义实现通常与其他功能关联的命名空间中的功能的扩展方法。 而是在与它们所属的功能相关联的命名空间中定义它们。

 ❌ 避免命名空间专用于扩展方法（例如 "Extension"）的命名空间。 而是使用描述性名称（例如，“路由”）。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。

## <a name="see-also"></a>另请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
