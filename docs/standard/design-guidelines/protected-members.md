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
ms.openlocfilehash: 4574dffc3f9dd1b60d655bfde33a4ddc1a81d350
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44068971"
---
# <a name="protected-members"></a>受保护的成员
受保护的成员本身不提供任何可扩展性，但它们会使通过子类化可扩展性功能更强大。 它们可以用于公开高级自定义选项，而不必要地复杂化的主要公共接口。  
  
 框架设计器需要要小心使用受保护的成员，因为"保护"的名称可以提供安全的错觉。 任何人都能够子类未密封的类并访问受保护成员和公共成员使用的防御性编码做法适用于受保护的成员的因此完全相同。  
  
 **✓ CONSIDER** 使用受保护的高级自定义的成员。  
  
 **✓ DO** 处理未密封类作为公共以便进行安全、 文档和兼容性分析中的受保护的成员。  
  
 任何人都可以从类继承，并且可以访问受保护的成员。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
