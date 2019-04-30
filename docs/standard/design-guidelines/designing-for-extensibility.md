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
author: KrzysztofCwalina
ms.openlocfilehash: 94900dee72230a1b9d099d78168acc508af62af7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026453"
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
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
