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
ms.openlocfilehash: 672d36c6b888ee9a89a76d5d417a7a7e92dd8f36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571656"
---
# <a name="unsealed-classes"></a>未密封类
密封的类不能被继承，并会阻止扩展性。 与此相反，可以从继承的类称为未密封的类。  
  
 **✓ CONSIDER** 没有使用未密封的类添加虚拟或受保护成员，因为提供成本较低的好办法尚未非常感谢与框架的扩展性。  
  
 开发人员通常想要从以便添加方便成员，如自定义的构造函数、 新方法或方法重载的未密封类继承。 例如，`System.Messaging.MessageQueue`是未密封，因此允许用户创建自定义队列到特定的队列路径该默认行为或添加自定义方法来简化用于特定方案的 API。  
  
 类在最编程语言中，默认情况下未密封的这也是框架中的大多数类建议的默认设置。 未密封的类型提供的扩展性是得多应有的重视 framework 用户和提供由于相对较低的测试与未密封的类型相关联的成本很便宜。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [密封](../../../docs/standard/design-guidelines/sealing.md)
