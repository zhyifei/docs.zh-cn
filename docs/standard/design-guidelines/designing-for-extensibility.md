---
title: 扩展性设计
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
ms.openlocfilehash: cd5db2d1e299df1b3d0f706ebc507e6855b72505
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709460"
---
# <a name="designing-for-extensibility"></a>扩展性设计
设计一个框架的一个重要方面是确保仔细考虑框架的可扩展性。 这要求你了解与各种可扩展性机制相关的成本和收益。 本章可帮助你确定哪些可扩展性机制（子类、事件、虚拟成员、回调等）可以最好地满足框架的要求。  
  
 有许多方法可以在框架中实现可扩展性。 有些方法功能不强但成本较低，有些方法功能强大但成本较高。 对于任何给定的可扩展性要求，应该选择满足要求的成本最低的可扩展性机制。 请记住，通常可以在以后添加更多的可扩展性，但不能在不引入中断性变更的情况下将其删除。  
  
## <a name="in-this-section"></a>本节内容  
 [未密封类](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [受保护的成员](../../../docs/standard/design-guidelines/protected-members.md)  
 [事件和回调](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [虚拟成员](../../../docs/standard/design-guidelines/virtual-members.md)  
 [抽象（抽象类型和接口）](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [用于实现抽象的基类](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [密封](../../../docs/standard/design-guidelines/sealing.md)  
 *部分©2005，2009 Microsoft Corporation。保留所有权利。*  
  
 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。  
  
## <a name="see-also"></a>另请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
