---
title: 受保护的成员
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d4d334d9809f374442e19807d3b249a17a1d9df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571073"
---
# <a name="protected-members"></a>受保护的成员
受保护的成员本身不提供任何可扩展性，但它们可以使通过子类化的扩展性功能更强大。 它们可以用于公开高级自定义选项，而不必要地并发的主要公共接口。  
  
 请小心使用受保护的成员，因为"保护"的名称可以提供安全的 false 意义上所需要的 framework 设计器。 任何人都可以为子类未密封的类和访问受保护成员，以及用于公共成员的防御性编码做法适用于受保护的成员的因此完全相同。  
  
 **✓ CONSIDER**使用受保护的高级自定义的成员。  
  
 **✓ DO**处理未密封类作为公共以便进行安全、 文档和兼容性分析中的受保护的成员。  
  
 任何人都可以从类继承，并且可以访问受保护的成员。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
