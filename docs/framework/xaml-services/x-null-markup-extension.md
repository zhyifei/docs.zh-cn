---
title: x:Null 标记扩展
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: 7dbea2c7d4010d8defc572dbdc14a0dfd6d7601e
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484710"
---
# <a name="xnull-markup-extension"></a>x:Null 标记扩展
指定`null`作为 XAML 成员的值。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a>备注  
 和C# C++中的空引用的关键字为 null。 Microsoft Visual Basic 关键字用于空引用`Nothing`, 但你始终使用`{x:Null}`作为 xaml 用法, 而不考虑与 xaml 关联的代码隐藏语言。  
  
 `x:Null`标记扩展没有可设置的属性。  
  
 Null 用法通常与 CLR <xref:System.Nullable%601>值的 XAML 成员公开关联。  
  
 标记扩展与所有 XAML 标记扩展一样, 使用大括号 (`{,}`) 将属性值的处理转义为非文本或事件处理程序引用。 `x:Null` 特性语法是最常用于该标记扩展的语法。 对象元素语法`<x:Null />`在技术上是可行的, 但很少使用`x:Null` , 因为标记扩展没有位置参数或构造参数。  
  
 有关标记扩展的信息, 请参阅[标记扩展和 WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md)。  
  
 在 .NET Framework XAML 服务中, 对此标记扩展的处理由<xref:System.Windows.Markup.NullExtension>类定义。  
  
## <a name="wpf-usage-notes"></a>WPF 使用说明  
 请注意`null` , 不一定是引用类型依赖属性的初始未设置值。 对于每个依赖属性, 初始默认值可能有所不同, 并且可以基于特定于属性的元数据。 许多依赖属性由于其验证`null`回调实现而不接受作为值。 有关依赖项属性的详细信息, 请参阅[依赖属性概述](../wpf/advanced/dependency-properties-overview.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [XAML 概述 (WPF)](../wpf/advanced/xaml-overview-wpf.md)
- [标记扩展和 WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
