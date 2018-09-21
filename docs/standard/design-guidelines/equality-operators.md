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
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46526481"
---
# <a name="equality-operators"></a>相等运算符
本部分讨论了重载相等运算符并引用`operator==`和`operator!=`作为相等运算符。  
  
 **X DO NOT** 重载相等运算符和不在其他之一。  
  
 **✓ DO** 确保<xref:System.Object.Equals%2A?displayProperty=nameWithType>和相等运算符具有完全相同的语义和类似的性能特征。  
  
 这通常意味着`Object.Equals`需要重写时重载相等运算符。  
  
 **X AVOID** 相等运算符从引发异常。  
  
 例如，如果返回 false 的参数之一为 null 而不是引发`NullReferenceException`。  
  
## <a name="equality-operators-on-value-types"></a>有关值类型的相等运算符  
 **✓ DO** 重载相等运算符的值类型，如果相等是有意义。  
  
 在大多数编程语言中，没有默认实现的`operator==`对于值类型。  
  
## <a name="equality-operators-on-reference-types"></a>对引用类型的相等运算符  
 **X AVOID** 重载相等运算符对可变引用类型。  
  
 许多语言具有引用类型的内置相等运算符。 内置运算符通常实现引用相等性，并默认行为更改为值相等性时，许多开发人员都很惊讶。  
  
 此问题得到缓解不可变的引用类型，因为不可变性，使得很难注意到引用相等性和值相等性之间的差异。  
  
 **X AVOID** 重载相等运算符对引用类型，如果实现可能会显著慢于引用相等性的。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
