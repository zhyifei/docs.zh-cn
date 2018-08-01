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
ms.openlocfilehash: 5b1e5784de277d59c7bc945cbe7b605653eec7bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571012"
---
# <a name="equality-operators"></a>相等运算符
本部分讨论重载相等运算符并引用`operator==`和`operator!=`作为相等运算符。  
  
 **X DO NOT** 重载相等运算符和不在其他之一。  
  
 **✓ DO** 确保<xref:System.Object.Equals%2A?displayProperty=nameWithType>和相等运算符具有完全相同的语义和类似的性能特征。  
  
 这通常意味着`Object.Equals`需要时重载相等运算符时被重写。  
  
 **X AVOID** 相等运算符从引发异常。  
  
 例如，返回 false 如果的自变量之一为 null 而不是引发`NullReferenceException`。  
  
## <a name="equality-operators-on-value-types"></a>有关值类型的相等运算符  
 **✓ DO** 重载相等运算符的值类型，如果相等是有意义。  
  
 在大多数编程语言中，没有默认实现的`operator==`为值类型。  
  
## <a name="equality-operators-on-reference-types"></a>对引用类型的相等运算符  
 **X AVOID** 重载相等运算符对可变引用类型。  
  
 许多语言都有内置的相等运算符对于引用类型。 内置运算符通常实现引用相等性，并更改为值相等的默认行为时，许多开发人员感到惊奇多功能。  
  
 因为不可变性使困难得多，需要注意引用相等性和值相等性之间的差异，用于不可变的引用类型缓解此问题。  
  
 **X AVOID** 重载相等运算符对引用类型，如果实现可能会显著慢于引用相等性的。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
