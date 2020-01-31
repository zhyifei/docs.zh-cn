---
title: 같음 연산자
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
# <a name="equality-operators"></a>같음 연산자
本部分讨论了重载相等运算符并将 `operator==` 和 `operator!=` 引用为相等运算符。

 ❌ 不要重载某个相等运算符而不是另一个相等运算符。

 ✔️确保 <xref:System.Object.Equals%2A?displayProperty=nameWithType> 和相等运算符具有完全相同的语义和类似的性能特征。

 这通常意味着，在重载相等运算符时需要替代 `Object.Equals`。

 ❌ 避免从相等运算符引发异常。

 例如，如果其中一个参数为 null，则返回 false，而不是引发 `NullReferenceException`。

## <a name="equality-operators-on-value-types"></a>值类型的等式运算符
 ✔️如果相等性是有意义的，则对值类型重载相等运算符。

 在大多数编程语言中，值类型没有 `operator==` 的默认实现。

## <a name="equality-operators-on-reference-types"></a>引用类型的等式运算符
 ❌ 避免对可变引用类型重载相等运算符。

 许多语言都具有针对引用类型的内置等式运算符。 内置运算符通常实现引用等式，当默认行更改为值等式时，许多开发人员都会感到惊讶。

 对于不可变的引用类型来说，此问题可得到缓解，因为不可变性使得引用等式和值等式之间的区别更难以被注意到。

 如果实现的速度远远低于引用相等性，❌ 避免对引用类型重载相等运算符。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>另请参阅

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [사용 지침](../../../docs/standard/design-guidelines/usage-guidelines.md)
