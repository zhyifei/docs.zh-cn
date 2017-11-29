---
title: "x:Null 标记扩展"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- Null
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
caps.latest.revision: "20"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: a60d74bdf3343d02eaf912ac7700f36a649f659c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xnull-markup-extension"></a>x:Null 标记扩展
指定`null`作为 XAML 成员的值。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a>备注  
 中的 null 引用的关键字[!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)]和[!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)]为 null。 [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)]关键字为空引用是`Nothing`，但始终使用`{x:Null}`作为 XAML 用法无论与 XAML 关联的代码隐藏语言。  
  
 `x:Null`标记扩展有任何可设置属性。  
  
 Null 的使用情况通常是与 CLR 的 XAML 成员透露关联<xref:System.Nullable%601>值。  
  
 `x:Null`标记扩展，所有 XAML 标记扩展，如使用大括号 (`{,}`) 的转义特性值应为非文本或事件处理程序引用的处理。 特性语法是最常用于该标记扩展的语法。 对象元素语法`<x:Null />`是从技术上讲是可行的但很少使用，因为`x:Null`标记扩展有无位置参数或构造自变量。  
  
 有关标记扩展的信息，请参阅[标记扩展和 WPF XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)。  
  
 在.NET Framework XAML 服务，此标记扩展的处理的定义方法<xref:System.Windows.Markup.NullExtension>类。  
  
## <a name="wpf-usage-notes"></a>WPF 用法说明  
 请注意，`null`不一定是引用类型依赖项属性的初始未设置的值。 初始默认值可以为每个依赖项属性而异，并且可以基于特定属性的元数据。 不接受许多依赖项属性`null`作为值，通过标记或由于其验证回调实现的代码。 有关依赖项属性的详细信息，请参阅[依赖项属性概述](../../../docs/framework/wpf/advanced/dependency-properties-overview.md)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.DependencyProperty.UnsetValue>  
 [XAML 概述 (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [标记扩展和 WPF XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
