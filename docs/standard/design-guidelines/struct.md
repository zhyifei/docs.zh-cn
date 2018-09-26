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
ms.openlocfilehash: 3879dc3f0270a56132b44882a74c50d05914ff89
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47176589"
---
# <a name="struct-design"></a>结构设计
常规用途的值类型通常称为结构，其 C# 关键字。 本部分提供有关常规结构设计指导原则。  
  
 **X DO NOT** 结构提供默认构造函数。  
  
 遵循此原则，而无需对数组的每个项运行构造函数创建的结构数组。 请注意，C# 不允许结构拥有默认构造函数。  
  
 **X DO NOT** 定义可变值类型。  
  
 可变值类型具有几个问题。 例如，当属性 getter 将返回值类型，调用方会接收一个副本。 隐式创建的副本，因为开发人员可能不知道它们转变副本，而不是原始值。 此外，某些语言 （尤其是动态语言） 有问题使用可变值类型，因为即使本地变量，取消引用时，会导致副本来进行。  
  
 **✓ DO** 确保其中所有实例数据的状态设置为零，false，或 null （根据需要） 是否有效。  
  
 这可以防止意外创建无效的实例时创建的结构数组。  
  
 **✓ DO** 实现<xref:System.IEquatable%601>有关值类型。  
  
 <xref:System.Object.Equals%2A?displayProperty=nameWithType>值类型上的方法会导致装箱，并且其默认实现不是非常高效，因为它使用反射。 <xref:System.IEquatable%601.Equals%2A> 可以更好的性能，并且可以实现，以便它不会导致装箱。  
  
 **X DO NOT** 显式延长<xref:System.ValueType>。 实际上，大多数语言禁止此行为。  
  
 一般情况下，结构可能非常有用，但仅用于不会频繁装箱的小规模、 单个的不可变值。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [类型设计准则](../../../docs/standard/design-guidelines/type.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [在类和结构之间选择](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
