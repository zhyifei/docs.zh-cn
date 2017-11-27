---
title: "密封"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8caa253a3f17c58f542317de579c4f7832c4efac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="sealing"></a>密封
面向对象的框架的功能之一是开发人员可以扩展和采用 framework designer 意料之外的方法来自定义它们。 这是设计的两个电源和可扩展的危险。 当您设计您的框架时，它是，因此，若要为扩展性仔细设计，当需要它时，以及限制扩展性危险时非常重要。  
  
 密封可以防止扩展性的强大机制。 你可以密封的类或单个成员。 密封类，将阻止用户从类继承。 密封成员可防止用户重写特定成员。  
  
 **X 不**密封类，而无需有充分的理由要这样做。  
  
 密封类，因为您不能将扩展性方案不充分的理由。 Framework 用户希望能够从类继承由于各种 nonobvious 原因，例如添加方便成员。 请参阅[未密封类](../../../docs/standard/design-guidelines/unsealed-classes.md)的 nonobvious 原因示例用户想要为从一种类型继承。  
  
 良好的密封类的原因包括：  
  
-   此类是静态的类。 请参阅[静态类设计](../../../docs/standard/design-guidelines/static-class.md)。  
  
-   类继承的受保护成员中存储安全敏感机密。  
  
-   类继承的多个虚成员，密封它们单独的成本将带来的好处将保留未密封的类。  
  
-   类是需要非常快的运行时查找的属性。 密封的属性具有略高的性能级别，比未密封的。 请参阅[属性](../../../docs/standard/design-guidelines/attributes.md)。  
  
 **X 不**在密封类型中声明受保护或虚拟成员。  
  
 根据定义，不能从继承密封的类型。 这意味着不能调用密封类型上的受保护的成员，并且密封类型上的虚拟方法不能重写。  
  
 **请考虑 ✓**密封重写的成员。  
  
 引入虚拟成员所产生的问题 (中所述[虚拟成员](../../../docs/standard/design-guidelines/virtual-members.md)) 应用到同样，重写应用尽管到略有一定程度上。 密封替代可保护从继承层次结构中该点开始这些问题。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>另请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [未密封的类](../../../docs/standard/design-guidelines/unsealed-classes.md)
