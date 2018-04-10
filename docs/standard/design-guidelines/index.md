---
title: 框架设计准则
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c48b3cbaae4155a894ba77263505b2ca85238427
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="framework-design-guidelines"></a>框架设计准则
本部分提供有关设计的库扩展且使用.NET Framework 进行交互的准则。 目的是帮助确保通过提供用于开发的编程语言无关的统一编程模型的 API 一致性和易于使用的库设计器。 我们建议你遵循这些设计准则，开发的类和扩展.NET Framework 的组件时。 不一致的库设计产生负面影响开发人员工作效率，并且不鼓励采用。  
  
 这些准则组织为包含以这些前缀的简单建议`Do`， `Consider`， `Avoid`，和`Do not`。 这些指南旨在帮助了解不同的解决方案之间权衡的类库设计器。 可能有很好的库设计需要违反这些设计准则的情况。 这种情况下应该很少见，而且很重要，必须为你确定有充分的理由。  
  
 这些准则摘自书*Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式*、 Krzysztof Cwalina 和 Brad Abrams。  
  
## <a name="in-this-section"></a>本节内容  
 [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 命名程序集、 命名空间、 类型和成员类库中的提供了准则。  
  
 [类型设计准则](../../../docs/standard/design-guidelines/type.md)  
 提供用于静态和抽象类、 接口、 枚举、 结构和其他类型的准则。  
  
 [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
 提供有关设计和使用属性、 方法、 构造函数、 字段、 事件、 运算符和参数的准则。  
  
 [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 讨论了扩展性机制，例如子类化，使用事件、 虚拟成员和回调，并说明如何选择最好地满足您的框架的需求的机制。  
  
 [异常的设计准则](../../../docs/standard/design-guidelines/exceptions.md)  
 描述设计、 引发和捕获异常的设计准则。  
  
 [使用准则](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 介绍如何使用常见的类型，如数组、 属性和集合、 支持序列化，以及重载相等运算符的指南。  
  
 [常用设计模型](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 选择并实施依赖项属性和的释放模式提供了准则。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [概述](../../../docs/framework/get-started/overview.md)  
 [.NET Framework 的路线图](http://msdn.microsoft.com/library/0b46b7c6-9163-4f99-8e58-0d1ee7da8c67)  
 [开发指南](../../../docs/framework/development-guide.md)
