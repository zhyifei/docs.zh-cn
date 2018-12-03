---
title: 相等运算符
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27550a8fd8292029cad9c2e699374a190b1a532e
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2018
ms.locfileid: "48839350"
---
# <a name="equality-operators"></a>相等运算符
本部分讨论了重载相等运算符，并将 `operator==` 和 `operator!=` 作为相等运算符。

**X 切忌** 重载相等运算符的其中一个而不重载另一个。  

**✓ 务必** 确保 <xref:System.Object.Equals%2A?displayProperty=nameWithType> 和相等运算符具有完全相同的语义和类似的性能特性。

这通常意味着重载相等运算符时 `Object.Equals` 也需要被重写。  

**X 避免** 相等运算符引发异常。
  
例如，如果其中一个参数为 null ，则返回 false ，而不是引发 `NullReferenceException`。  
  
## <a name="equality-operators-on-value-types"></a>值类型的相等运算符
**✓ 务必** 在值类型上重载相等运算符，如果相等是有意义的。

在大多数编程语言中，对于值类型没有 `operator==` 的默认实现。  
  
## <a name="equality-operators-on-reference-types"></a>引用类型的相等运算符
**X 避免** 在可变引用类型上重载相等运算符。

许多语言对引用类型都有内置的相等运算符。内置运算符通常实现引用相等性，当默认行为更改为值相等性时，许多开发人员都会感到意外。
  
对于不可变的引用类型，此问题不是很明显，因为不可变性使得更难以注意引用相等性和值相等性之间的差异。

**X 避免** 对引用类型重载相等运算符，如果实现可能会显著慢于引用相等性。

*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*

*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*

## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
