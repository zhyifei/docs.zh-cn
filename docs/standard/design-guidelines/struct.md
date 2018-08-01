---
title: 结构设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2621aa96cf89b453d5faec3357d0890ca36251d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572731"
---
# <a name="struct-design"></a>结构设计
通用值类型最常称为结构，其 C# 关键字。 本部分提供常规结构设计的准则。  
  
 **X DO NOT** 结构提供默认构造函数。  
  
 遵循这一准则允许的结构而无需在该数组的每个项上运行构造函数创建的数组。 请注意，C# 不允许结构拥有默认构造函数。  
  
 **X DO NOT** 定义可变值类型。  
  
 可变值类型具有几个问题。 例如，当属性 getter 返回值类型时，调用方将收到副本。 隐式创建的副本，因为开发人员可能不知道它们变异副本，而不是原始值。 此外，某些语言 （尤其是动态语言） 有问题使用可变值类型，因为即使本地变量，取消引用时，会导致副本进行。  
  
 **✓ DO** 确保其中所有实例数据的状态设置为零，false，或 null （根据需要） 是否有效。  
  
 这样可防止意外创建无效的实例时创建结构的数组。  
  
 **✓ DO** 实现<xref:System.IEquatable%601>有关值类型。  
  
 <xref:System.Object.Equals%2A?displayProperty=nameWithType>有关值类型的方法会导致装箱，和其默认实现不是非常高效，因为它使用反射。 <xref:System.IEquatable%601.Equals%2A> 可以更好的性能，并且可以实现，以便它不会导致装箱。  
  
 **X DO NOT** 显式延长<xref:System.ValueType>。 事实上，大多数语言防止这种情况。  
  
 一般情况下，结构可能非常有用，但应仅用于小型、 单个、 不可变将不经常装箱的值。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [类型设计准则](../../../docs/standard/design-guidelines/type.md)  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [在类和结构之间选择](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
