---
title: 接口设计
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: dc7185f9541952d528de38b627052239f5d8b4ae
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="interface-design"></a>接口设计
尽管大多数 Api 最佳使用类和结构进行建模，有一些情况下在其中更合适或接口的唯一选择。  
  
 CLR 不支持多重继承 （即，CLR 类不能从多个基类继承），但它允许实现除了从基类继承的一个或多个接口的类型。 因此，接口通常用于实现多重继承的效果。 例如，<xref:System.IDisposable>是一个接口，用于类型来支持 disposability 独立于他们想要参与任何其他继承的层次结构。  
  
 其他接口中的定义是相应的情形是在创建了公共接口，可以支持几种类型，包括某些值类型。 值类型不能从继承类型以外<xref:System.ValueType>，但它们可以实现接口，因此使用接口是为了提供通用的基类型的唯一选项。  
  
 **✓ 执行**定义一个接口，如果你需要一些常见的 API 来支持的一组包含值类型的类型。  
  
 **请考虑 ✓**定义的接口，如果你需要在已继承自其他类型的类型上支持其功能。  
  
 **请避免 x**使用标记接口 （不包含任何成员的接口）。  
  
 如果你需要将标记为具有特定特征 （标记） 的类，通常情况下，使用的自定义特性，而不是接口。  
  
 **✓ 执行**提供至少一种类型的接口的实现。  
  
 执行此可帮助验证接口的设计。 例如，<xref:System.Collections.Generic.List%601>实现的<xref:System.Collections.Generic.IList%601>接口。  
  
 **✓ 执行**提供使用你定义的每个接口的至少一个 API （采用作为参数或属性的接口的方法类型化为接口）。  
  
 执行此可帮助验证接口设计。 例如，<xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType>使用<xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType>接口。  
  
 **X 不**将成员添加到具有以前发布的接口。  
  
 这样将会破坏接口的实现。 为了避免版本控制问题，应创建一个新的接口。  
  
 除了这些准则中所述的情况下，你应该一般情况下，选择类，而不是接口在设计托管的代码可重用库。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [类型设计准则](../../../docs/standard/design-guidelines/type.md)  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)
