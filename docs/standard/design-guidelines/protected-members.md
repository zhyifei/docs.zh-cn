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
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44199734"
---
# <a name="protected-members"></a>受保护的成员
受保护的成员本身不提供任何可扩展性，但它们可以通过子类化使可扩展性更强大。它们可用于公开高级自定义选项，而不会毫无必要地使主公共接口复杂化。

框架设计者需要小心使用受保护的成员，因为“受保护”一词会给人一种虚假的安全感。任何人都能够对未密封的类进行子类化并访问受保护的成员，因此所有用于公共成员的防御性编码实践都适用于受保护的成员。

**✓ 考虑** 使用受保护的成员进行高级自定义。

**✓ 务必** 为了安全、文档记录和兼容性分析目的，将未密封类中的受保护成员视为公共成员。

任何人都可以从类继承并访问受保护的成员。

* 部分版权 © 2005，2009 Microsoft Corporation。保留所有权利。* 

* 经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
