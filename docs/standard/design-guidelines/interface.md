---
title: 接口设计
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
ms.openlocfilehash: 544035180a5004bfe2f4c75c680116e52bf25f98
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744152"
---
# <a name="interface-design"></a>接口设计
虽然大多数 API 最好使用类和结构进行建模，但有些情况下接口更合适或是唯一的选择。

 CLR 不支持多重继承（即，CLR 类不能从多个基类继承），但它允许类型除了继承基类之外还实现一个或多个接口。 因此，通常使用接口来实现多重继承的效果。 例如，<xref:System.IDisposable> 是一个接口，该接口允许类型独立于要参与的任何其他继承层次结构来支持 disposability。

 适合定义接口的另一种情况是创建一个可以由多种类型支持的公共接口，包括一些值类型。 值类型不能从 <xref:System.ValueType>以外的类型继承，但它们可以实现接口，因此，使用接口是提供公共基类型的唯一选项。

 如果需要某些包含值类型的类型集支持某些常见 API，✔️确实要定义接口。

 ✔️如果需要在已从其他类型继承的类型上支持其功能，请考虑定义接口。

 ❌ 避免使用标记接口（没有成员的接口）。

 如果需要将类标记为具有特定特征（标记），通常使用自定义特性而不是接口。

 ✔️提供至少一种类型作为接口的实现。

 此做法有助于验证接口的设计。 例如，<xref:System.Collections.Generic.List%601> 是 <xref:System.Collections.Generic.IList%601> 接口的实现。

 ✔️提供至少一个使用你定义的每个接口的 API （将接口用作参数的方法或类型化为接口的属性）。

 此做法有助于验证接口设计。 例如，<xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> 使用 <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> 接口。

 ❌ 不要将成员添加到之前已发货的接口。

 这样做会破坏接口的实现。 应创建一个新接口以避免版本控制问题。

 除了这些指南中描述的情况之外，一般情况下，应该在设计托管代码的可重用库时选择类而不是接口。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。

## <a name="see-also"></a>另请参阅

- [类型设计准则](../../../docs/standard/design-guidelines/type.md)
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
