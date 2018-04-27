---
title: 抽象类设计
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
caps.latest.revision: 13
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a98c40ccc8005789a3a991bfc93deb11786b8943
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="abstract-class-design"></a>抽象类设计
**X 不**在抽象类型中定义公共或受保护内部构造函数。  
  
 构造函数应为公共的仅当用户将需要创建该类型的实例。 由于无法创建抽象类型的实例，具有公共构造函数的抽象类型不正确地设计和都误导性的用户。  
  
 **✓ 执行**在抽象类中定义为受保护或内部构造函数。  
  
 受保护的构造函数更常见的是，并只允许基类，来创建子类型时执行自己的初始化。  
  
 内部构造函数可以用于限制对定义的类的程序集的抽象类的具体实现。  
  
 **✓ 执行**提供至少一个继承自每个抽象类，要交付的具体类型。  
  
 执行此有助于验证抽象类的设计。 例如，<xref:System.IO.FileStream?displayProperty=nameWithType>实现的<xref:System.IO.Stream?displayProperty=nameWithType>抽象类。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [类型设计准则](../../../docs/standard/design-guidelines/type.md)  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)
