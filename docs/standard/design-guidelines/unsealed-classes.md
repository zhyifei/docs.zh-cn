---
title: 非密封类
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: KrzysztofCwalina
ms.openlocfilehash: 8d7b1500506ec73a0d33d5352756cb85039358e5
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153223"
---
# <a name="unsealed-classes"></a>非密封类
密封的类不能被继承，并会阻止可扩展性。 与此相反，可被继承的类称为非密封类。  
  
 **✓ 考虑**使用未添加虚拟或受保护成员的非密封类，这是为框架提供经济但有效的可扩展性的好方法。  

 开发人员通常希望从非密封的类继承，以便添加自定义构造函数、新方法或方法重载等便利成员。 例如，`System.Messaging.MessageQueue` 是非密封的，因此用户可以创建默认为特定队列路径的自定义队列，或添加自定义方法以简化特定方案的 API。  

 在大多数编程语言中，默认情况下类都是非密封的，这也是框架中大多数类的推荐默认值。 框架用户非常需要非密封类型提供的可扩展性，并且这种可扩展性的提供成本相当低，因为非密封类型的相关测试成本也相对较低。  

*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*

 *通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [密封](../../../docs/standard/design-guidelines/sealing.md)
