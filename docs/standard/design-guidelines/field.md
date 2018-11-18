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
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "45970651"
---
# <a name="field-design"></a>字段设计
封装原则是面向对象设计中最重要的概念之一。该原则规定存储在对象内的数据只能由该对象访问。
  
阐释该原则的一种方式是，一个类型应该被设计为可以在不破坏类型成员之外的代码的情况下对该类型的字段进行更改（名称或类型更改）。这种阐释紧接着表明所有字段必须是私有的。
  
我们从这个严格的限制中排除了常量和静态只读字段，因为根据定义，这些字段几乎不需要更改。
  
**X 切忌** 提供公共或受保护的实例字段。
  
您应提供访问字段的属性，而不是将其公开或受保护。
  
**✓ 务必** 使用常量字段表示永不改变的常量。

编译器将 const 字段的值直接烧写到调用代码中。因此，在没有破坏兼容性的风险的情况下，永远不能更改const值。

**✓ 务必** 对预定义的对象实例使用公共的静态的 `readonly` 字段。  

如果存在该类型的预定义实例，则将它们声明为该类型本身的公共只读静态字段。

**X 切忌** 将可变类型的实例分配给 `readonly` 字段。  

可变类型是具有可在实例化后修改的实例的类型。例如，数组，大多数集合和流都是可变类型，但是 <xref:System.Int32displayProperty=nameWithType>、<xref:System.Uri?displayProperty=nameWithType>、和 <xref:System.StringdisplayProperty=nameWithType> 都是不变的。引用类型字段上的只读修饰符可防止存储在字段中的实例被替换，但它不会阻止通过调用更改实例的员来修改字段的实例数据。
  
*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*
*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*
  
## <a name="see-also"></a>请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
