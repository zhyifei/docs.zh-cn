---
title: 抽象类设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5b9dacc4995a126e1ee3f6062dca796194d4882
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44178622"
---
# <a name="abstract-class-design"></a>抽象类设计
**X DO NOT** 在抽象类型中定义公共或受保护内部构造函数。  
  
 构造函数应为公共，仅当用户将需要创建该类型的实例。 因为不能创建抽象类型的实例，具有公共构造函数的抽象类型不正确是设计并具有误导性的用户。  
  
 **✓ DO** 在抽象类中定义为受保护或内部构造函数。  
  
 受保护的构造函数，则更容易，并只是允许基类以创建子类型时进行其自己的初始化。  
  
 内部构造函数可以用于限制对程序集定义的类的抽象类的具体实现。  
  
 **✓ DO** 提供至少一个继承自每个抽象类，要交付的具体类型。  
  
 这些措施可帮助验证抽象类的设计。 例如，<xref:System.IO.FileStream?displayProperty=nameWithType>是一种实现的<xref:System.IO.Stream?displayProperty=nameWithType>抽象类。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [类型设计准则](../../../docs/standard/design-guidelines/type.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
