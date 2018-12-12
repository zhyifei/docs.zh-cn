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
author: KrzysztofCwalina
ms.openlocfilehash: fd1abdb4ff6f4850eea96bcfc3afbfe00a4ae56a
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127688"
---
# <a name="sealing"></a>密封
面向对象的框架的功能之一是开发人员可以扩展和未预料到框架设计器的方式自定义它们。 这是设计的两个电源和可扩展的危险。 在设计您的框架，它，因此是非常重要时需要，仔细设计可扩展性以及限制可扩展性时这是很危险。  
  
 密封可以防止可扩展性的强大机制。 密封类或单个成员。 密封类，可阻止用户从类继承。 密封成员可阻止用户重写特定成员。  
  
 **X DO NOT** 密封类，而无需有充分的理由要这样做。  
  
 密封类，因为您不能将可扩展性方案不是一个充分的理由。 框架用户希望从类继承的各种 nonobvious 原因，例如，添加方便成员。 请参阅[未密封类](../../../docs/standard/design-guidelines/unsealed-classes.md)有关 nonobvious 原因的示例用户想要继承的类型。  
  
 密封类充分的理由包括：  
  
-   类是一个静态类。 请参阅[静态类设计](../../../docs/standard/design-guidelines/static-class.md)。  
  
-   类继承的受保护成员中存储安全敏感机密。  
  
-   类继承许多虚拟成员和密封它们单独的成本会超过保留的未密封的类的好处。  
  
-   类是需要非常快的运行时查找的属性。 密封的属性具有比未密封的略高性能级别。 请参阅[属性](../../../docs/standard/design-guidelines/attributes.md)。  
  
 **X DO NOT** 在密封类型中声明受保护或虚拟成员。  
  
 根据定义，不能从继承密封的类型。 这意味着不能调用密封类型上受保护的成员，并且不能重写密封类型上的虚方法。  
  
 **✓ CONSIDER** 密封重写的成员。  
  
 从引入虚拟成员可能导致问题，(中所述[虚拟成员](../../../docs/standard/design-guidelines/virtual-members.md)) 适用于替代，尽管到略有一定程度上。 密封替代使您可以避免这些问题从继承层次结构中该点开始。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [未密封类](../../../docs/standard/design-guidelines/unsealed-classes.md)
