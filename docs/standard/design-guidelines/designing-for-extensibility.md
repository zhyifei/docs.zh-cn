---
title: 扩展性设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c1690d0cdf1f57eaf0a794d6e71babfa4fa6425
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216436"
---
# <a name="designing-for-extensibility"></a>扩展性设计
设计一个框架的一个重要方面是确保仔细考虑框架的可扩展性。这要求您了解与各种可扩展性机制相关的成本和收益。本章可帮助您确定哪些可扩展性机制（子类、事件、虚拟成员、回调等）可以最好地满足框架的要求。
  
有许多方法可以在框架中实现可扩展性。它们的范围从功能不强但成本更低到功能强大但成本较高。对于任何给定的可扩展性要求，您应该选择满足要求的成本最低的可扩展性机制。请记住，以后通常可以添加更多的可扩展性，但是您永远无法在不引入破坏性变更的情况下将其删除。
  
## <a name="in-this-section"></a>本节内容  
 [未密封类](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [受保护的成员](../../../docs/standard/design-guidelines/protected-members.md)  
 [事件和回调](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [虚拟成员](../../../docs/standard/design-guidelines/virtual-members.md)  
 [抽象（抽象类型和接口）](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [用于实现抽象的基类](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [密封](../../../docs/standard/design-guidelines/sealing.md)  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
