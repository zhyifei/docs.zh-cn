---
title: 静态类设计
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
ms.openlocfilehash: 35bcf1d403c78cdfcbb476b2eb5de2251a564b9a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709057"
---
# <a name="static-class-design"></a>静态类设计
静态类的定义为：仅包含静态成员的类 (当然除了继承自<xref:System.Object?displayProperty=nameWithType> 的实例成员和可能是私有的构造函数)。 某些语言提供对静态类的内置支持。 在 C# 2.0 及更高版本中，当类声明为静态时，它是密封、抽象的，并且不能覆盖或声明实例成员。  
  
 静态类是纯面向对象设计和简单性之间的妥协。 它们通常用于提供其他操作的快捷方式（例如<xref:System.IO.File?displayProperty=nameWithType> ），扩展方法的持有者，或完全面向对象的包装器不合适的功能（例如<xref:System.Environment?displayProperty=nameWithType> ）。  
  
 **✓ 务必** 谨慎使用静态类。  
  
 静态类应仅用作框架的面向对象核心的支持类。  
  
 **X DO NOT** 静态类视为杂项存储桶。  
  
 **X 切忌** 在静态类中声明或覆盖实例成员。  
  
 **✓ 务必** 将静态类声明为密封，抽象，并添加一个私有实例构造函数，如果您的编程语言没有内置静态类支持的话。  
  
 *部分©2005，2009 Microsoft Corporation。保留所有权利。*  
  
 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。  
  
## <a name="see-also"></a>另请参阅

- [类型设计准则](../../../docs/standard/design-guidelines/type.md)
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
