---
title: 静态类设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3a0a51fc6055190f9a0189de2e17d98f88036ea
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46518043"
---
# <a name="static-class-design"></a>静态类设计
静态类被定义为仅包含静态成员的类 (当然除了继承自的实例成员<xref:System.Object?displayProperty=nameWithType>和可能是私有构造函数)。 某些语言用于静态类提供内置支持。 在 C# 2.0 及更高版本，当一个类声明为静态，密封的抽象，并且可以重写任何实例成员，或将其声明。  
  
 静态类是纯粹的面向对象的设计和简单性之间泄漏。 它们通常用于提供其他操作的快捷方式 (如<xref:System.IO.File?displayProperty=nameWithType>)，持有者的扩展方法或为其完整的面向对象的包装器是不能确保的功能 (如<xref:System.Environment?displayProperty=nameWithType>)。  
  
 **✓ DO** 静态类应谨慎使用。  
  
 应仅作为 framework 的面向对象的核心的支持类使用静态的类。  
  
 **X DO NOT** 静态类视为杂项存储桶。  
  
 **X DO NOT** 声明或重写中的静态类的实例成员。  
  
 **✓ DO** 静态类声明为密封的抽象，并添加一个私有实例构造函数，如果您的编程语言不具有对静态类的内置支持。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [类型设计准则](../../../docs/standard/design-guidelines/type.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
