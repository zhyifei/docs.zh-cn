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
除了明显的可读性的原因之外，遵循参数名称的准则非常重要，因为当可视化设计工具提供智能感知和类浏览功能时，参数会显示在文档和设计器中。
  
 **✓ 要**参数名称中使用 camelCasing。  
  
 **✓ 要**使用描述性的参数名称。  
  
 **✓ 考虑**使用基于参数含义的名称，而不是参数类型的名称。  
  
### <a name="naming-operator-overload-parameters"></a>命名运算符重载参数  
 **✓ 要**如果参数没有意义，请对`left`和`right`使用二进制运算符重载参数名称。  
  
 **✓ 要**如果参数没有意义，请将`value`用于一元运算符重载参数名称。
  
 **✓ 考虑**为运算符的重载参数使用有意义的名称，如果这样做会很有意义。  
  
 **X 不要**对运算符重载参数名称使用缩写或数字索引。
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*
  
 *由 Pearson Education, Inc 许可，转载自[Framework 设计准则： 可重用.NET 库的约定、 惯用法和模式 第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者 Krzysztof Cwalina 和 Brad Abrams，由Addison Wesley Professional 于 2008 年 10 月 22 日发布，作为 Microsoft Windows 开发系列的一部分。
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
