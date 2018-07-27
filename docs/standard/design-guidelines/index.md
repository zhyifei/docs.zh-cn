---
title: 框架设计准则
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2674acf14aae5e892dfb9707a19cca12b4797c90
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572978"
---
# <a name="framework-design-guidelines"></a>框架设计准则
本部分提供的准则适用于设计那些可扩展 .NET Framework 并与之交互的库。 目的是通过提供独立于开发所用编程语言的统一编程模型，帮助库设计者确保 API 的一致性和易用性。 建议在开发可扩展 .NET Framework 的类和组件时遵循这些设计准则。 不一致的库设计会对开发人员的工作效率产生负面影响，影响用户采用它。  
  
 这些准则已整理成简单的建议，其开头词为`要 `Do``，`考虑 `Consider``，`避免 `Avoid``和`不要 `Do not``。 这些准则旨在帮助类库设计人员了解如何在不同解决方案之间进行权衡取舍。 在某些情况下，若要进行良好的库设计，必须违反这些设计准则。 这种情况应该很罕见，重要的是，你的决定要有明确和令人信服的理由。  
  
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
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [概述](../../../docs/framework/get-started/overview.md)  
 [.NET Framework 的路线图](https://msdn.microsoft.com/library/0b46b7c6-9163-4f99-8e58-0d1ee7da8c67)  
 [开发指南](../../../docs/framework/development-guide.md)
