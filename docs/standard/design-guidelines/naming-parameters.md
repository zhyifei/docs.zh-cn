---
title: 命名参数
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
author: KrzysztofCwalina
ms.openlocfilehash: 35965f03f5c50cbe3ffcc9bdb615d99c50fc30a2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53147906"
---
# <a name="naming-parameters"></a>命名参数
除了提升可读性这一明显目的外，遵循参数名称准则的一个重要原因是文档和设计器（可视化设计工具在提供 Intellisense 和类浏览功能时）中会显示参数。
  
  
 **✓ 务必** 在参数名称中使用 camelCasing。  
  
 **✓ 务必** 使用描述性参数名称。  
  
 **✓ 考虑** 使用基于参数含义而非参数类型的名称。  
  
### <a name="naming-operator-overload-parameters"></a>命名运算符重载参数  
 **✓ 务必执行** ：如果参数没有意义，请为二元运算符重载参数名称使用 `left` 和 `right`。  
  
 **✓ 务必执行** ：如果参数没有意义，请为一元运算符重载参数名称使用 `value`。  
  
 **✓ 考虑** 为运算符重载参数使用有意义的名称（如果这样做很有用的话）。  
  
 **X DO NOT要** 在运算符重载参数名称中使用缩写形式或数值索引。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
