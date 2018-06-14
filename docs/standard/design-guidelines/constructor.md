---
title: 构造函数设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- default constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d7ca279dc1626cd526910af93326280bcd8301d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575552"
---
# <a name="constructor-design"></a>构造函数设计
有两种类型的构造函数： 键入构造函数和实例构造函数。  
  
 类型构造函数是静态的它们由 CLR 之前使用的类型。 创建类型的实例时，将运行实例构造函数。  
  
 类型构造函数不能接受任何参数。 实例构造函数可以。 不采用任何参数的实例构造函数通常称为默认构造函数。  
  
 构造函数是创建类型的实例的最简单方法。 大多数开发人员将搜索，并尝试使用构造函数之前他们考虑备选方法创建 （如工厂方法） 的实例。  
  
 **请考虑 ✓**提供简单，理想情况下是默认值，构造函数。  
  
 简单的构造函数具有极小的数字的参数，和所有参数都是基元或枚举。 此类简单的构造函数提高可用性的框架。  
  
 **请考虑 ✓**而不一个构造函数中使用的静态工厂方法，如果所需的操作的语义执行不直接映射到的新实例的构造，或遵循的构造函数设计准则是不合理。  
  
 **✓ 执行**设置主属性构造函数参数用作快捷方式。  
  
 应在语义方面之间没有差异使用跟某些属性集的空构造函数和使用具有多个自变量的构造函数。  
  
 **✓ 执行**使用相同的名称用于构造函数参数和属性，如果使用构造函数参数只需设置属性。  
  
 此类参数和属性的唯一区别应大小写不同。  
  
 **✓ 执行**构造函数中的最小工作。  
  
 构造函数不应执行极大的工作以外捕获构造函数参数。 所需之前，应延迟的成本的其他任何处理。  
  
 **✓ 执行**根据引发从实例构造函数的异常。  
  
 **✓ 执行**显式声明在类中，公共默认构造函数，如果这样的构造函数是必需的。  
  
 如果你不显式声明任何构造函数，在类型上，许多语言 （如 C# 中) 将会自动添加公共默认构造函数。 （抽象类获取受保护的构造函数。）  
  
 向类中添加参数化构造函数可阻止编译器添加默认构造函数。 这通常会导致意外的重大更改。  
  
 **请避免 x**显式在结构上定义默认的构造函数。  
  
 这使数组创建速度更快，因为如果未定义默认构造函数，它没有在数组中每个插槽上运行。 请注意，许多编译器，包括 C# 中，不允许为此具有无参数构造函数的结构。  
  
 **请避免 x**调用其构造函数内的对象上的虚拟成员。  
  
 调用的虚拟成员将导致派生程度最高的替代，用于调用，即使派生程度最高的类型的构造函数已完全尚未运行。  
  
### <a name="type-constructor-guidelines"></a>类型构造函数准则  
 **✓ 执行**将设为私有静态构造函数。  
  
 静态构造函数，也称为类构造函数，用于初始化类型。 CLR 创建的第一个实例的类型或调用该类型上的任何静态成员之前调用静态构造函数。 用户具有无法控制当调用该静态构造函数。 如果静态构造函数不是私有的则可以调用 CLR 以外的代码。 根据构造函数中执行的操作，这可能导致意外的行为。 C# 编译器强制静态构造函数来为私有构造函数。  
  
 **X 不**从静态构造函数引发异常。  
  
 如果从类型构造函数引发异常，类型不适合于当前的应用程序域中。  
  
 **请考虑 ✓**初始化以内的静态字段，而不用显式静态构造函数，由于运行时能够优化没有显式定义的静态构造函数的类型的性能。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)
