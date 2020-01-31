---
title: 추상화(추상 형식 및 인터페이스)
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
ms.openlocfilehash: 6a4f511af72aad916d367153090504e2a8e11cb8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741813"
---
# <a name="abstractions-abstract-types-and-interfaces"></a>추상화(추상 형식 및 인터페이스)
抽象是一种描述协定但不提供协定的完整实现的类型。 抽象通常作为抽象类或接口实现，并带有一组明确定义的参考文档，该文档描述实现协定的类型的所需语义。 .NET Framework 中一些最重要的抽象包括 <xref:System.IO.Stream>、<xref:System.Collections.Generic.IEnumerable%601> 和 <xref:System.Object>。

 可以扩展框架，方法是：先实现一个支持抽象协定的具体类型，然后将该具体类型与使用（操作）该抽象的框架 API 配合使用。

 能够经得起时间考验的有意义且有用的抽象很难设计。 主要的困难是设置合适的成员，不能多也不能少。 如果抽象具有太多成员，将很难或几乎不可能实现。 如果承诺功能的成员太少，那么在很多重要的场景中它就变得毫无用处。

 框架中太多的抽象也会对框架的可用性产生负面影响。 如果不理解抽象如何适应具体实现和抽象 API 操作的全局，通常很难理解抽象。 此外，抽象的名称及其成员必然是抽象的，如果没有首先理解其使用的更广泛的背景，它们常常会变得更晦涩难懂。

 但是，抽象提供了非常强大的可扩展性，其他可扩展性机制通常无法与其匹敌。 它们是许多架构模式（例如插件、控制反转 (IoC)、管道等）的核心。 它们对于框架的可测试性也非常重要。 良好的抽象能够为单元测试消除严重的依赖。 总之，抽象让现代的面向对象的框架具有更受欢迎的丰富内涵。

 ❌ 不要提供抽象，除非通过开发一些具体的实现和使用抽象的 Api 来对它们进行测试。

 ✔️在设计抽象类和接口时，请仔细选择抽象类和接口。

 ✔️考虑为抽象的具体实现提供引用测试。 此类测试应允许用户测试其实现是否正确实现了协定。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>另请参阅

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [확장성을 위한 디자인](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
