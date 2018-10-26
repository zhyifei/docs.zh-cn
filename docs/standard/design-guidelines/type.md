---
title: 类型设计准则
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a7fb9964d0e542c0937c55ae65bd88b3f7149fa8
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44187934"
---
# <a name="type-design-guidelines"></a>类型设计准则
 就 CLR 而言，它仅支持两种类型 — 引用类型和值类型。但出于探讨框架设计的目的，我们将类型划分为多个逻辑组，每种都有其特定的设计规范。  
  
 类是使用最普遍的引用类型。多数框架中的大部分引用类型都是类。类的广泛应用主要得益于其支持丰富的面向对象功能，以及普适性。基类和抽象类是具备扩展性的特殊逻辑组。

 接口也是一种类型。接口可以被引用类型和值类型实现，因此可以充当这两种类型多态层次结构的根。此外，接口也可用于模拟多个继承，而 CLR 本身并不支持该功能。
    
 结构是常见的值类型。结构应当用来定义类似于语言基元的小型简单类型。
   
 枚举是一种特殊的值类型，它适用于声明一组数量有限的值，例如一周七天的名称、控制台颜色等。
  
 静态类的作用是为静态成员提供容器。它们通常被用来为其他操作提供快捷方式。 
  
 委托、 异常、 属性、 数组和集合是适用于特定用途的特殊引用类型。关于这些类型的设计准则与使用情况将在本书其他章节中进行讨论。  
  
 **✓ 务必** 确保每个类型中的成员相互关联，而不仅仅是将不相关的功能集合在一起。  
  
## <a name="in-this-section"></a>本节内容  
 [在类和结构之间选择](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [抽象类设计](../../../docs/standard/design-guidelines/abstract-class.md)  
 [静态类设计](../../../docs/standard/design-guidelines/static-class.md)  
 [接口设计](../../../docs/standard/design-guidelines/interface.md)  
 [结构设计](../../../docs/standard/design-guidelines/struct.md)  
 [枚举设计](../../../docs/standard/design-guidelines/enum.md)  
 [嵌套类型](../../../docs/standard/design-guidelines/nested-types.md)  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
