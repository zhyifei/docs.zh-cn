---
title: "静态类设计"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8c36bf5790d033eddb6bb7e0d910482143a9bcac
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="static-class-design"></a>静态类设计
静态该类可以定义为仅包含静态成员的类 (当然除了从继承的实例成员<xref:System.Object?displayProperty=nameWithType>和可能是一个专用的构造函数)。 某些语言为静态的类提供内置支持。 在 C# 2.0 版和更高版本的类声明为静态，它是密封的抽象，，可以重写任何实例成员，或将其声明。  
  
 静态类是纯的面向对象的设计和简易性之间的折衷。 它们通常用于提供其他操作的快捷方式 (如<xref:System.IO.File?displayProperty=nameWithType>)，持有人的扩展方法或为其完整的面向对象的包装，则不能确保的功能 (如<xref:System.Environment?displayProperty=nameWithType>)。  
  
 **✓ 执行**静态类应谨慎使用。  
  
 静态类应只可用作支持框架的面向对象的核心的类。  
  
 **X 不**静态类视为杂项存储桶。  
  
 **X 不**声明或重写中的静态类的实例成员。  
  
 **✓ 执行**静态类声明为密封的抽象，并添加一个私有实例构造函数，如果您的编程语言不具有对静态类的内置支持。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [类型设计准则](../../../docs/standard/design-guidelines/type.md)  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)
