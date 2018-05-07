---
title: x:Reference 标记扩展
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: 960f5c0e4192df72090c1a571dfc2fc5e3fd8ba3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="xreference-markup-extension"></a>x:Reference 标记扩展
在 XAML 标记中其他位置声明的实例的引用。 引用所引用的元素`x:Name`。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object property="{x:Reference instancexName}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>XAML 对象元素用法  
  
```xaml  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`instancexName`|`x:Name`值 (或值<xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-标识属性) 的引用的实例。|  
  
## <a name="remarks"></a>备注  
 `x:Reference` 提供对否则在特定的框架，例如 WPF 中实现的一个元素引用概念 XAML 语言级别支持。  
  
## <a name="xreference-and-wpf"></a>X:reference 和 WPF  
 在 WPF 和 XAML 2006 中，元素引用都由框架级别功能的<xref:System.Windows.Data.Binding.ElementName%2A>绑定。 对于大多数 WPF 应用程序和方案，<xref:System.Windows.Data.Binding.ElementName%2A>应仍使用绑定。 此一般性指导异常可能包含情况下，有数据上下文或使数据绑定显得不切实际其他作用域注意事项以及标记编译不涉及到在其中。  
  
 `x:Reference` 在 XAML 2009 中定义一个构造。 在 WPF 中，可以使用 XAML 2009 功能，但仅针对未进行 WPF 标记编译的 XAML。 标记编译的 XAML 以及 BAML 形式的 XAML 当前不支持 XAML 2009 语言关键字和功能。
