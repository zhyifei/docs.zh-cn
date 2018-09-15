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
ms.openlocfilehash: 65c54fe9a076a219c61280a98c390b16f56b5015
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2018
ms.locfileid: "45649397"
---
# <a name="field-design"></a>字段设计
封装原则是最重要的概念之一中面向对象的设计。 此原则指出，应仅对该对象可访问的对象内存储的数据。  
  
 有用的方式来解释原则是说，以便对该类型 （名称或类型的更改） 的字段的更改可以进行而不会破坏代码以外的其他类型的成员，应设计一种类型。 此解释立即意味着所有字段必须都为私有。  
  
 因为此类字段，根据定义，几乎从不需要更改，我们会从这种严格限制，排除常量和静态只读字段。  
  
 **X DO NOT** 提供公共或受保护的实例字段。  
  
 您应提供用于访问而不是使它们成为公共或受保护的字段的属性。  
  
 **✓ DO** 常量字段用于将永远不会更改的常量。  
  
 编译器加深直接到调用代码的常量字段的值。 因此，可以永远不会更改常量值，而不必冒险破坏兼容性。  
  
 **✓ DO** 使用公共静态`readonly`预定义的对象实例的字段。  
  
 如果有预定义的类型实例，请将它们声明为公共只读静态字段的类型本身。  
  
 **X DO NOT** 分配到的可变类型的实例`readonly`字段。  
  
 可变类型是具有可将它们实例化之后修改的实例的类型。 例如，数组中，大多数集合和流是可变类型，但<xref:System.Int32?displayProperty=nameWithType>， <xref:System.Uri?displayProperty=nameWithType>，和<xref:System.String?displayProperty=nameWithType>是所有固定不变。 上一个引用类型字段的只读修饰符可以防止实例存储在字段中被替换，但不会阻止该字段的实例数据更改的实例的调用成员被修改。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
