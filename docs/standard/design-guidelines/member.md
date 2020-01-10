---
title: 成员设计准则
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], about member design guidelines
- members [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], members
- member design guidelines [.NET Framework]
ms.assetid: 0ce93180-1d7b-4f8c-9306-f828b2d66b8f
ms.openlocfilehash: cf4f1d2fee73e3e65dc4d92ea97a62f4a7e4c4e5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709265"
---
# <a name="member-design-guidelines"></a>成员设计准则
方法、属性、事件、构造函数和字段统称为成员。 框架功能最终以成员的方式向框架用户公开。  
  
 成员可以是虚拟的或非虚拟的，具体的或抽象的，静态的或实例的，并且可以具有多个不同的可访问范围。 这些多样性提供了令人难以置信的表现力，但同时也需要框架设计者小心处理。  
  
 本章提供了在设计任何类型的成员时应遵循的基本准则。  
  
## <a name="in-this-section"></a>本节内容  
 [成员重载](../../../docs/standard/design-guidelines/member-overloading.md)  
 [属性设计](../../../docs/standard/design-guidelines/property.md)  
 [构造函数设计](../../../docs/standard/design-guidelines/constructor.md)  
 [事件设计](../../../docs/standard/design-guidelines/event.md)  
 [字段设计](../../../docs/standard/design-guidelines/field.md)  
 [扩展方法](../../../docs/standard/design-guidelines/extension-methods.md)  
 [运算符重载](../../../docs/standard/design-guidelines/operator-overloads.md)  
 [参数设计](../../../docs/standard/design-guidelines/parameter-design.md)  
 *部分©2005，2009 Microsoft Corporation。保留所有权利。*  
  
 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。  
  
## <a name="see-also"></a>另请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
