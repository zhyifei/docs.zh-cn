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
  
 **请考虑 ✓**使用基于参数的含义，而不是参数的类型的名称。  
  
### <a name="naming-operator-overload-parameters"></a>命名运算符重载参数  
 **✓ 执行**使用`left`和`right`为二元运算符重载参数名称，如果没有给参数的类型没有意义。  
  
 **✓ 执行**使用`value`的一元运算符重载参数名称，如果没有给参数的类型没有意义。  
  
 **请考虑 ✓**有意义的名称，运算符的重载参数，如果这样做会增加巨大的价值。  
  
 **X 不**使用缩写或数值索引运算符重载参数名称。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
