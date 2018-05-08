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
ms.openlocfilehash: af7511f4159fdbfe2d3f972dc927e9ee11fd586f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="type-design-guidelines"></a>类型设计准则
从 CLR 角度来看，有只有两种类型的类别 — 引用类型和值类型，但为了 framework 设计有关的讨论，我们可以将类型划分为多个逻辑组，每个都有其自己的特定设计规则。  
  
 类是引用类型的一般情况。 它们构成了大量的大部分框架中的类型。 类到它们支持面向对象的功能的设置的丰富和它们的常规适用性欠其受欢迎程度。 基类和抽象类是与扩展相关的特殊逻辑分组。  
  
 接口是由引用类型和值类型可以实现的类型。 因此，它们可以作为引用类型和值类型的多态层次结构的根。 此外，接口可以用于模拟本机不支持 CLR 的多个继承。  
  
 结构是值类型的一般情况下，且应保留对于小型，简单类型，类似于语言基元。  
  
 枚举是用来定义的值，如一周的控制台颜色，和等的天的短集的值类型的特殊情况。  
  
 静态类是用于适用于静态成员的容器的类型。 它们通常用于提供其他操作的快捷方式。  
  
 委托、 异常、 属性、 数组和集合是适用于特定用途的引用类型的所有特殊情况和本书中别处讨论的设计和使用情况的准则。  
  
 **✓ 执行**确保每个类型定义完善的一组相关成员，而不仅仅是随机的不相关的功能集合。  
  
## <a name="in-this-section"></a>本节内容  
 [在类和结构之间选择](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [抽象类设计](../../../docs/standard/design-guidelines/abstract-class.md)  
 [静态类设计](../../../docs/standard/design-guidelines/static-class.md)  
 [接口设计](../../../docs/standard/design-guidelines/interface.md)  
 [结构设计](../../../docs/standard/design-guidelines/struct.md)  
 [枚举设计](../../../docs/standard/design-guidelines/enum.md)  
 [嵌套类型](../../../docs/standard/design-guidelines/nested-types.md)  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)
