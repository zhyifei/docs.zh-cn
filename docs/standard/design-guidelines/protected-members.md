---
title: 受保护的成员
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: KrzysztofCwalina
ms.openlocfilehash: f0ad21f0a5b869332223d96991dd0a7bebeba420
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149349"
---
# <a name="protected-members"></a>受保护的成员
受保护的成员本身不提供任何可扩展性，但它们会使通过子类化可扩展性功能更强大。 它们可以用于公开高级自定义选项，而不必要地复杂化的主要公共接口。  
  
 框架设计器需要要小心使用受保护的成员，因为"保护"的名称可以提供安全的错觉。 任何人都能够子类未密封的类并访问受保护成员和公共成员使用的防御性编码做法适用于受保护的成员的因此完全相同。  
  
 **✓ CONSIDER** 使用受保护的高级自定义的成员。  
  
 **✓ DO** 处理未密封类作为公共以便进行安全、 文档和兼容性分析中的受保护的成员。  
  
 任何人都可以从类继承，并且可以访问受保护的成员。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
