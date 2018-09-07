---
title: Attributes1
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51aa91b1acbae9f1a15ac12441090dd4c1c2dcb1
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43869138"
---
# <a name="attributes"></a>特性
<xref:System.Attribute?displayProperty=nameWithType> 用于定义自定义特性的基类。  
  
 属性是可以添加到程序集、 类型、 成员和参数等的编程元素的批注。 它们存储在程序集的元数据，可在运行时使用反射 Api 访问。 例如，该框架定义<xref:System.ObsoleteAttribute>，这可以应用于类型或成员，以指示类型或成员已被弃用。  
  
 属性可以具有一个或多个执行其他数据相关的属性的属性。 例如，`ObsoleteAttribute`可以携带有关中的发布的其他信息的类型或成员已弃用的和新的 Api 替换为已过时 API 的说明。  
  
 应用该属性时，必须指定属性的某些属性。 这些被称为所需的属性或所需的参数，因为它们表示作为位置构造函数参数。 例如，<xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A>属性的<xref:System.Diagnostics.ConditionalAttribute>是必需的属性。  
  
 一定不需要应用了该属性指定的属性被称为可选属性 （或可选参数）。 它们由可设置的属性表示。 编译器提供特殊语法来设置这些属性时应用的特性。 例如，<xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType>属性表示的可选参数。  
  
 **✓ DO** 命名自定义特性类带有后缀"属性"。  
  
 **✓ DO** 应用<xref:System.AttributeUsageAttribute>到自定义属性。  
  
 **✓ DO** 为可选自变量提供可设置属性。  
  
 **✓ DO** 提供所需的参数只获取属性。  
  
 **✓ DO** 提供构造函数参数初始化对应于所需的参数的属性。 每个参数应为相应的属性 （尽管具有不同大小写） 具有相同的名称。  
  
 **X AVOID** 提供构造函数参数初始化对应于可选参数的属性。  
  
 换而言之，不具有可使用构造函数和 setter 设置的属性。 此原则使非常明确，哪些参数是可选的它是必需的并可避免让两种方法执行同一操作。  
  
 **X AVOID** 重载自定义特性构造函数。  
  
 拥有一个构造函数清楚地传达给用户哪些参数是必需参数和可选。  
  
 **✓ DO** 尽可能密封自定义特性类。 这使属性查找速度更快。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
