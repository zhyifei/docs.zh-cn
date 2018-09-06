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
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "44036020"
---
# <a name="type-design-guidelines"></a>类型设计准则
从 CLR 角度来看，有只有两个类别的类型 — 引用类型和值类型，但为了框架设计有关的讨论，我们可以将类型划分为多个逻辑组，每个都有其自己特定的设计规则。  
  
 类是引用类型的一般情况。 它们构成了在框架的大多数类型的大容量。 类欠其受欢迎程度设置面向对象的所支持的功能的丰富和常规适用性。 基类和抽象类是与扩展相关的特殊逻辑分组。  
  
 接口是由引用类型和值类型可以实现的类型。 因此，它们可以充当多态的引用类型和值类型的层次结构的根。 此外，可以使用接口来模拟多个继承，不由 CLR 本机支持。  
  
 结构是值类型的一般情况下，且应将其保留对于小型的简单类型，类似于语言基元。  
  
 枚举都是用来定义的值，如一周、 控制台颜色和等等的天的短集的值类型的一种特殊情况。  
  
 静态类是用于容器的静态成员的类型。 它们通常用于提供其他操作的快捷方式。  
  
 委托、 异常、 属性、 数组和集合是适用于特定用途的引用类型的所有特殊情况下，在本书中其他位置讨论了为其设计和使用情况的指导原则。  
  
 **✓ DO** 确保每个类型定义完善的一组相关成员，而不仅仅是随机的不相关的功能集合。  
  
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
