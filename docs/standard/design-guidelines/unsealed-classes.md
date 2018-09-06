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
# <a name="unsealed-classes"></a>未密封类
密封的类不能被继承，并会阻止可扩展性。 与此相反，可以继承自的类称为未密封的类。  
  
 **✓ CONSIDER** 没有使用未密封的类添加虚拟或受保护成员，因为提供成本较低的好办法尚未非常感谢与框架的扩展性。  
  
 开发人员经常需要从以便添加方便成员，如自定义构造函数、 新方法或方法重载的未密封类继承。 例如，`System.Messaging.MessageQueue`是未密封，因此允许用户创建默认为特定的队列路径的自定义队列，或添加自定义方法，用于简化针对特定方案的 API。  
  
 类在最常用编程语言中，默认情况下未密封的这也是框架中的大多数类建议的默认设置。 未密封的类型提供可扩展性是 framework 用户更应有的重视和成本不高由于未密封的类型与关联的测试相对较低成本提供。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [密封](../../../docs/standard/design-guidelines/sealing.md)
