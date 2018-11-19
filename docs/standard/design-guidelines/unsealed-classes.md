---
title: 未密封类
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef0f1c4c9b2d1928d6f96d62ab12df9786756498
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891372"
---
# <a name="unsealed-classes"></a>非密封类
密封的类不能被继承，并会阻止可扩展性。与此相反，可以继承的类称为非密封类。  
  
**✓ 考虑** 使用没有添加虚拟或受保护成员的非密封类，因为这是为框架提供经济但非常用的可扩展性的好方法。

开发人员经常希望从非密封的类继承，以便添加自定义构造函数、新方法或方法重载等便利员。例如，`System.Messaging.MessageQueue` 是非密封的，因此允许用户创建默认为定队列路径的自定义队列，或添加自定义方法以简化特定方案的API。

在大多数编程语言中，默认情况下类都是非密封的，这也是框架中大多数类的推荐默认值。架用户非常需要由非密封类型提供的可扩展性，并且提供的成本相当低，因为与非密封类型关的测试成本也相对较低。

*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*

*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [密封](../../../docs/standard/design-guidelines/sealing.md)
