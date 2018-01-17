---
title: "抽象（抽象类型和接口）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 276c5883487d8fba47d7fb80060d4c947e0f6cd6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="abstractions-abstract-types-and-interfaces"></a>抽象（抽象类型和接口）
一种抽象是描述的协定，但不提供完整实现的协定的类型。 通常作为抽象类或接口，实现的抽象，而且随附一组明确定义的参考文档描述实现协定的类型所需的语义。 .NET Framework 中最重要的抽象的一些包括<xref:System.IO.Stream>， <xref:System.Collections.Generic.IEnumerable%601>，和<xref:System.Object>。  
  
 你可以通过实现支持协定的抽象的具体类型并使用此具体类型 framework Api 使用 （操作系统上） 来扩展框架的抽象。  
  
 能够承受测试有意义且有用抽象是时间的很难设计的。 主要困难获取正确的一组成员，没有更多和不较少。 如果一种抽象具有太多的成员，则它将成为难或甚至无法实现。 如果已承诺的功能的成员太少，则将没有用处，在许多有趣的方案。  
  
 框架中的太多抽象还造成负面影响的 framework 的可用性。 它通常是很难了解一种抽象，而不了解它如何适用于具体的实现和抽象在操作的 Api 的较大的图片。 此外，抽象和其成员的名称是一定抽象，这通常使得它们含义隐晦、 unapproachable 而不了解其使用情况的更广泛上下文第一个。  
  
 但是，抽象提供的其他扩展性机制通常不能与匹配的功能非常强大扩展性。 它们的许多体系结构模式，如插件的核心是反向的控件 (IoC)、 管道，依次类推。 它们也是非常重要的框架可测试性。 良好的抽象，使能够出繁重的依赖关系，用于单元测试存根。 总之，抽象是负责广受欢迎的丰富功能，现代的面向对象的框架。  
  
 **X 不**提供抽象，除非它们通过开发几个具体实现和使用抽象的 Api 测试过。  
  
 **✓ 执行**设计抽象时，请仔细选择一个抽象类和接口之间。  
  
 **请考虑 ✓**提供抽象的具体实现的引用测试。 此类测试应允许用户以测试是否其实现正确实现协定。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
