---
title: 密封
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
ms.openlocfilehash: ddf463e98fb6a9c5ccaae90e9cfc74b5691b13a9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743621"
---
# <a name="sealing"></a>密封
面向对象的框架的一个特性是开发人员可以以框架设计者未曾预料到的方式扩展和定制它们。 这是可扩展设计的强大和危险之处。 因此，在设计框架时，必须根据需要仔细设计可扩展性并在不安全的情况下对其进行限制。

 防止可扩展性的强大机制是密封。 可以密封类或单个成员。 密封类会阻止用户继承该类。 密封成员可防止用户重写特定成员。

 ❌ 不要密封类，而不会有充分的理由。

 因为无法预料到可扩展性场景而密封一个类并不是一个充分的理由。 框架用户喜欢因各种非显而易见的原因继承类，比如添加一些便利的成员。 有关用户要从类型继承的 nonobvious 原因的示例，请参阅未[密封类](../../../docs/standard/design-guidelines/unsealed-classes.md)。

 对类进行密封的充足理由包括：

- 该类是一个静态类。 请参阅[静态类设计](../../../docs/standard/design-guidelines/static-class.md)。

- 该类在继承的受保护成员中存储了对安全敏感的机密。

- 该类继承了许多虚拟成员，单独密封它们的成本将超过使该类未密封的益处。

- 该类是一个需要极快速运行时查找的属性。 密封属性的性能水平略高于未密封的属性。 请参阅[特性](../../../docs/standard/design-guidelines/attributes.md)。

 ❌ 不在密封类型上声明受保护成员或虚拟成员。

 根据定义，不能从密封类型继承。 这意味着无法调用密封类型上的受保护成员，并且无法重写密封类型上的虚拟方法。

 ✔️考虑密封重写的成员。

 引入虚拟成员（在[虚拟成员](../../../docs/standard/design-guidelines/virtual-members.md)中讨论）可能会产生的问题也适用于重写，尽管稍微略低一些。 密封重写可以防止这些继承层次结构中的问题。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。

## <a name="see-also"></a>另请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
- [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
- [未密封类](../../../docs/standard/design-guidelines/unsealed-classes.md)
