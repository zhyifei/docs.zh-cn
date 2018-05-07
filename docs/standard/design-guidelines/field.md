---
title: 字段设计
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d47934c3fed17f75a97ef5da0397c6ceba53d68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="field-design"></a>字段设计
封装原则是最重要的概念之一在面向对象的设计。 这一原则指出，应仅供该对象存储在对象内的数据。  
  
 有用的方式解释原则是说，以便对该类型 （名称或类型的更改） 的字段可以进行更改而不会破坏以外的其他代码的类型的成员，应设计类型。 此解释立即意味着所有字段必须都是私有的。  
  
 因为此类字段，几乎根据定义，永远不会需要更改，我们会从此严格限制，排除常数和静态只读字段。  
  
 **X 不**提供公共或受保护的实例字段。  
  
 你应提供用于访问而不是进行这些公共或受保护的字段的属性。  
  
 **✓ 执行**常量字段用于将永远不会更改的常量。  
  
 编译器在直接到调用代码之前完成剩余的 const 字段的值。 因此，常量值永远不会更改就不会破坏兼容性的风险。  
  
 **✓ 执行**使用公共静态`readonly`预定义的对象实例的字段。  
  
 如果没有预定义的类型实例，请将它们声明为公共只读的静态字段的类型本身。  
  
 **X 不**分配到的可变类型的实例`readonly`字段。  
  
 可变类型是可在于实例化之后进行修改的实例的类型。 例如，数组、 大多数集合和流是可变类型，但<xref:System.Int32?displayProperty=nameWithType>， <xref:System.Uri?displayProperty=nameWithType>，和<xref:System.String?displayProperty=nameWithType>是所有不可变。 引用类型字段上的只读修饰符可防止在从被替换，字段中存储的实例，但不会阻止该字段的实例数据被修改通过更改实例的调用成员。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)
