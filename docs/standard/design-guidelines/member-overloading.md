---
title: 成员重载
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
ms.openlocfilehash: c9cb178e838aab99c22089b527a6bd2e86b325de
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727836"
---
# <a name="member-overloading"></a>成员重载
成员重载意味着在同一类型上创建两个或多个成员，这些成员仅在参数的数量或类型中不同，但具有相同的名称。 例如，在下面的中，将重载 `WriteLine` 方法：

```csharp
public static class Console {
    public void WriteLine();
    public void WriteLine(string value);
    public void WriteLine(bool value);
    ...
}
```

 由于只有方法、构造函数和索引属性可以有参数，因此只能重载这些成员。

 重载是提高可重用库的可用性、生产力和可读性的最重要方法之一。 参数数量重载使您可以提供更简单的构造函数和方法版本。 使用参数类型的重载，可以为在所选的不同类型集上执行相同操作的成员使用相同的成员名称。

 ✔️尝试使用描述性参数名称来指示较短重载使用的默认值。

 ❌ 避免在重载中随意改变参数名称。 如果一个重载中的参数表示与另一个重载中的参数相同的输入，则这些参数应具有相同的名称。

 ❌ 避免在重载成员中参数顺序不一致。 具有相同名称的参数应出现在所有重载的同一位置。

 ✔️仅使最长重载虚拟（如果需要可扩展性）。 更短的重载只需调用更长的重载。

 ❌ 不要使用 `ref` 或 `out` 修饰符重载成员。

 某些语言无法解析对重载的调用。 此外，此类重载通常具有完全不同的语义，但可能不应作为重载，而是使用两种不同的方法。

 ❌ 没有重载的参数的位置和类型相同，但语义不同。

 ✔️允许为可选参数传递 `null`。

 ✔️确实使用成员重载，而不是使用默认参数定义成员。

 默认参数不符合 CLS。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。

## <a name="see-also"></a>另请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
