---
title: 接口设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c687d7622e82ee206b2201760818827398f8543b
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863715"
---
# <a name="interface-design"></a>接口设计
尽管大多数 Api 最适合使用类和结构进行建模，存在一些情况下在其中更合适或接口的唯一选择。  
  
 CLR 不支持多重继承 （即，CLR 类不能从多个基类继承），但是它的确允许实现除了继承自基类的一个或多个接口的类型。 因此，接口通常用于实现多个继承的效果。 例如，<xref:System.IDisposable>是一个接口，允许支持 disposability 独立于他们想要参与任何其他继承的层次结构的类型。  
  
 在创建了公共接口，可以支持几种类型，包括某些值类型的接口是在其中定义相应的其他情况。 值类型不能继承自类型而不<xref:System.ValueType>，但它们可以实现接口，因此使用的接口是为了提供一个公共基类型的唯一选项。  
  
 **✓ DO** 定义一个接口，如果你需要一些常见的 API 来支持的一组包含值类型的类型。  
  
 **✓ CONSIDER** 定义的接口，如果你需要在已继承自其他类型的类型上支持其功能。  
  
 **X AVOID** 使用标记接口 （不包含任何成员的接口）。  
  
 如果你需要将标记为具有特定特征 （标记） 的类，一般情况下，使用自定义特性而不是接口。  
  
 **✓ DO**提供至少一种类型的接口的实现。  
  
 这些措施可帮助验证接口的设计。 例如，<xref:System.Collections.Generic.List%601>是一种实现的<xref:System.Collections.Generic.IList%601>接口。  
  
 **✓ DO**提供使用你定义的每个接口的至少一个 API （采用作为参数或属性的接口的方法类型化为接口）。  
  
 这些措施可帮助验证界面设计。 例如，<xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType>使用<xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType>接口。  
  
 **X DO NOT** 将成员添加到具有以前发布的接口。  
  
 执行此操作将会破坏接口的实现。 为了避免版本控制问题，应创建新的接口。  
  
 除了这些指南中所述的情况下，您应，一般情况下，选择类而不是接口在设计托管的代码的可重用库。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [类型设计准则](../../../docs/standard/design-guidelines/type.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
