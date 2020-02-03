---
title: 相等运算符
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
ms.openlocfilehash: 34fc8eef5270369419b76899f0dbe1ace106caf6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741704"
---
# <a name="equality-operators"></a>相等运算符
本节讨论重载相等运算符并将 `operator==` 和 `operator!=` 视为相等运算符。

 ❌ 不要重载某个相等运算符而不是另一个相等运算符。

 ✔️确保 <xref:System.Object.Equals%2A?displayProperty=nameWithType> 和相等运算符具有完全相同的语义和类似的性能特征。

 这通常意味着在重载相等运算符时需要重写 `Object.Equals`。

 ❌ 避免从相等运算符引发异常。

 例如，如果其中一个参数为 null，而不是引发 `NullReferenceException`，则返回 false。

## <a name="equality-operators-on-value-types"></a>值类型的等式运算符
 ✔️如果相等性是有意义的，则对值类型重载相等运算符。

 在大多数编程语言中，值类型没有 `operator==` 的默认实现。

## <a name="equality-operators-on-reference-types"></a>引用类型的等式运算符
 ❌ 避免对可变引用类型重载相等运算符。

 许多语言都具有针对引用类型的内置等式运算符。 内置运算符通常实现引用等式，当默认行更改为值等式时，许多开发人员都会感到惊讶。

 对于不可变的引用类型来说，此问题可得到缓解，因为不可变性使得引用等式和值等式之间的区别更难以被注意到。

 如果实现的速度远远低于引用相等性，❌ 避免对引用类型重载相等运算符。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。

## <a name="see-also"></a>另请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
- [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
