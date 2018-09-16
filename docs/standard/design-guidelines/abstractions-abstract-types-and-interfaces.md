---
title: 抽象（抽象类型和接口）
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ad8b2dd3dbf2a7a75c98a3115d4351dfea4e1a0
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45686019"
---
# <a name="abstractions-abstract-types-and-interfaces"></a>抽象（抽象类型和接口）
一种抽象是描述协定，但不提供完整的实现的协定的类型。 通常作为抽象类或接口，实现的抽象概念以及它们与一组定义完善的参考文档，描述所需的语义的实现的协定的类型。 一些.NET Framework 中最重要的抽象包括<xref:System.IO.Stream>， <xref:System.Collections.Generic.IEnumerable%601>，和<xref:System.Object>。  
  
 您可以通过实现支持一种抽象的协定的具体类型和使用框架 Api 使用 （操作系统上） 使用此具体类型来扩展框架的抽象。  
  
 一种有意义且有用的抽象，能够承受测试是时间的很难设计。 主要困难获取正确成员，没有更多并没有更少的集。 如果抽象具有太多的成员，将很难或几乎不可能实现。 如果是承诺的功能的成员太少，变得无用的许多有趣的情形。  
  
 框架中的太多抽象还产生负面影响的 framework 的可用性。 通常是很难理解抽象，无需了解它如何适用于具体的实现和对抽象操作的 Api 的更大的图片。 此外，抽象和其成员的名称是一定是抽象的这通常会使它们比较难懂且 unapproachable 而无需第一个了解其使用情况的更广泛的上下文。  
  
 但是，抽象提供非常强大的可扩展性的其他扩展性机制通常不能与匹配。 它们的许多体系结构模式，如插件，核心反转控制 (IoC)、 管道和等等。 它们也是非常重要的可测试性的框架。 很好的抽象，使得可以去掉用于单元测试的大量依赖关系。 总之，抽象是负责的现代面向对象的框架广受欢迎的丰富功能。  
  
 **X DO NOT** 提供抽象，除非它们通过开发几个具体实现和使用抽象的 Api 测试过。  
  
 **✓ DO** 设计抽象时，请仔细选择一个抽象类和接口之间。  
  
 **✓ CONSIDER** 提供抽象的具体实现的引用测试。 此类测试应允许用户以测试是否它们的实现正确地实现该协定。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
