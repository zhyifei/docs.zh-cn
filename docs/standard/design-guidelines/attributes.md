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
ms.openlocfilehash: 493ac709123c67311ba570894fb324ae7148bfae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574629"
---
# <a name="attributes"></a>特性
<xref:System.Attribute?displayProperty=nameWithType> 用于定义自定义特性的基类。  
  
 属性是可以添加到编程元素，如程序集、 类型、 成员和参数的批注。 它们存储在程序集的元数据，并可以在运行时使用反射 Api 访问。 例如，框架定义<xref:System.ObsoleteAttribute>，此方法可用于为类型或成员，以指示类型或成员已被否决。  
  
 属性可以携带与属性相关的其他数据的一个或多个属性。 例如，`ObsoleteAttribute`无法携带有关中的发布版本的其他信息的类型或成员已弃用并替换已过时 API 的新 Api 的说明。  
  
 应用该特性，则必须指定属性的某些属性。 这些被称为所需的属性或必需的参数，因为它们表示为从位置构造函数参数。 例如，<xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A>属性<xref:System.Diagnostics.ConditionalAttribute>是必需的属性。  
  
 不一定需要应用了该属性指定的属性被称为可选属性 （或可选自变量）。 它们由可设置属性表示。 编译器提供用于设置这些属性时应用的特性的特殊语法。 例如，<xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType>属性表示的可选自变量。  
  
 **✓ DO**命名自定义特性类带有后缀"属性"。  
  
 **✓ DO**应用<xref:System.AttributeUsageAttribute>到自定义属性。  
  
 **✓ DO**为可选自变量提供可设置属性。  
  
 **✓ DO**提供所需的参数只获取属性。  
  
 **✓ DO**提供构造函数参数初始化对应于所需的参数的属性。 每个参数应为对应的属性 （尽管具有不同大小写） 具有相同的名称。  
  
 **X AVOID**提供构造函数参数初始化对应于可选参数的属性。  
  
 没有换而言之，可用设置的一个构造函数和 setter 的属性。 此原则使很明确的哪些参数是可选的它是必需的并可避免让两种做同样的事情。  
  
 **X AVOID**重载自定义特性构造函数。  
  
 具有只有一个构造函数清楚地向用户的参数是必需的哪些对象是可选。  
  
 **✓ DO**尽可能密封自定义特性类。 这使属性查找的速度更快。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)
