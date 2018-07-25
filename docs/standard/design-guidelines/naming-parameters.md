---
title: 命名参数
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parameters, names
- names [.NET Framework], parameters
ms.assetid: ca3c956e-725a-441b-b4e3-eab5d472f41c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed6b96bb05c52de4bfd8b6ad6b972c9d22ca66da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570481"
---
# <a name="naming-parameters"></a>命名参数
超出可读性的明显原因，务必遵循参数名称的指南，因为在可视化设计工具提供了 Intellisense 和浏览功能的类时，参数将显示在文档和设计器。  
  
 **✓ 执行**参数名称中使用 camelcasing 大小写约定。  
  
 **✓ 执行**使用描述性的参数名称。  
  
 **✓ 考虑**使用基于参数含义而非参数类型的名称。  
  
### <a name="naming-operator-overload-parameters"></a>命名运算符重载参数  
 **✓ 务必执行**：如果参数没有意义，请为二元运算符重载参数名称使用 `left` 和 `right`。  
  
 **✓ 务必执行**：如果参数没有意义，请为一元运算符重载参数名称使用 `value`。  
  
 **✓ 考虑**为运算符重载参数使用有意义的名称（如果这样做很有用的话）。  
  
 **X 不要**在运算符重载参数名称中使用缩写形式或数值索引。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
